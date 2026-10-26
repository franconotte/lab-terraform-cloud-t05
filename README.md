# Lab T05 10-01 — Terraform Cloud + GitHub

Infraestructura de ejemplo (EC2 + Security Groups + data source de AMI) que se despliega
desde **HCP Terraform** con workflow de control de versiones: cada push a este repo
dispara un `plan`, y el `apply` se confirma desde la interfaz de HCP.

## Variables del workspace

En HCP Terraform, **Variables → Environment variables**, marcadas como *sensitive*:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `AWS_SESSION_TOKEN`

Las credenciales del AWS Academy Learner Lab caducan al cerrar la sesión, así que hay que
recargarlas cada vez. Es la misma limitación que en GitHub Actions y en CircleCI.

## Terraform variables

`aws_region`, `instance_type`, `environment` y `business_divsion` tienen valores en
`terraform.auto.tfvars`.
