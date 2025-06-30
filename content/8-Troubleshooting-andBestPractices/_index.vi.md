---
title : "Xử lý lỗi và các quy tắc vận hành chuẩn"
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
- Sử dụng quét theo dịch vụ cụ thể: `--services s3,ec2`
- Giới hạn region: `--regions us-east-1`
- Sử dụng lọc tag để giảm phạm vi

**Issue: Memory or Resource Errors**
- Giảm số lượng worker: `--workerCounts 2`
- Quét ít dịch vụ hơn cùng một lúc
- Sử dụng CloudShell trong region có ít tài nguyên hơn

#### 8.2. Best Practices

**Scanning Strategy:**
1. Bắt đầu với các dịch vụ quan trọng (IAM, S3, EC2)
2. Từ từ mở rộng đến tất cả dịch vụ
3. Chạy quét định kỳ (hàng tuần/hàng tháng)
4. Tập trung vào các phát hiện có tác động cao trước

**Report Management:**
1. Lưu trữ báo cáo một cách an toàn (không bao giờ để lộ công khai)
2. Theo dõi tiến trình khắc phục theo thời gian
3. Chia sẻ phát hiện với các team liên quan
4. Ghi chép các hành động khắc phục đã thực hiện

**Performance Optimization:**
1. Sử dụng lọc tag cho môi trường lớn
2. Quét trong giờ thấp điểm
3. Cân nhắc chia các lần quét lớn thành các phần nhỏ hơn
4. Giám sát việc sử dụng tài nguyên CloudShell

---