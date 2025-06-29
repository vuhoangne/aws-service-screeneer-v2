---
title : "Advanced Scanning Options"
date: "2024-01-01" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### 4.1. Multi-Region Scanning
{{%expand "Scan multiple regions simultaneously:" %}}![Scan multiple regions simultaneously:](/images/5/1.png){{% /expand%}}
```bash
# Scan specific regions
screener --regions us-east-1,us-west-2,eu-west-1

# Scan ALL regions (use with caution)
screener --regions ALL
```

#### 4.2. Service-Specific Scanning
Focus on specific services for faster, targeted analysis:

```bash
# Scan only S3
screener --regions us-east-1 --services s3

# Scan multiple specific services
screener --regions us-east-1 --services s3,ec2,rds,iam

# Scan with beta features enabled
screener --regions us-east-1 --services s3,lambda --beta 1
```

#### 4.3. Tag-Based Filtering
Filter resources based on tags:

```bash
# Filter by environment tag
screener --regions us-east-1 --tags env=prod

# Multiple tag filters
screener --regions us-east-1 --tags env=prod%department=finance,hr

# Complex tag filtering
screener --regions us-east-1 --tags "Environment=Production%CostCenter=IT,Marketing"
```

#### 4.4. Beta Features
Enable beta features for additional checks:

```bash
screener --regions us-east-1 --beta 1
```

---
