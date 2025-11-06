### User Group Keys for each user

Para agregar una key a cada usuario en cuestión:

1. Click sobre el usuario
2. Ir a la pestaña “Security credentials”
3. Ir a la sección de “Access Keys”
4. “Create access key”

Solo se pueden tener dos claves activas para cada usuario.

AWS Automation Practice - Admin DevOps Console

```bash
# Crea access keys para cada usuario
   aws configure --profile admin
   aws configure --profile developer
   aws configure --profile readonly
```

Creating Policies at the CLI

```bash
aws iam create-policy --policy-name CLIAdminPolicy --policy-document file:///Users/mithologic/repos/mydevpath-playground/aws-devops/policies/devops-group/devops-admin-policy.json --description "Full access to EC2, S3, RDS, CloudWatch, and ELB - created via CLI"
```

```bash
aws iam create-policy --policy-name CLIDeveloperPolicy --policy-document file:///Users/mithologic/repos/mydevpath-playground/aws-devops/policies/devops-group/devops-developer-policy.json --description "Full access to EC2, S3, RDS, CloudWatch, and ELB - created via CLI"
```

```bash
aws iam create-policy --policy-name CLIReadOnlyPolicy --policy-document file:///Users/mithologic/repos/mydevpath-playground/aws-devops/policies/devops-group/devops-readonly-policy.json --description "Full access to EC2, S3, RDS, CloudWatch, and ELB - created via CLI"
```

TODO: Translate notes, complement them and push into github