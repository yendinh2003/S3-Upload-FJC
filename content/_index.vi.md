---
title : "Session Management"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---

# Tải ảnh lên Amazon S3 bằng Amazon Lambda và API Gateway

### Tổng quan

 - Tải ảnh lên Amazon S3 bằng AWS Lambda và API Gateway là một giải pháp phổ biến trong các ứng dụng web hiện đại nhằm xử lý ảnh không cần máy chủ (serverless).
Trong mô hình này:
- Người dùng gửi ảnh (dạng Base64 hoặc file) qua API Gateway bằng phương thức POST.
- API Gateway chuyển dữ liệu tới AWS Lambda.
- Lambda xử lý dữ liệu ảnh và upload trực tiếp lên Amazon S3 – một dịch vụ lưu trữ đối tượng mạnh mẽ
### Nội dung

 1. [Giới thiệu](1-introduce/)
 2. [Các bước chuẩn bị](2-Prerequiste/)
 3. [Cấu Hình Lambda](3-ConfigLambda/)
 4. [Cấu Hình API Gateway](4-ApitoLambda/)
 5. [Test API trên Postman](5-TestAPI/)
 6. [Dọn dẹp tài nguyên](6-cleanup/)
