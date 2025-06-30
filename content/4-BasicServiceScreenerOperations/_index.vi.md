---
title : "Các thao tác cơ bản của bộ phận sàng lọc dịch vụ"
date: "2024-01-01" 
weight : 3 
chapter : false
pre : " <b> 3. </b> "
---
#### 3.1. Your First Scan - Single Region, All Services
{{%expand "Bắt đầu với một lần quét cơ bản cho region hiện tại của bạn:" %}}![Start with a basic scan of your current region:](/images/4/1.png){{% /expand%}}
```bash
# Replace 'us-east-1' with your current region
screener --regions us-east-1
```
 
**Điều gì xảy ra trong quá trình quét này:**
- Service Screener phân tích tất cả các dịch vụ AWS được hỗ trợ trong region được chỉ định
- Nó chạy các lệnh gọi API chỉ đọc để thu thập thông tin cấu hình
- Kiểm tra được thực hiện theo các thực hành tốt nhất của AWS
- Kết quả được biên soạn thành một báo cáo toàn diện

#### 3.2. Monitor Scan Progress
Quá trình quét sẽ hiển thị các chỉ báo tiến độ. Output thông thường bao gồm:
- Giai đoạn khám phá dịch vụ
- Phân tích từng dịch vụ
- Tạo báo cáo
- Tạo file output

#### 3.3. Understanding Scan Duration
Thời gian quét phụ thuộc vào:
- Số lượng tài nguyên trong tài khoản của bạn
- Số lượng region được quét
- Số lượng dịch vụ được phân tích
- Độ trễ mạng

Thời gian quét thông thường:
- Môi trường nhỏ (ít tài nguyên): 2-5 phút
- Môi trường trung bình: 5-15 phút
- Môi trường lớn: 15-30+ phút

---