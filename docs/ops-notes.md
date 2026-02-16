# Ops Notes (Production Considerations)

## Observability

- CloudWatch metrics and alarms for ALB, EC2, ASG, and RDS
- Centralized logging for web/app tier (CloudWatch Logs)
- ALB access logs to S3 (optional)

## Security

- No public IPs on EC2 instances
- Restrict inbound using security group chaining (ALB → Web → Internal ALB → App → DB)
- Store secrets in Secrets Manager / SSM Parameter Store
- Encrypt data at rest (EBS/RDS) and in transit (TLS)

## Availability

- Multi-AZ across tiers
- Health checks and auto-replacement via ASG + ALB target groups
- RDS Multi-AZ managed failover
