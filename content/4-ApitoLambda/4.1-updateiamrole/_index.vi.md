---
title : "Cấu hình API Gateway REST API kết nối Lambda"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 4.1 </b> "
---

🎯 Mục tiêu:
Tạo một endpoint dạng:
~~~
https://abc123.execute-api.us-east-1.amazonaws.com/prod/upload
~~~
→ Khi gọi API POST + gửi ảnh base64 → Lambda chạy → upload lên S3.
1. Cấu Hình

Như ở trên bước 2.3 [Tạo REST API](\2.3-createrestapi)
- Chọn APIs ở thanh chức năng bên trái , sau đó chọn API mà ta đã tạo
- Sau đó tiếp tục cấu hình cho **API** đó
![API](/images/23.png)

Tại trang cấu hình cho API chúng ta tạo , truy cập vào **Resources**
- Tiến hành **Create resources**

- Resource name : upload
- Cuối là Create reosources
![API](/images/24.png)
![API](/images/25.png)
- Sau đó sẽ trả về lại giao diện **Resources** và thông báo tạo thành công
- Chọn /upload → Actions → Create Method → chọn POST → nhấn tick ✔️
![API](/images/26.png)
- Cấu hình:
- Integration type: Lambda Function
- Use Lambda Proxy integration: ✅ BẬT
- Lambda Region: us-east-1
- Lambda Function: chọn uploadImageToS3
- Nhấn Create Method
![API](/images/27.png)
![API](/images/28.png)

2. Deploy API
- Trên thanh menu Actions → chọn Deploy API
- Tạo một Stage mới:
- Stage name: prod
- Nhấn Deploy
  ![Lambda](/images/29.png)
    ![Lambda](/images/30.png)

Sau khi deploy xong, bạn sẽ thấy link giống như:
~~~
https://co9tjkrvjc.execute-api.us-east-1.amazonaws.com/prod
~~~
![Lambda](/images/31.png)