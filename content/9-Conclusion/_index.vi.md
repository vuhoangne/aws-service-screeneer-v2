---
title : "Kết thúc Workshop"
date : "2024-01-01"
weight : 9
chapter : false
pre : " <b> 9. </b> "
--- 
**##### Những điểm chính**
- **Service Screener là một công cụ mạnh mẽ** để xác định các vi phạm thực hành tốt nhất của AWS
- **Quét thường xuyên** giúp duy trì tư thế bảo mật và tối ưu hóa
- **Ưu tiên là quan trọng** - tập trung vào các phát hiện có tác động cao trước
- **Tích hợp với các quy trình hiện có** tối đa hóa giá trị
- **Cải tiến liên tục** thông qua đánh giá và khắc phục thường xuyên
**##### Tài nguyên bổ sung**
- [Kho GitHub của AWS Service Screener](https://github.com/aws-samples/service-screener-v2)
- [Khung AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/)
- [Thực hành bảo mật tốt nhất của AWS](https://aws.amazon.com/security/security-resources/)
- [Tối ưu hóa chi phí AWS](https://aws.amazon.com/aws-cost-management/)
---
**#### Tham khảo lệnh**
**##### Lệnh cơ bản**
```bash
# Quét đơn giản
screener --regions REGION_NAME
# Quét nhiều vùng
screener --regions REGION1,REGION2,REGION3
# Tất cả vùng
screener --regions ALL
# Dịch vụ cụ thể
screener --regions REGION --services SERVICE1,SERVICE2
# Với tính năng beta
screener --regions REGION --beta 1
# Với lọc tag
screener --regions REGION --tags KEY=VALUE
# Với tích hợp Well-Architected
screener --regions REGION --others '{"WA": {"region": "REGION", "reportName": "NAME", "newMileStone": 1}}'
```
**##### Định danh dịch vụ**
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
**#### Hướng dẫn khắc phục sự cố**
**##### Thông báo lỗi phổ biến và giải pháp**
**Lỗi: "Unable to locate credentials"**
- Giải pháp: Đảm bảo thông tin xác thực AWS được cấu hình trong CloudShell
- Chạy: `aws configure list` để xác minh
**Lỗi: "Access Denied"**
- Giải pháp: Kiểm tra quyền IAM
- Đảm bảo chính sách ReadOnlyAccess được gắn
**Lỗi: "Region not found"**
- Giải pháp: Sử dụng định danh vùng chính xác (ví dụ: us-east-1, không phải US East 1)
**Lỗi: "Service not supported"**
- Giải pháp: Kiểm tra danh sách dịch vụ được hỗ trợ
- Sử dụng định danh dịch vụ chính xác
**##### Mẹo tối ưu hóa hiệu suất**
1. **Giảm phạm vi:**
   - Sử dụng vùng cụ thể thay vì ALL
   - Nhắm vào dịch vụ cụ thể
   - Áp dụng bộ lọc tag
2. **Quản lý tài nguyên:**
   - Giám sát việc sử dụng tài nguyên CloudShell
   - Giảm số lượng worker nếu cần
   - Chia các lần quét lớn thành các phần nhỏ hơn
3. **Tối ưu hóa mạng:**
   - Chạy quét từ các vùng gần tài nguyên của bạn
   - Tránh thời gian sử dụng cao điểm
   - Xem xét giới hạn API theo vùng