# Simple Terraform Module

A basic Terraform module that creates an EC2 instance and S3 bucket in AWS.

## Files

- **main.tf** - Core resources (EC2 instance, S3 bucket, and data source for AMI)
- **variables.tf** - Input variables with descriptions
- **outputs.tf** - Output values for instance ID, IP, and bucket details
- **terraform.tfvars** - Example variable values

## Quick Start

1. **Configure AWS credentials:**
   ```bash
   aws configure
   # or set AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY environment variables
   ```

2. **Update terraform.tfvars** with your desired values:
   - Change `bucket_name` to a globally unique name (S3 bucket names must be unique across all AWS accounts)

3. **Initialize Terraform:**
   ```bash
   terraform init
   ```

4. **Review the plan:**
   ```bash
   terraform plan
   ```

5. **Apply the configuration:**
   ```bash
   terraform apply
   ```

6. **Destroy resources (when done):**
   ```bash
   terraform destroy
   ```

## Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `aws_region` | AWS region | us-east-1 |
| `instance_type` | EC2 instance type | t3.micro |
| `instance_name` | Name tag for instance | terraform-instance |
| `bucket_name` | S3 bucket name (required, must be unique) | - |

## Outputs

- `instance_id` - EC2 instance ID
- `instance_public_ip` - Public IP address of the instance
- `s3_bucket_name` - Name of the S3 bucket
- `s3_bucket_arn` - ARN of the S3 bucket
