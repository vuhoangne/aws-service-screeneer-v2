---
title : "Tích hợp với công cụ AWS Well-Architected"
date : "2024-01-01" 
weight : 7 
chapter : false
pre : " <b> 7. </b> "
---
#### 7.1. Enable Well-Architected Integration
{{%expand "Tạo một workload trong AWS Well-Architected Tool:" %}}![Create a workload in AWS Well-Architected Tool:](/images/7/1.png){{% /expand%}}
```bash
screener --regions us-east-1 --beta 1 --others '{"WA": {"region": "us-east-1", "reportName": "MyWorkload_ServiceScreener", "newMileStone": 1}}'
```

**Giải thích các tham số:**
- `region`: Nơi tạo workload Well-Architected
- `reportName`: Tên workload của bạn
- `newMileStone`:  
    - Đặt thành 1 để tạo milestone mới cho mỗi lần chạy
    - Đặt thành 0 để chỉ tạo milestone nếu chưa có

#### 7.2. Migration Planning Evaluation
Dành cho AWS Partner thực hiện đánh giá migration:

```bash
screener --regions us-east-1 --others '{"mpe": {"id": "migration-eval-001"}}'
```

#### 7.3. View Well-Architected Integration
1. {{%expand "Điều hướng đến AWS Well-Architected Tool trong AWS Console" %}}![Navigate to AWS Well-Architected Tool in the AWS Console](/images/7/2.png){{% /expand%}}
2. {{%expand "Tìm workload của bạn (được đặt tên như chỉ định trong `reportName`)" %}}![Find your workload (named as specified in `reportName`)](/images/7/3.png){{% /expand%}}
3. {{%expand "Xem lại milestone được tạo bởi Service Screener" %}}![Review the milestone created by Service Screener](/images/7/4.png){{% /expand%}}
4. Combining Parameters
Bạn có thể kết hợp cả tham số MPE và WA:
{{%expand "Output sau khi kết hợp" %}}![Output](/images/7/5.png){{% /expand%}}
```bash
screener --regions us-east-1 --others '{"WA": {"region": "us-east-1", "reportName": "SS_Report", "newMileStone": 1}, "mpe": {"id": "migration-eval-001"}}'
```
---