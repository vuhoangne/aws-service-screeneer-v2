---
title : "Troubleshooting and Best Practices"
date : "2024-01-01" 
weight : 8 
chapter : false
pre : " <b> 8. </b> "
---
#### 8.1. Common Issues and Solutions

**Issue: Permission Denied Errors**
```bash
# Check your current AWS identity
aws sts get-caller-identity

# Verify permissions
aws iam get-user
aws iam list-attached-user-policies --user-name YOUR_USERNAME
```

**Issue: Scan Takes Too Long**
- Use service-specific scanning: `--services s3,ec2`
- Limit regions: `--regions us-east-1`
- Use tag filtering to reduce scope

**Issue: Memory or Resource Errors**
- Reduce worker count: `--workerCounts 2`
- Scan fewer services at once
- Use CloudShell in a region with fewer resources

#### 8.2. Best Practices

**Scanning Strategy:**
1. Start with critical services (IAM, S3, EC2)
2. Gradually expand to all services
3. Run regular scans (weekly/monthly)
4. Focus on high-impact findings first

**Report Management:**
1. Store reports securely (never expose publicly)
2. Track remediation progress over time
3. Share findings with relevant teams
4. Document remediation actions taken

**Performance Optimization:**
1. Use tag filtering for large environments
2. Scan during off-peak hours
3. Consider breaking large scans into smaller chunks
4. Monitor CloudShell resource usage

---
