---
title : "Phân tích dữ liệu và giải thích báo cáo"
date: "2024-01-01" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

#### 5.1. Download and Extract Report
Sau khi quá trình quét hoàn tất:

1. **Tải xuống báo cáo:**
   - {{%expand "Trong CloudShell, click Actions → Download file" %}}![In CloudShell, click "Actions" → "Download file"](/images/6/1.png){{% /expand%}}
   - {{%expand "Nhập đường dẫn: `/tmp/service-screener-v2/output.zip`" %}}![Enter the path: `/tmp/service-screener-v2/output.zip`](/images/6/2.png){{% /expand%}}
   - Click "Download"

2. **Giải nén báo cáo:**
   - Giải nén file đã tải xuống trên máy tính local của bạn
   - {{%expand "Mở `index.html` trong trình duyệt web" %}}![Open `index.html` in your web browser](/images/6/3.png){{% /expand%}}

#### 5.2. Navigate the Report Interface
Báo cáo bao gồm:

   1. **Left Navigation Panel:**
      - Tổng quan Dashboard
      - Các phần theo dịch vụ cụ thể
      - Thống kê tóm tắt

   2. **Main Content Area:**
      - Các phát hiện chi tiết
      - Khuyến nghị theo tài nguyên cụ thể
      - Chỉ báo mức độ nghiêm trọng

   3. **Key Sections:**
      - **Critical**: Các vấn đề cần chú ý ngay lập tức
      - **High**: Khuyến nghị quan trọng
      - **Medium**: Cơ hội tối ưu hóa
      - **Low**: Cải tiến nhỏ

#### 5.3. Understanding Finding Categories

1. {{%expand "Security Findings:" %}}![Security Findings:](/images/6/4.png){{% /expand%}} 
   - Tài nguyên không được mã hóa
   - Chính sách quá lỏng lẻo
   - Thiếu cấu hình bảo mật
   - Vi phạm tuân thủ

2. {{%expand "Cost Optimization:" %}}![Cost Optimization:](/images/6/5.png){{% /expand%}}
   - Tài nguyên sử dụng ít
   - Instance quá lớn
   - Tài nguyên không sử dụng
   - Cơ hội tối ưu hóa lưu trữ

3. {{%expand "Performance" %}}![Performance:](/images/6/6.png){{% /expand%}}
   - Cấu hình không tối ưu
   - Thiếu giám sát
   - Phân bổ tài nguyên không hiệu quả

4. {{%expand "Reliability:" %}}![Reliability:](/images/6/7.png){{% /expand%}}
   - Điểm lỗi đơn lẻ
   - Thiếu backup
   - Khôi phục thảm họa không đầy đủ

5. {{%expand "Operational Excellence:" %}}![Operational Excellence:](/images/6/8.png){{% /expand%}}
   - Thiếu tự động hóa
   - Giám sát không đầy đủ
   - Drift cấu hình

#### 5.4. Prioritizing Recommendations
Sử dụng framework này để ưu tiên các phát hiện:

1. **Critical Security Issues** (Sửa ngay lập tức)
2. **High-Impact Cost Savings** (Chiến thắng nhanh)
3. **Reliability Improvements** (Ngăn ngừa sự cố)
4. **Performance Optimizations** (Trải nghiệm người dùng)
5. **Operational Improvements** (Hiệu quả lâu dài)

---