---
title : "Test API trên PostMan"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---
#### TEST API UPLOAD ẢNH Base64 TRÊN POSTMAN 
Trong đề tài này chúng ta sẽ sử dụng Base64,công dụng của Base64 trong đề tài upload ảnh lên S3 bằng Lambda và API Gateway là giúp truyền dữ liệu ảnh qua mạng (HTTP) một cách an toàn và dễ xử lý trong môi trường text-only như JSON hoặc Lambda

1. Base64 là gì?
- Base64 là một cách mã hóa nhị phân thành văn bản (chuỗi ký tự), giúp gửi các file (ảnh, âm thanh, v.v.) qua các hệ thống chỉ hỗ trợ văn bản như:
  + JSON
  + HTML
  + HTTP request body
- Ưu điểm khi dùng Base64
  + Dễ nhúng vào JSON ("body": "{ imageBase64: '...'}")
  + Không cần cấu hình phức tạp như multipart/form-data
  + Có thể test dễ dàng trong Lambda console

- Trong đề tài này, Base64 giúp mã hóa ảnh thành chuỗi văn bản để gửi qua API Gateway một cách dễ dàng, và Lambda có thể giải mã lại để upload lên S3. Đây là giải pháp đơn giản, hiệu quả để truyền ảnh trong môi trường không hỗ trợ file trực tiếp như Lambda Console hay API Gateway.
2. Test API trên PostMan
- Như ở trên ta đã gọi được URL là:
~~~
https://co9tjkrvjc.execute-api.us-east-1.amazonaws.com/prod/uploads
~~~
- Tiếp theo cùng tiến hành trên PostMan
  + Method : POST
  + URL    : API vừa tạo
  + Header : "" Content-Type: application/json ""
  + Body   :
    ~~~
    {"image": "/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBxISEh..."}
    ~~~
- Đường link image là mình convert sang base64
![API](/images/32.png)
![API](/images/33.png)
- Sau đó nhấn Send và kết quả sẽ được hiển thị bên dưới :
![API](/images/34.png)

3. Kiểm tra kết quả trên S3 
- Sai khi Post man thông báo upload thành công thì chúng ta qua S3 kiểm tra kết quả ảnh đã lên chưa
- Như trong hình ảnh là đã thành công
![API](/images/35.png)
- Nếu muốn xem ảnh chi tiết, hãy chọn ảnh bạn muốn xem , khi giao diện mở ra chọn **Open**
- Khi đó sẽ được chuyển sang trang mới và ảnh đã được hiển thị
![API](/images/36.png)
![API](/images/37.png)

Vậy là bạn đã thực hiện upload ảnh lên S3 thành công