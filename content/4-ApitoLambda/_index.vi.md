---
title : "Cấu hình API Gateway"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---
🔹 AWS Lambda là gì?
AWS Lambda là một dịch vụ điện toán không máy chủ (serverless) của Amazon Web Services (AWS), cho phép bạn chạy mã (code) mà không cần quản lý máy chủ. Bạn chỉ cần viết function và upload lên, Lambda sẽ tự động thực thi khi được kích hoạt — ví dụ bởi API Gateway, sự kiện từ S3, DynamoDB, v.v.

✅ Không cần quản lý máy chủ

✅ Tự động scale theo lượng request

✅ Tính phí theo thời gian chạy thực tế

🔹 Tại sao phải cấp quyền S3 cho Lambda?
Khi một hàm Lambda cần truy cập đến tài nguyên AWS khác, như đọc/ghi file vào Amazon S3, thì phải có quyền thông qua IAM Role gắn với Lambda.

Lambda không tự động có quyền truy cập S3 – để đảm bảo an toàn bảo mật theo nguyên tắc least privilege (chỉ cấp quyền cần thiết).

👉 Vì vậy, nếu Lambda cần:
- Upload ảnh lên S3 → cần quyền s3:PutObject
- Tải ảnh từ S3 → cần s3:GetObject
- Xoá ảnh → cần s3:DeleteObject

✅ Tóm lại:
Lambda giúp triển khai code linh hoạt, nhanh chóng và tiết kiệm chi phí.
Phải cấp quyền rõ ràng để Lambda truy cập S3 — giúp kiểm soát chặt chẽ tài nguyên, tránh rủi ro bảo mật.


Vậy trong phần này sẽ tìm hiểu về cách cấu hình Lambcho cho phù hợp và cấp quyền S3 cho Lambda

#### Nội Dung
4.1 [Tạo REST API kết nối Lambda](4.1-updateiamrole/)