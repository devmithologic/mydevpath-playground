# Plan Certificación AWS + DevOps Integration - 10 Semanas

## Estructura del Plan

### **Calendario:** Solo Lunes a Viernes | Sábados y Domingos: DESCANSO

### **FASE 1: Semanas 1-6 - AWS Solutions Architect Associate (SAA-C03)**
- **Duración:** 6 semanas (30 días hábiles)
- **Carga diaria:** 3-4 horas AWS + DSA ligero
- **Total horas AWS:** ~90-120 horas
- **Objetivo:** Certificarse en AWS SAA-C03
- **Examen programado:** Finales de Semana 6 o principios de Semana 7

### **FASE 2: Semanas 7-10 - Docker, Kubernetes, CI/CD (todo integrado con AWS)**
- **Duración:** 4 semanas (20 días hábiles)
- **Carga diaria:** 3-4 horas DevOps
- **DSA:** 2 horas/semana (2 sesiones de 1 hora)
- **Objetivo:** Portfolio completo de proyectos DevOps + AWS

---

## Recursos Principales para AWS SAA-C03

**Curso principal:**
- Stephane Maarek - Ultimate AWS Certified Solutions Architect Associate (Udemy)

**Practice Exams:**
- Tutorials Dojo (Jon Bonso) - 6 practice exams completos

**Hands-on:**
- AWS Free Tier para practicar
- AWS Skill Builder labs

**Documentación:**
- AWS Whitepapers (Well-Architected Framework)
- AWS FAQs de servicios clave

---

## FASE 1: CERTIFICACIÓN AWS (Semanas 1-6)

### Dominios del Examen SAA-C03:
1. Design Secure Architectures (30%)
2. Design Resilient Architectures (26%)
3. Design High-Performing Architectures (24%)
4. Design Cost-Optimized Architectures (20%)

---

### SEMANA 1: IAM, EC2, Storage Fundamentals

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 1 | Lunes | AWS Overview e IAM | AWS | Global Infrastructure, Regiones, AZs, IAM (users, groups, policies, roles, MFA) | 180 | AWS SAA Domain 1: Security |
| 1 | Martes | EC2 Fundamentals | AWS | Instance types, AMI, User Data, Security Groups, Key Pairs, EC2 pricing models | 180 | AWS SAA Domain 2 & 3 |
| 1 | Martes | DSA - Arrays: Two Pointers | DSA | Mantenimiento: 2 problemas - Two Sum II, Remove Duplicates | 60 | Mantener habilidades básicas |
| 1 | Miércoles | EC2 Storage: EBS | AWS | EBS volumes, snapshots, volume types (gp2, gp3, io1, io2), encryption, lifecycle | 180 | AWS SAA Domain 2 & 3 |
| 1 | Jueves | EC2 Advanced: EFS e Instance Store | AWS | EFS (regional storage), Instance Store (ephemeral), comparación EBS vs EFS vs S3 | 180 | AWS SAA Domain 2 |
| 1 | Viernes | Load Balancers | AWS | ELB types (ALB, NLB, CLB, GWLB), target groups, health checks, sticky sessions | 180 | AWS SAA Domain 2 & 3 |

**Total Semana 1:** ~16 horas (3.2h/día promedio)

---

### SEMANA 2: Auto Scaling, S3, Databases

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 2 | Lunes | Auto Scaling Groups | AWS | ASG, launch templates, scaling policies (target tracking, step, simple), lifecycle hooks | 180 | AWS SAA Domain 2 |
| 2 | Martes | S3 Deep Dive Part 1 | AWS | Buckets, objects, versioning, replication (same-region, cross-region), encryption | 180 | AWS SAA Domain 1 & 4 |
| 2 | Martes | DSA - Sliding Window | DSA | Mantenimiento: 2 problemas - Max Subarray, Longest Substring No Repeat | 60 | Mantener habilidades básicas |
| 2 | Miércoles | S3 Deep Dive Part 2 | AWS | Storage classes (S3 Standard, IA, One Zone, Glacier), lifecycle policies, S3 Select | 180 | AWS SAA Domain 4: Cost |
| 2 | Jueves | RDS y Aurora | AWS | RDS engines, Multi-AZ, Read Replicas, Aurora (MySQL/PostgreSQL), Aurora Serverless | 180 | AWS SAA Domain 2 & 3 |
| 2 | Viernes | DynamoDB | AWS | Tables, items, partition keys, sort keys, indexes (GSI, LSI), DynamoDB Streams, DAX | 180 | AWS SAA Domain 3 |

**Total Semana 2:** ~16 horas

---

### SEMANA 3: VPC Networking, Security, DNS

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 3 | Lunes | VPC Fundamentals | AWS | VPC, Subnets (public/private), Route Tables, Internet Gateway, NAT Gateway vs NAT Instance | 210 | AWS SAA Domain 1 & 2 |
| 3 | Martes | VPC Advanced Connectivity | AWS | VPC Peering, VPC Endpoints (Gateway, Interface), PrivateLink, Transit Gateway | 180 | AWS SAA Domain 1 & 3 |
| 3 | Martes | DSA - Hash Maps | DSA | Mantenimiento: 2 problemas - Two Sum, Group Anagrams | 60 | Mantener habilidades básicas |
| 3 | Miércoles | Network Security | AWS | Security Groups vs NACLs, VPN (Site-to-Site, Client VPN), Direct Connect | 180 | AWS SAA Domain 1 |
| 3 | Jueves | Security Services | AWS | WAF, Shield (Standard, Advanced), GuardDuty, Inspector, Macie, Secrets Manager, KMS | 210 | AWS SAA Domain 1: Security |
| 3 | Viernes | Route 53 y CloudFront | AWS | DNS records, routing policies (simple, weighted, latency, failover), health checks, CloudFront distributions, OAI/OAC | 180 | AWS SAA Domain 2 & 3 |

**Total Semana 3:** ~17 horas

---

### SEMANA 4: Serverless, Integration, Container Services

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 4 | Lunes | Lambda y Serverless | AWS | Lambda functions, triggers, layers, versions/aliases, Lambda@Edge, SAM | 210 | AWS SAA Domain 3 & 4 |
| 4 | Martes | API Gateway y Step Functions | AWS | API Gateway (REST, HTTP, WebSocket), integrations, Step Functions (state machines) | 180 | AWS SAA Domain 3 |
| 4 | Martes | DSA - Linked Lists | DSA | Mantenimiento: 2 problemas - Reverse List, Merge Two Sorted Lists | 60 | Mantener habilidades básicas |
| 4 | Miércoles | SQS, SNS, Kinesis | AWS | SQS (standard, FIFO), SNS (topics, subscriptions), Kinesis Data Streams, Firehose | 210 | AWS SAA Domain 2 & 3 |
| 4 | Jueves | EventBridge y Messaging | AWS | EventBridge (rules, event buses), Amazon MQ, decoupling patterns | 180 | AWS SAA Domain 2 |
| 4 | Viernes | Container Services | AWS | ECS (EC2 vs Fargate), ECR, EKS basics, App Runner, comparaciones | 180 | AWS SAA Domain 3 |

**Total Semana 4:** ~17 horas

---

### SEMANA 5: Analytics, Migration, Monitoring, DR

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 5 | Lunes | Data Analytics | AWS | Athena, Redshift, EMR, Glue, QuickSight, Lake Formation, OpenSearch | 210 | AWS SAA Domain 3 |
| 5 | Martes | Migration Services | AWS | DMS, Snow Family (Snowcone, Snowball, Snowmobile), DataSync, Transfer Family, Application Migration Service | 180 | AWS SAA Domain 2 |
| 5 | Martes | DSA - Binary Search | DSA | Mantenimiento: 2 problemas - Binary Search, Search Rotated Array | 60 | Mantener habilidades básicas |
| 5 | Miércoles | Monitoring y Management | AWS | CloudWatch (metrics, logs, alarms, dashboards), CloudTrail, Config, Systems Manager, Trusted Advisor | 210 | AWS SAA Domain 1 & 2 |
| 5 | Jueves | Disaster Recovery | AWS | Backup strategies, RPO/RTO, Backup/Restore, Pilot Light, Warm Standby, Multi-Site active-active | 180 | AWS SAA Domain 2 |
| 5 | Viernes | Practice Exam 1 + Review | AWS | Tomar Practice Exam #1 completo (130 min), revisar todas las respuestas (120 min) | 240 | Assessment y gap analysis |

**Total Semana 5:** ~18 horas

---

### SEMANA 6: Cost Optimization, Well-Architected, Practice Exams Final

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 6 | Lunes | Cost Optimization | AWS | Reserved Instances, Savings Plans, Spot Instances, Cost Explorer, Budgets, Cost Allocation Tags, Compute Optimizer, rightsizing | 210 | AWS SAA Domain 4: Cost |
| 6 | Martes | Well-Architected Framework | AWS | 6 Pillars: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability | 180 | AWS SAA Todos los dominios |
| 6 | Martes | DSA - Stacks básicos | DSA | Mantenimiento: 2 problemas - Valid Parentheses, Min Stack | 60 | Mantener habilidades básicas |
| 6 | Miércoles | Practice Exam 2 + Review | AWS | Tomar Practice Exam #2 (130 min), revisar respuestas incorrectas exhaustivamente (120 min) | 240 | Assessment - target >70% |
| 6 | Jueves | Weak Areas Review | AWS | Repasar servicios donde fallaste en practice exams, cheatsheets de comparaciones | 210 | Remediation personalizada |
| 6 | Viernes | Practice Exam 3 + Final Review | AWS | Practice Exam #3 (130 min), review (90 min), flashcards de servicios clave (60 min) | 240 | Final prep - target >75% |

**Total Semana 6:** ~18 horas

**🎯 Programar examen oficial AWS SAA-C03:** Lunes o Martes de Semana 7

---

## FASE 2: DOCKER, KUBERNETES, CI/CD + AWS (Semanas 7-10)

### Objetivo de esta fase:

Ahora que eres **AWS Certified Solutions Architect**, vas a dominar containerización y orquestación usando servicios nativos de AWS. Esta combinación (AWS + Docker/K8s) te hace extremadamente valioso para employers.

**Proyectos de esta fase:**
1. **Proyecto 1:** App multi-container con Docker Compose + ECR
2. **Proyecto 2:** Deploy automático en ECS Fargate con CI/CD (CodePipeline)
3. **Proyecto 3:** Cluster EKS completo con aplicación full-stack
4. **Proyecto 4 (Final):** Aplicación production-ready con EKS, RDS Aurora, S3, CloudFront, ALB, todo provisionado con Terraform

---

### SEMANA 7: Docker Fundamentals + AWS ECR/ECS

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 7 | Lunes | 🎉 EXAMEN AWS SAA-C03 | AWS | Tomar examen de certificación oficial | 150 | ¡Certificación AWS! |
| 7 | Lunes (tarde) | Docker - Introducción | DevOps | Qué es Docker, instalación, primeros contenedores (docker run, exec, ps, logs) | 120 | Fundamentos de containerización |
| 7 | Martes | Docker - Images y Dockerfiles | DevOps | Dockerfile syntax, build, layers, caching, multi-stage builds, .dockerignore, best practices | 180 | Crear images optimizadas |
| 7 | Martes | DSA - Binary Trees básico | DSA | 2 problemas: Max Depth Binary Tree, Invert Binary Tree | 60 | Retomar DSA activo |
| 7 | Miércoles | Docker - Volumes y Networks | DevOps | Volumes (named, anonymous, bind mounts), networks (bridge, host, overlay), docker-compose basics | 180 | Persistencia y conectividad |
| 7 | Jueves | Docker Compose - Multi-container apps | DevOps | docker-compose.yml syntax, services, networks, volumes, environment variables, depends_on | 180 | Orquestar aplicaciones localmente |
| 7 | Jueves | DSA - Binary Search Trees | DSA | 2 problemas: Validate BST, Lowest Common Ancestor BST | 60 | Árboles de búsqueda |
| 7 | Viernes | AWS ECR + Push Images | DevOps | Crear repos ECR, docker login, tag, push, image scanning, lifecycle policies | 120 | Integración Docker + AWS |
| 7 | Viernes | Proyecto 1 inicio | Proyecto | Dockerizar app personal (ej: API + DB) y subir a ECR | 120 | Portfolio: App containerizada |

**Total Semana 7:** ~17 horas

---

### SEMANA 8: AWS ECS, Fargate, CI/CD Pipeline

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 8 | Lunes | AWS ECS - Task Definitions | DevOps | ECS clusters, task definitions, container definitions, task roles vs execution roles | 180 | Orquestación serverless AWS |
| 8 | Martes | AWS ECS - Services y Fargate | DevOps | ECS services, Fargate launch type, ALB integration, service discovery, auto-scaling | 180 | Orquestación serverless AWS |
| 8 | Martes | DSA - Graphs: DFS | DSA | 2 problemas: Number of Islands, Clone Graph | 60 | Grafos y traversal |
| 8 | Miércoles | AWS CodePipeline - CI/CD intro | DevOps | CodeCommit, CodeBuild, CodeDeploy, CodePipeline stages, artifacts | 180 | CI/CD nativo AWS |
| 8 | Jueves | GitHub Actions con AWS | DevOps | GitHub Actions workflows, OIDC con AWS, deploy a ECS desde GitHub | 180 | CI/CD moderno |
| 8 | Jueves | DSA - Graphs: BFS | DSA | 2 problemas: Word Ladder, Course Schedule | 60 | Grafos BFS y topological sort |
| 8 | Viernes | Proyecto 2 completo | Proyecto | Deploy app en ECS Fargate con CI/CD completo (GitHub → Build → ECR → ECS) | 240 | Portfolio: Serverless containers |

**Total Semana 8:** ~18 horas

---

### SEMANA 9: Kubernetes + AWS EKS

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 9 | Lunes | Kubernetes - Arquitectura | DevOps | K8s architecture (control plane, nodes), pods, kubectl, namespaces, labels, selectors | 180 | Fundamentos de Kubernetes |
| 9 | Martes | Kubernetes - Deployments y Services | DevOps | Deployments, ReplicaSets, rolling updates, Services (ClusterIP, NodePort, LoadBalancer) | 180 | Fundamentos de Kubernetes |
| 9 | Martes | DSA - Dynamic Programming intro | DSA | 2 problemas: Climbing Stairs, House Robber | 60 | DP básico |
| 9 | Miércoles | Kubernetes - ConfigMaps y Secrets | DevOps | ConfigMaps, Secrets, environment variables, volume mounts, best practices | 180 | Configuration management K8s |
| 9 | Jueves | AWS EKS - Cluster Setup | DevOps | eksctl, EKS cluster creation, node groups, IAM roles for service accounts (IRSA), add-ons | 180 | Kubernetes managed en AWS |
| 9 | Jueves | DSA - Review patrones | DSA | 3 problemas mixtos: repasar Two Pointers, Hash Maps, Binary Search | 90 | Consolidación DSA |
| 9 | Viernes | Kubernetes - Persistent Storage | DevOps | PersistentVolumes, PersistentVolumeClaims, StorageClasses, EBS CSI driver en EKS | 180 | Storage en Kubernetes |

**Total Semana 9:** ~17 horas

---

### SEMANA 10: EKS Avanzado, Terraform, Proyecto Final

| Semana | Día | Título | Tipo | Tema | Duración (min) | Objetivo Relacionado |
|--------|-----|--------|------|------|----------------|---------------------|
| 10 | Lunes | Helm - Package Manager | DevOps | Helm charts, values, templates, dependencies, Helm repositories | 180 | Package management K8s |
| 10 | Martes | Terraform - IaC Fundamentals | DevOps | HCL syntax, providers, resources, state, variables, outputs, modules | 180 | Infrastructure as Code |
| 10 | Martes | Job Search - CV y LinkedIn | Job Search | Actualizar CV con certificación AWS, optimizar LinkedIn, comenzar aplicaciones | 90 | Búsqueda activa de empleo |
| 10 | Miércoles | Terraform con AWS - EKS | DevOps | Provisionar EKS cluster completo con Terraform, VPC, subnets, node groups | 180 | IaC para Kubernetes en AWS |
| 10 | Jueves | Monitoring - Prometheus y Grafana | DevOps | Prometheus en K8s, Grafana dashboards, métricas de aplicación y cluster | 180 | Observability |
| 10 | Viernes | PROYECTO FINAL - Parte 1 | Proyecto | Diseñar y comenzar: App full-stack en EKS con Terraform (infra), Helm (app), CI/CD | 240 | Portfolio showcase |
| 10 | Viernes (extra opcional) | PROYECTO FINAL - Parte 2 | Proyecto | Completar: RDS Aurora, S3 para assets, CloudFront, ALB, todo IaC, demo funcional | 180 | Portfolio showcase completo |

**Total Semana 10:** ~17-20 horas (con proyecto final extra opcional)

---

## Sistema de Tracking y Métricas

### Métricas semanales a trackear en Notion:

**Semanas 1-6 (AWS):**
- Horas estudiadas AWS: __ / 16-18 horas target
- Temas completados: __ / __ 
- Practice exam scores (semanas 5-6): __%
- DSA problems solved: 2/semana

**Semanas 7-10 (DevOps):**
- Horas DevOps: __ / 17-18 horas target
- Proyectos completados: __ / 4
- DSA problems solved: 4-6/semana
- Job applications sent: __ (target: 3-5/semana desde semana 10)

---

## Recursos Adicionales Recomendados

### Para AWS:
- **Udemy:** Stephane Maarek - AWS SAA
- **Practice:** Tutorials Dojo (Jon Bonso)
- **Docs:** AWS Whitepapers, FAQs
- **Hands-on:** AWS Free Tier

### Para Docker/Kubernetes:
- **Docs:** Docker oficial, Kubernetes oficial
- **Cursos:** KodeKloud (Mumshad Mannambeth)
- **Practice:** Play with Docker, Play with Kubernetes

### Para DSA:
- **Platform:** LeetCode, NeetCode
- **Patterns:** NeetCode 150, Grind 75

### Para Terraform:
- **Docs:** Terraform oficial
- **Curso:** HashiCorp Learn

---

## Estrategia de Examen AWS SAA-C03

### Semana antes del examen (Semana 6):

**Lunes-Martes:**
- Review de servicios clave
- Cheatsheets y comparaciones

**Miércoles:**
- Practice Exam #2 (simular condiciones reales)

**Jueves:**
- Estudiar solo weak areas del practice exam

**Viernes:**
- Practice Exam #3
- Flashcards

**Sábado-Domingo:**
- DESCANSO (muy importante antes del examen)

**Lunes Semana 7:**
- ¡EXAMEN!

### Tips para el examen:
- Dormir bien la noche anterior
- Llegar 30 min antes (o preparar espacio si es online)
- Leer cada pregunta DOS veces
- Marcar preguntas difíciles para revisar al final
- Time management: ~2 min por pregunta (65 preguntas en 130 min)

---

## Plan de Job Search (Semanas 7-10)

### Semana 7:
- Actualizar CV con "AWS Certified Solutions Architect Associate"
- Optimizar LinkedIn con certificación

### Semana 8-9:
- Identificar 20 empresas target
- Networking en LinkedIn
- Comenzar a aplicar (2-3 aplicaciones/semana)

### Semana 10:
- Aplicaciones intensivas (5+ por semana)
- Preparación de entrevistas (behavioral STAR method)
- Tener portfolio listo para mostrar

---

## Checklist de Éxito - 10 Semanas

Al final de este plan deberías tener:

### Certificaciones:
- ✅ AWS Certified Solutions Architect Associate (SAA-C03)

### Habilidades Técnicas:
- ✅ AWS: ~30 servicios dominados, arquitecturas multi-tier
- ✅ Docker: Containerización, multi-stage builds, docker-compose
- ✅ Kubernetes: Pods, Deployments, Services, Storage, Helm
- ✅ ECS/EKS: Orquestación de containers en AWS
- ✅ CI/CD: Pipelines automáticos con GitHub Actions / CodePipeline
- ✅ IaC: Terraform para provisionar infraestructura
- ✅ Monitoring: Prometheus + Grafana

### Portfolio:
- ✅ 4 proyectos prácticos demostrables
- ✅ GitHub profile completo con READMEs detallados
- ✅ Proyecto final showcase (full-stack en AWS)

### DSA:
- ✅ ~50 problemas resueltos
- ✅ Patrones principales dominados (Arrays, Linked Lists, Trees, Graphs, DP intro)

### Job Search:
- ✅ CV optimizado con certificación
- ✅ LinkedIn destacado
- ✅ 15-20 aplicaciones enviadas
- ✅ Pipeline activo de oportunidades

---

## Notas Finales

### Flexibilidad:
- Si un tema requiere más tiempo, tómalo del siguiente día
- Si te enfermas o surge algo urgente, no te estreses, ajusta el calendario
- El objetivo es **aprender bien**, no solo completar el checklist

### Consistencia:
- Estudiar 3-4 horas diarias de lunes a viernes es sostenible
- Fines de semana libres te permite recuperar energía
- 10 semanas pasan rápido con disciplina

### Comunidad:
- Únete a subreddits: r/AWSCertifications, r/devops
- Comparte tu progreso en LinkedIn
- Busca study groups

### Motivación:
- Recuerda tu "por qué": Conseguir mejor posición DevOps/SRE
- Celebra pequeños wins (completar semana, pasar practice exam, certificarte)
- El esfuerzo de 10 semanas puede cambiar tu carrera para siempre

**¡Éxito en tu journey Alejandro! 🚀**