---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
**Amazon S3 (Simple Storage Service)** là dịch vụ lưu trữ đối tượng của AWS, cho phép người dùng lưu trữ và truy xuất bất kỳ loại dữ liệu nào như hình ảnh, video, tài liệu, hay tệp dữ liệu lớn. Dữ liệu trong S3 được lưu trong các "bucket" và có thể truy cập thông qua URL hoặc API. S3 cung cấp khả năng lưu trữ gần như không giới hạn, độ bền cao, và khả năng tích hợp mạnh mẽ với các dịch vụ khác trong hệ sinh thái AWS. Đây là lựa chọn lý tưởng cho việc lưu trữ file tĩnh, sao lưu dữ liệu, hoặc phân phối nội dung qua internet.

 **Amazon API Gateway** là dịch vụ cho phép tạo, công bố, quản lý và bảo mật các API ở quy mô lớn. Nó đóng vai trò là cổng giao tiếp giữa client (ví dụ: trình duyệt, ứng dụng mobile) và các dịch vụ backend như AWS Lambda hoặc máy chủ EC2. Với API Gateway, bạn có thể dễ dàng xây dựng API RESTful hoặc HTTP để tiếp nhận và xử lý các yêu cầu từ phía người dùng. Dịch vụ này hỗ trợ quản lý version, hạn chế rate, xác thực, và logging, giúp quá trình triển khai API trở nên nhanh chóng, an toàn và dễ kiểm soát.

 **AWS Lambda** là dịch vụ điện toán không máy chủ (serverless) của AWS, cho phép bạn chạy code mà không cần quản lý máy chủ vật lý hoặc ảo. Lambda hoạt động dựa trên cơ chế kích hoạt theo sự kiện – nghĩa là khi có sự kiện xảy ra (ví dụ: một file được upload lên S3 hoặc một request từ API Gateway), Lambda sẽ tự động chạy đoạn mã mà bạn đã viết. Bạn chỉ cần tập trung vào logic xử lý, còn AWS sẽ lo toàn bộ việc triển khai, mở rộng, và vận hành. Lambda hỗ trợ nhiều ngôn ngữ như Python, Node.js, Java, và Go, rất phù hợp cho các ứng dụng nhỏ, các tác vụ tự động, và hệ thống backend linh hoạt.

.

Với việc sử dụng S3, bạn sẽ có được những ưu điểm sau:

- Có thể lưu hàng triệu hoặc hàng tỷ file mà không lo thiếu dung lượng.
- Đảm bảo độ bền dữ liệu lên đến 99.999999999% (11 số 9), rất an toàn cho việc lưu trữ dài hạn.
- Mỗi tệp đều có URL riêng, có thể truy cập trực tiếp qua web hoặc thông qua API.
- Cho phép kiểm soát quyền truy cập từng file, từng bucket bằng policy, IAM, ACL.
- Làm việc tốt với Lambda, CloudFront, API Gateway, Athena, v.v.

Amazon S3 là một giải pháp lưu trữ đám mây mạnh mẽ, linh hoạt và đáng tin cậy, phù hợp cho cả cá nhân lẫn doanh nghiệp ở mọi quy mô. Với khả năng lưu trữ không giới hạn, độ bền dữ liệu cực cao, và tích hợp sâu với hệ sinh thái AWS, S3 là lựa chọn hàng đầu cho việc lưu trữ hình ảnh, video, tài liệu, backup, và nội dung tĩnh cho website hoặc ứng dụng. Nhờ vào cơ chế phân quyền và truy cập linh hoạt, Amazon S3 không chỉ giúp lưu trữ an toàn mà còn hỗ trợ triển khai các hệ thống hiện đại như serverless một cách dễ dàng và hiệu quả.