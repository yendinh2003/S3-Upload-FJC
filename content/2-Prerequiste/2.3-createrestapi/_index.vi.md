---
title : "Tạo Rest API trong API Gateway"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 2.3 </b> "
---

#### Cấu hình API Gateway cho chức năng phân tích ảnh ####

1. Tìm kiếm và truy cập dịch vụ của API Gateway
    - Tại thành tìm kiếm , hãy nhập API Gateway và truy cập vào dịch vụ đó
  ![API](/images/10.png)
    - Sau khi truy cập được dịch vụ thực hiện tác vụ Create an API

2. Cấu hình API Gateway 
    - Tại trang API type, bạn có thể thấy có nhiều loại API sử dụng cho từng mục đích khác nhau như : **HTTP API**, **REST API** , **WebSocket API**,**.......**
    - Trong phần này , chúng ta sẽ cùng sử dụng **REST API**

    Trong phần choose a API type
    - Bạn hãy chọn **REST API**
    - Bấm vào button **Build**
    - Kết quả như sau:
      ![API](/images/11.png)
  Khi vào được giao diện **Create REST API**
    - API details : chọn **New API**
    - API name : ImageUploadAPI
    - API endpoint type : Regional
    - Sau đó ấn chọn buuton Create API
    

    Sau đó sẽ được điều hướng về API vừa tạo và gửi thông báo tạo thành công 
    ![API](/images/13.png)