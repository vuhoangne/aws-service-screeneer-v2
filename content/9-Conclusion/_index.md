---
title : "Workshop Conclusion"
date : "2024-01-01" 
weight : 9 
chapter : false
pre : " <b> 9. </b> "
---

##### Key Takeaways
- **Service Screener is a powerful tool** for identifying AWS best practice violations
- **Regular scanning** helps maintain security and optimization posture
- **Prioritization is crucial** - focus on high-impact findings first
-  **Integration with existing processes** maximizes value
- **Continuous improvement** through regular assessment and remediation

##### Additional Resources
- [AWS Service Screener GitHub Repository](https://github.com/aws-samples/service-screener-v2)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS Security Best Practices](https://aws.amazon.com/security/security-resources/)
- [AWS Cost Optimization](https://aws.amazon.com/aws-cost-management/)
---

#### Command Reference

##### Basic Commands
```bash
# Simple scan
screener --regions REGION_NAME

# Multi-region scan
screener --regions REGION1,REGION2,REGION3

# All regions
screener --regions ALL

# Specific services
screener --regions REGION --services SERVICE1,SERVICE2

# With beta features
screener --regions REGION --beta 1

# With tag filtering
screener --regions REGION --tags KEY=VALUE

# With Well-Architected integration
screener --regions REGION --others '{"WA": {"region": "REGION", "reportName": "NAME", "newMileStone": 1}}'
```

##### Service Identifiers
- `s3` - Amazon S3
- `ec2` - Amazon EC2
- `rds` - Amazon RDS
- `iam` - AWS IAM
- `lambda` - AWS Lambda
- `cloudfront` - Amazon CloudFront
- `eks` - Amazon EKS
- `dynamodb` - Amazon DynamoDB
- `elasticache` - Amazon ElastiCache
- `opensearch` - Amazon OpenSearch
- `apigateway` - Amazon API Gateway
- `cloudtrail` - AWS CloudTrail
- `guardduty` - Amazon GuardDuty
- `kms` - AWS KMS
- `efs` - Amazon EFS
- `redshift` - Amazon Redshift
- `cloudwatch` - Amazon CloudWatch

#### Troubleshooting Guide

##### Common Error Messages and Solutions

**Error: "Unable to locate credentials"**
- Solution: Ensure AWS credentials are configured in CloudShell
- Run: `aws configure list` to verify

**Error: "Access Denied"**
- Solution: Check IAM permissions
- Ensure ReadOnlyAccess policy is attached

**Error: "Region not found"**
- Solution: Use correct region identifiers (e.g., us-east-1, not US East 1)

**Error: "Service not supported"**
- Solution: Check supported services list
- Use correct service identifiers

##### Performance Optimization Tips

1. **Reduce Scope:**
   - Use specific regions instead of ALL
   - Target specific services
   - Apply tag filters

2. **Resource Management:**
   - Monitor CloudShell resource usage
   - Reduce worker count if needed
   - Break large scans into smaller chunks

3. **Network Optimization:**
   - Run scans from regions close to your resources
   - Avoid peak usage times
   - Consider regional API limits


