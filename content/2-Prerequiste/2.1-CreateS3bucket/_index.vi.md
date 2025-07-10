---
title : "Tạo S3 Bucket để lưu trữ "
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.1 </b> "
---
#### Khởi tạo S3 Bucket dùng để lưu trữ hình ảnh và kết quả

 Truy cập vào Console và tìm dịch vụ Amazon S3
  - Truy cập vào trang [AWS Management Console](https://aws.amazon.com/vi/console/)
  - Tiến hành đăng nhập tài khoản của bạn
  - Sau khi đăng nhập thành công thì sẽ chuyển người dùng đến trang chính của **AWS Manage Console** như hình dưới : 
    ![S3](/images/console.png)
  - Tìm kiếm S3 trên thanh Search và chọn dịch vụ S3
    ![S3](/images/S3-1.png)
  - Chọn Create bucket và làm theo hướng dẫn

 Cấu hình cho S3

  Tại phần **General configuration:**
  - AWS Region: tùy theo Region của bạn muốn sử dụng
  - Bucket type: chọn General purpose
  - Bucket name: nhập fjc-s3bucket

  Tại phần **Object Ownership:**
  - Chọn **ACLs disable (recommended)**
   ![S3](/images/S3-3.png)

   Tại phần **Block Public Access setting for this bucket:**
   - Bỏ chọn **Block all public access**
   - Tích chọn **I acknowledge that the current settings might result in this bucket and the objects within becoming public.**
      ![S3](/images/S3-4.png)

  Giữ nguyên cấu hình mặc định ở phần dưới rồi sau đó chọn Create Bucket
  - Đợi vài giây sau đó bạn sẽ được chuyển đến trang danh sách và hiển thị thông báo tạo thành công như hình dưới:
      ![S3](/images/S3-5.png)