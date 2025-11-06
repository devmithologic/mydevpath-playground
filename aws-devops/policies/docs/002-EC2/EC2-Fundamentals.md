## ¿Qué es Amazon EC2?

**Amazon Elastic Compute Cloud (EC2)** es un servicio de computación en la nube que proporciona capacidad de cómputo escalable. Permite lanzar servidores virtuales (instancias) bajo demanda, pagando solo por los recursos que utilizas.

### Características Principales

- **Elasticidad**: Escala vertical y horizontalmente según necesidad
- **Modelos de pago**: On-Demand, Reserved, Spot Instances
- **Control total**: Acceso root/administrador a las instancias
- **Integración**: Se conecta nativamente con otros servicios AWS

---

## Regiones y Zonas de Disponibilidad

### Regiones (Regions)

Las **regiones de AWS** son ubicaciones geográficas físicas alrededor del mundo donde AWS agrupa sus centros de datos.

**Características clave:**

- Cada región es completamente independiente
- Los recursos NO se replican automáticamente entre regiones
- Cada región tiene su propio conjunto de servicios y precios
- Debes seleccionar explícitamente la región al crear recursos

**Ejemplos de regiones:**

- `us-east-1` - Norte de Virginia
- `us-west-2` - Oregón
- `eu-west-1` - Irlanda
- `ap-southeast-1` - Singapur

### Zonas de Disponibilidad (Availability Zones - AZs)

Cada región contiene múltiples **Zonas de Disponibilidad** aisladas físicamente pero conectadas con red de baja latencia.

**Conceptos importantes:**

- Las AZs están diseñadas para tolerancia a fallos
- Distribuir instancias entre AZs aumenta la disponibilidad
- Identificadas como: `us-east-1a`, `us-east-1b`, etc.

### Consideraciones Multi-Región

**¿Por qué usar múltiples regiones?**

- **Latencia**: Servir usuarios más cerca geográficamente
- **Compliance**: Requisitos de residencia de datos
- **Disaster Recovery**: Redundancia geográfica total
- **Alta disponibilidad**: Protección contra fallas regionales

---

## Security Groups: Firewalls Virtuales

### ¿Qué son los Security Groups?

Los **Security Groups** actúan como **firewalls virtuales** a nivel de instancia que controlan el tráfico de entrada (inbound) y salida (outbound) de tus instancias EC2.

### Características Fundamentales

### Comportamiento Stateful

- **Stateful**: Si permites tráfico entrante, la respuesta saliente es automáticamente permitida
- No necesitas crear reglas explícitas de salida para respuestas
- El sistema recuerda las conexiones establecidas

### Modelo "Deny by Default"

- **Por defecto, todo el tráfico entrante está BLOQUEADO**
- **Por defecto, todo el tráfico saliente está PERMITIDO**
- Solo defines reglas de **permiso** (allow), no de denegación (deny)

### Alcance Regional

- Los Security Groups son **específicos de cada región**
- Si creas instancias en `us-east-1` y `eu-west-1`, necesitas security groups separados
- No puedes reutilizar un SG entre regiones

### Asociación con Instancias

- Una instancia puede tener **múltiples Security Groups** (hasta 5)
- Un Security Group puede proteger **múltiples instancias**
- Los cambios en un SG se aplican **inmediatamente** a todas las instancias asociadas

---

## Estructura de Reglas de Security Groups

### Reglas de Entrada (Inbound Rules)

Controlan qué tráfico puede **llegar** a tu instancia.

### Componentes de una Regla Inbound

```bash
┌─────────────────────────────────────────────────────────┐
│ Type     | Protocol | Port Range | Source               │
├─────────────────────────────────────────────────────────┤
│ SSH      | TCP      | 22         | 0.0.0.0/0            │
│ HTTP     | TCP      | 80         | 0.0.0.0/0            │
│ HTTPS    | TCP      | 443        | 0.0.0.0/0            │
│ Custom   | TCP      | 8080       | sg-0123456789abcdef  │
└─────────────────────────────────────────────────────────┘
```

### Tipos de Origen (Source)

1. **CIDR Block**: Rango de IPs
    - `0.0.0.0/0` - Todo internet (público)
    - `10.0.0.0/16` - Red privada específica
    - `203.0.113.25/32` - IP específica (el `/32` significa solo esa IP)
2. **Security Group**: Otro security group
    - `sg-0123456789abcdef` - Permite tráfico desde instancias con ese SG
    - Útil para arquitecturas multi-tier
3. **Prefix List**: Lista de rangos IP administrados por AWS
    - `pl-id-for-s3` - Por ejemplo, para servicios AWS

### Reglas de Salida (Outbound Rules)

Controlan qué tráfico puede **salir** de tu instancia.

### Regla por Defecto

```bash
┌─────────────────────────────────────────────────────────┐
│ Type        | Protocol | Port Range | Destination       │
├─────────────────────────────────────────────────────────┤
│ All traffic | All      | All        | 0.0.0.0/0         │
└─────────────────────────────────────────────────────────┘
```

Por defecto, las instancias pueden comunicarse con cualquier destino.

---

---

## Configuraciones Comunes de Security Groups

### 1. Web Server Security Group

**Propósito**: Servidor web público (nginx, Apache, Node.js)

**Inbound Rules:**

```bash
SSH      | TCP | 22   | Tu_IP/32          | Administración
HTTP     | TCP | 80   | 0.0.0.0/0         | Tráfico web
HTTPS    | TCP | 443  | 0.0.0.0/0         | Tráfico web seguro
```

**Outbound Rules:**

```bash
All traffic | All | All | 0.0.0.0/0   | (regla por defecto)
```

### 2. Application Server Security Group

**Propósito**: Servidor de aplicaciones en capa privada

**Inbound Rules:**

```bash
Custom TCP | TCP | 8080 | sg-web-servers    | Desde web tier
SSH        | TCP | 22   | sg-bastion-host   | Administración
```

**Outbound Rules:**

```bash
PostgreSQL | TCP | 5432 | sg-database       | Acceso a DB
HTTPS      | TCP | 443  | 0.0.0.0/0        | APIs externas
```

### 3. Database Security Group

**Propósito**: Base de datos (PostgreSQL, MySQL, MongoDB)

**Inbound Rules:**

```bash
PostgreSQL | TCP | 5432 | sg-app-servers    | Desde app tier
MySQL      | TCP | 3306 | sg-app-servers    | Desde app tier
MongoDB    | TCP | 27017| sg-app-servers    | Desde app tier
```

**Outbound Rules:**

```bash
(Generalmente restringido, solo lo necesario)
```

### 4. Bastion Host / Jump Server

**Propósito**: Punto de entrada seguro para administración

**Inbound Rules:**

```bash
SSH | TCP | 22 | Tu_IP_Oficina/32     | SSH desde ubicación confiable
```

**Outbound Rules:**

```bash
SSH | TCP | 22 | sg-private-instances  | SSH a instancias privadas
```

### 5. Load Balancer Security Group

**Propósito**: Application/Network Load Balancer

**Inbound Rules:**

```bash
HTTP  | TCP | 80  | 0.0.0.0/0    | Tráfico público
HTTPS | TCP | 443 | 0.0.0.0/0    | Tráfico público seguro
```

**Outbound Rules:**

```bash
Custom TCP | TCP | 8080 | sg-web-servers    | Health checks y tráfico
```

---

## Mejores Prácticas de Security Groups

### 1. Principio de Menor Privilegio

```bash
# ❌ MAL - Demasiado permisivo
SSH | TCP | 22 | 0.0.0.0/0

# ✅ BIEN - Solo tu IP
SSH | TCP | 22 | 203.0.113.25/32

# ✅ MEJOR - Rango de tu oficina
SSH | TCP | 22 | 203.0.113.0/24
```

### 2. Nomenclatura Descriptiva

```bash
# Estructura recomendada
[entorno]-[capa]-[función]-sg

Ejemplos:
prod-web-public-sg
dev-app-private-sg
staging-db-postgres-sg
prod-bastion-ssh-sg
```

### 3. Usa Security Groups Referencias

```bash
# En lugar de IPs hardcodeadas
Source: sg-app-tier-12345

# Beneficios:
- Auto-actualización si las IPs cambian
- Más legible y mantenible
- Mejor para entornos dinámicos
```

### 4. Separa por Capas (Tier Segregation)

```bash
Internet
    ↓
[Load Balancer SG]
    ↓
[Web Tier SG]
    ↓
[App Tier SG]
    ↓
[Database Tier SG]
```

### 5. Documenta y Etiqueta

```json
Tags:
{
  "Name": "prod-web-public-sg",
  "Environment": "Production",
  "Tier": "Web",
  "ManagedBy": "Terraform",
  "Owner": "DevOps Team"
}
```

### 6. Audita Regularmente

```bash
# Busca reglas peligrosas
# SSH abierto al mundo
aws ec2 describe-security-groups \
  --filters "Name=ip-permission.from-port,Values=22" \
            "Name=ip-permission.cidr,Values=0.0.0.0/0"

# Todos los puertos abiertos
aws ec2 describe-security-groups \
  --query 'SecurityGroups[?IpPermissions[?FromPort==`0` && ToPort==`65535`]]'
```

---

## Security Groups vs Network ACLs

### Comparación Rápida

| **Característica** | **Security Groups** | **Network ACLs** |
| --- | --- | --- |
| **Nivel** | Instancia (ENI) | Subnet |
| **Estado** | Stateful | Stateless |
| **Reglas** | Solo ALLOW | ALLOW y DENY |
| **Orden** | Sin orden | Evaluadas en orden |
| **Aplicación** | Selectiva | Todas las instancias de la subnet |
| **Por defecto** | Deny inbound/ Allow outbound | Allow todo |

### Cuándo Usar Cada Uno

**Security Groups (Primera Línea)**

- Control granular por instancia
- Reglas basadas en roles/funciones
- 99% de los casos de uso

**Network ACLs (Segunda Línea)**

- Bloqueo de rangos IP maliciosos
- Cumplimiento regulatorio
- Defensa en profundidad adicional

---

## Comandos Útiles AWS CLI

### Listar Security Groups

```bash
# Todos los SG en la región actual
aws ec2 describe-security-groups

# SG por ID
aws ec2 describe-security-groups --group-ids sg-0123456789

# SG por nombre
aws ec2 describe-security-groups --filters "Name=group-name,Values=prod-web-sg"

# Formato tabla
aws ec2 describe-security-groups \
    --query 'SecurityGroups[*].[GroupId,GroupName,Description]' \
    --output table
```

### Crear Security Group

```bash
# Crear SG básico
aws ec2 create-security-group \
    --group-name mi-web-sg \
    --description "Security group para servidores web" \
    --vpc-id vpc-0123456789

# Con tags
aws ec2 create-security-group \
    --group-name mi-web-sg \
    --description "Web servers" \
    --vpc-id vpc-0123456789 \
    --tag-specifications 'ResourceType=security-group,Tags=[{Key=Name,Value=prod-web-sg},{Key=Environment,Value=production}]'
```

### Agregar Reglas

```bash
# Agregar regla SSH
aws ec2 authorize-security-group-ingress \
    --group-id sg-0123456789 \
    --protocol tcp \
    --port 22 \
    --cidr 203.0.113.25/32

# Agregar regla HTTP desde anywhere
aws ec2 authorize-security-group-ingress \
    --group-id sg-0123456789 \
    --protocol tcp \
    --port 80 \
    --cidr 0.0.0.0/0

# Agregar regla desde otro SG
aws ec2 authorize-security-group-ingress \
    --group-id sg-0123456789 \
    --protocol tcp \
    --port 5432 \
    --source-group sg-app-tier-12345
```

### Eliminar Reglas

```bash
# Remover regla específica
aws ec2 revoke-security-group-ingress \
    --group-id sg-0123456789 \
    --protocol tcp \
    --port 22 \
    --cidr 0.0.0.0/0
```

### Ver Instancias por Security Group

```bash
# Qué instancias usan este SG
aws ec2 describe-instances \
    --filters "Name=instance.group-id,Values=sg-0123456789" \
    --query 'Reservations[*].Instances[*].[InstanceId,State.Name,PublicIpAddress]' \
    --output table
```

### Multi-Región

```bash
# Listar SGs en diferentes regiones
for region in us-east-1 us-west-2 eu-west-1; do
    echo "=== Region: $region ==="
    aws ec2 describe-security-groups \
        --region $region \
        --query 'SecurityGroups[*].[GroupId,GroupName]' \
        --output table
done
```

---

## SSH Key-Pairs

### ¿Qué son los Key-Pairs?

Los **key-pairs** son pares de claves criptográficas (pública y privada) utilizadas para autenticación SSH en instancias EC2 Linux.

### Componentes

- **Clave pública**: AWS la almacena y la coloca en tu instancia EC2
- **Clave privada**: Tú la descargas y guardas (archivo `.pem`)
- **Solo puedes descargar la clave privada UNA vez** al crearla

### Características Importantes

### Alcance Regional

- Los key-pairs son **específicos de cada región**
- Si creas instancias en `us-east-1` y `eu-west-1`, necesitas key-pairs en ambas regiones
- No puedes usar el mismo key-pair entre regiones (a menos que lo importes manualmente)

### Formato del Archivo

```bash
# Nombre típico
my-keypair.pem

# Contenido (clave privada)
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAx7g...
...
-----END RSA PRIVATE KEY-----
```

### Creación de Key-Pairs

### Opción 1: Crear en AWS Console

1. Ve a EC2 Dashboard
2. En el menú lateral: **Network & Security** → **Key Pairs**
3. Click **Create key pair**
4. Nombre: `mi-keypair-region`
5. Formato: `.pem` (Linux/Mac) o `.ppk` (Windows/PuTTY)
6. Descarga y guarda en lugar seguro

### Opción 2: Crear vía AWS CLI

```bash
# Crear key-pair y guardar la clave privada
aws ec2 create-key-pair \
    --key-name mi-keypair \
    --query 'KeyMaterial' \
    --output text > mi-keypair.pem

# Establecer permisos correctos
chmod 400 mi-keypair.pem
```

### Opción 3: Importar Key-Pair Existente

```bash
# Si ya tienes un par de claves SSH
aws ec2 import-key-pair \
    --key-name mi-keypair-existente \
    --public-key-material fileb://~/.ssh/id_rsa.pub
```

### Uso del Key-Pair

### Conectarse a una Instancia EC2

```bash
# Sintaxis básica
ssh -i /ruta/a/mi-keypair.pem ec2-user@<IP-PUBLICA>

# Ejemplos por distribución
# Amazon Linux / Amazon Linux 2
ssh -i mi-keypair.pem ec2-user@54.123.45.67

# Ubuntu
ssh -i mi-keypair.pem ubuntu@54.123.45.67

# RHEL
ssh -i mi-keypair.pem ec2-user@54.123.45.67

# SUSE
ssh -i mi-keypair.pem ec2-user@54.123.45.67
```

### Gestión Multi-Región de Key-Pairs

### Estrategia de Nomenclatura

```bash
# Incluir región en el nombre
company-ec2-us-east-1.pem
company-ec2-eu-west-1.pem
company-ec2-ap-southeast-1.pem
```

### Organización Recomendada

```bash
~/.ssh/
├── aws-keys/
│   ├── us-east-1/
│   │   └── prod-keypair.pem
│   ├── us-west-2/
│   │   └── prod-keypair.pem
│   └── eu-west-1/
│       └── prod-keypair.pem
└── config
```

### SSH Config para Múltiples Regiones

```bash
# ~/.ssh/config

# US East
Host ec2-us-east
    HostName 54.123.45.67
    User ec2-user
    IdentityFile ~/.ssh/aws-keys/us-east-1/prod-keypair.pem
    
# EU West
Host ec2-eu-west
    HostName 34.567.89.12
    User ec2-user
    IdentityFile ~/.ssh/aws-keys/eu-west-1/prod-keypair.pem
```

### Seguridad de Key-Pairs

### Permisos Correctos

```bash
# La clave privada debe tener permisos restrictivos
chmod 400 mi-keypair.pem

# Si no lo haces, SSH rechazará la conexión
# Error: "Permissions 0644 for 'key.pem' are too open"
```

### Mejores Prácticas

1. **Nunca compartas** tu clave privada
2. **Nunca subas** claves privadas a Git/repositorios
3. **Usa claves diferentes** para prod/dev/staging
4. **Rota claves regularmente** (cada 90-180 días)
5. **Respalda las claves** en un lugar seguro (bóveda de contraseñas)
6. **Usa bastion hosts** para acceso a instancias privadas
7. **Considera AWS Systems Manager Session Manager** como alternativa sin SSH

### Rotación de Key-Pairs

```bash
# 1. Crear nuevo key-pair
aws ec2 create-key-pair --key-name new-keypair \
    --query 'KeyMaterial' --output text > new-keypair.pem

# 2. Agregar nueva clave pública a instancias existentes
# (conectarte con el key antiguo y agregar el nuevo)
cat new-keypair.pub >> ~/.ssh/authorized_keys

# 3. Probar conexión con nueva clave
ssh -i new-keypair.pem ec2-user@IP

# 4. Una vez confirmado, eliminar clave antigua de AWS
aws ec2 delete-key-pair --key-name old-keypair
```

---

## Troubleshooting Común

### Problema 1: No puedo conectarme por SSH

```bash
# Verificar Security Group permite SSH desde tu IP
aws ec2 describe-security-groups --group-ids sg-xxx \
    --query 'SecurityGroups[*].IpPermissions[?FromPort==`22`]'

# Verificar instancia está corriendo
aws ec2 describe-instances --instance-ids i-xxx \
    --query 'Reservations[*].Instances[*].State.Name'

# Verificar permisos del key-pair
ls -la mi-keypair.pem
# Debe mostrar: -r-------- (400)
```

### Problema 2: "Connection timeout"

**Causa común**: Security Group no permite SSH desde tu IP

**Solución**:

```bash
# Agregar tu IP actual al SG
MI_IP=$(curl -s https://checkip.amazonaws.com)
aws ec2 authorize-security-group-ingress \
    --group-id sg-0123456789 \
    --protocol tcp \
    --port 22 \
    --cidr ${MI_IP}/32
```

### Problema 3: Security Group en región incorrecta

```bash
# Verificar en qué región está el SG
aws ec2 describe-security-groups \
    --group-ids sg-0123456789 \
    --region us-east-1

# Si falla, prueba otras regiones
aws ec2 describe-security-groups \
    --group-ids sg-0123456789 \
    --region eu-west-1
```

---

## Recursos de Referencia

### Documentación Oficial

- [AWS EC2 User Guide](https://docs.aws.amazon.com/ec2/)
- [Security Groups Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)
- [AWS Regions & AZs](https://aws.amazon.com/about-aws/global-infrastructure/)

### Comando de Ayuda Rápida

```bash
# Ver regiones disponibles
aws ec2 describe-regions --output table

# Ver AZs en región actual
aws ec2 describe-availability-zones --output table

# Ver todos tus Security Groups
aws ec2 describe-security-groups --output table
```