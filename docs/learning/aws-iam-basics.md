# AWS IAM Basics: Learning Log

## IAM Users vs. IAM Roles
- **IAM User:** An identity with long-term credentials used by a person or application to interact with AWS.
- **IAM Role:** An identity with temporary credentials that can be assumed by trusted entities (like an AWS Lambda function or a user). Roles are preferred for service-to-service communication to avoid hardcoding access keys.

## IAM Groups
Groups are collections of IAM users. They allow you to apply the same permissions (like `LumenS3ReadOnlyPolicy`) to multiple users at once, making access management scalable.

## Trust Policy vs. Permissions Policy (Roles)
- **Trust Policy:** Defines *who* or *what* is allowed to assume the role (e.g., allowing `lambda.amazonaws.com` to assume the role).
- **Permissions Policy:** Defines *what* the role is actually allowed to do once assumed (e.g., writing logs to CloudWatch or reading from an S3 bucket).