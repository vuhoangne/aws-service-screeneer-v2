---
title : "Integration with AWS Well-Architected Tool"
date : "2024-01-01" 
weight : 7 
chapter : false
pre : " <b> 7. </b> "
---
#### 7.1. Enable Well-Architected Integration
{{%expand "Create a workload in AWS Well-Architected Tool:" %}}![Create a workload in AWS Well-Architected Tool:](/images/7/1.png){{% /expand%}}
```bash
screener --regions us-east-1 --beta 1 --others '{"WA": {"region": "us-east-1", "reportName": "MyWorkload_ServiceScreener", "newMileStone": 1}}'
```

**Parameters Explained:**
- `region`: Where to create the Well-Architected workload
- `reportName`: Name of your workload
- `newMileStone`:  
    - Set to 1 to create new milestone each run
    - Set to 0 to create a milestone only if none exists

#### 7.2. Migration Planning Evaluation
For AWS Partners conducting migration evaluations:

```bash
screener --regions us-east-1 --others '{"mpe": {"id": "migration-eval-001"}}'
```

#### 7.3. View Well-Architected Integration
1. {{%expand "Navigate to AWS Well-Architected Tool in the AWS Console" %}}![Navigate to AWS Well-Architected Tool in the AWS Console](/images/7/2.png){{% /expand%}}
2. {{%expand "Find your workload (named as specified in `reportName`)" %}}![Find your workload (named as specified in `reportName`)](/images/7/3.png){{% /expand%}}
3. {{%expand "Review the milestone created by Service Screener" %}}![Review the milestone created by Service Screener](/images/7/4.png){{% /expand%}}
4. Combining Parameters
You can combine both MPE and WA parameters:
{{%expand "Output after combine" %}}![Output](/images/7/5.png){{% /expand%}}
```bash
screener --regions us-east-1 --others '{"WA": {"region": "us-east-1", "reportName": "SS_Report", "newMileStone": 1}, "mpe": {"id": "migration-eval-001"}}'
```
---