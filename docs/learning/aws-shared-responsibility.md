# AWS Shared Responsibility Model

## Security of the cloud
AWS is responsible for protecting and maintaining the underlying cloud infrastructure (physical facilities, hardware, and networking).

## Security in the cloud
LUMEN is responsible for securely configuring its resources, permissions, applications, and data.

## Implications for LUMEN
- Apply least-privilege IAM permissions (never use the Root account for daily dev).
- Avoid committing credentials to Git.
- Review data storage and access controls before deploying S3 data lakes.
- Consider privacy before processing camera or voice data.
- Monitor resource usage and unexpected costs via AWS Budgets.