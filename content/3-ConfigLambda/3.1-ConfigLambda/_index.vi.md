---
title : "Cấu hình Lambda"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.1 </b> "
---
1. Truy cập vào Lambda và funtion vừa tạo
Tại giao diện dịch vụ Lambda:
- Ở bên trái là danh sách chức năng của Lambda, chúng ta sẽ chọn **Function**
- Bạn có thể thấy danh sách function chúng ta đã tạo ở trên là "fjc-upload-image"
- Tiến hành click vào function đó chúng ta sẽ thấy overview về function đó
![Lambda](/images/14.png)
2. Cấu hình Lambda
- Tại đây chính là phần mà bạn có thể thao tác các dòng lệnh code để lập trình bằng **ngôn ngữ Python** như đã cấu hình ở phần trước đó:
![Lambda](/images/15.png)
- Tại đây bạn sẽ tiến hành nhập code để chức năng phân tích ảnh có thể hoạt động
- Bạn hãy nhập code theo cấu trúc như sau:
~~~
const AWS = require('aws-sdk');
const s3 = new AWS.S3();
const BUCKET = 'fjc-s3bucket'; // <-- đổi tên bucket của mình

exports.handler = async (event) => {
    try {
        const body = JSON.parse(event.body);
        const imageData = body.image; // base64 image
        const buffer = Buffer.from(imageData, 'base64');
        const fileName = `upload-${Date.now()}.jpg`;

        await s3.putObject({
            Bucket: BUCKET,
            Key: fileName,
            Body: buffer,
            ContentEncoding: 'base64',
            ContentType: 'image/jpeg',
        }).promise();

        return {
            statusCode: 200,
            body: JSON.stringify({ message: 'Upload thành công', key: fileName }),
        };
    } catch (error) {
        return {
            statusCode: 500,
            body: JSON.stringify({ error: error.message }),
        };
    }
};
~~~
- Sau khi nhập vào trong phần Code Source theo cấu trúc trên bạn có thể tiến hành lưu lại cách thay đổi bằng cách:
- Bấm button **Deploy** hoặc tổ hợp phím (Ctrl + Shift + U)
- Đợi một vài giây, hệ thống sẽ lưu lại tất cả các thay đổi của bạn và trả về thông báo lưu thành công
- Kết quả như các hình bên dưới:
![Lambda](/images/16.png)

Bạn đã hoàn thành bước cấu hình cho Lambda