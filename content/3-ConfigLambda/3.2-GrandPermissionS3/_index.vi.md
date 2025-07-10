---
title : "Cấp quyền S3 cho Lambda"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2. </b> "
---
#### Cấp quyền S3 cho Lambda Function (trong IAM Console) ####

1. Cách 1: Cấp quyền toàn quyền S3 (dễ, nhanh)
- Trong giao diện IAM , tại thanh chức năng bên trái chọn **Role**
- Bạn sẽ thấy **Role** có tên giống function mình vừa tạo
- Tiến hành click vào **Role**
- Kết quả như hình sau : 
![Lambda](/images/17.png)

- Sau khi vào được giao diện của **Role** đó:
- Ở phần **Permissions policies**:
- Ta tiến hành chọn tác vụ **Add permission** sau đó chọn **Attach Policies**
![Lambda](/images/18.png)

Chúng ta sẽ thấy toàn bộ danh sách các **Permissions Policies**
- Trên thanh Seacrch, tiến hành tìm kiếm **AmazonS3FullAccess**
- Chọn policies đó và tiến hành **Add permission**
![lambda](/images/19.png)
📌 Kết quả: Lambda giờ có toàn quyền với tất cả bucket S3

2. Cách 2 : Cấp quyền chỉ upload ảnh vào đúng 1 bucket (an toàn hơn)
- Quay lại với **Role** của function vừa tạo đó 
- Ở phần **Permissions policies**:
- Ta tiến hành chọn tác vụ **Add permission** sau đó chọn **Create inline policy**
![Lambda](/images/20.png)

- Sau khi vào giao diện **Create policy**
- Tại phần **Specify permission** , chúng ta có thể đưa code vào để cấu hình 
- Sau đó nhấn Next
~~~
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "s3:PutObject"
      ],
      "Resource": "arn:aws:s3:::fjc-s3bucket/"
    }
  ]
}
~~~
![Lambda](/images/21.png)

- Tiếp theo đến giao diện **Review and create**
- Policy name : LambdaS3UploadOnly
- Sau đó chọn **Create policy**
- Sau khi tạo xong sẽ được đưa về **Role** và hiển thị thông báo thành công
![Lmabda](/images/22.png)

📌 Sau khi hoàn tất, Lambda của bạn đã có thể upload ảnh lên S3 bucket thành công.

