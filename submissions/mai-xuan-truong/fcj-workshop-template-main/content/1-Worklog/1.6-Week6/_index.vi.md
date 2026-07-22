---
title: "Tuần 6 Worklog"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6:

- Thực hành AWS SAM và cách mô tả hạ tầng serverless bằng template.
- Làm quen với validate, build, deploy và xử lý lỗi khi triển khai tài nguyên AWS.
- Ghi chú các nguyên tắc đặt tên, IAM permission và biến môi trường để dùng cho dự án.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **S3 Evidence Store**<br>- **Công việc:** Tôi học sâu hơn về S3 trong bài toán lưu evidence file. Tôi ghi chú vì sao file lớn không nên đi qua Lambda trực tiếp mà nên dùng presigned URL để browser upload thẳng lên S3. Tôi cũng xem các cấu hình quan trọng như bucket policy, object key, versioning, lifecycle và CORS cho upload từ trình duyệt.<br>- **Kiến thức:** S3 phù hợp làm evidence store vì bền vững, dễ phân quyền và hỗ trợ presigned URL để giảm tải backend.<br>- **Kết quả:** Tôi hiểu được flow tạo presigned URL, browser PUT file lên S3 và backend lưu metadata riêng.<br>- **Bài học:** Presigned URL cần giới hạn thời gian và không được log/publish công khai. | 25/05/2026 | 25/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **CloudWatch Logs**<br>- **Công việc:** Tôi thực hành đọc CloudWatch log group, log stream, timestamp và error trace. Trong serverless, log là nguồn thông tin chính để debug vì không có server cố định để truy cập. Tôi ghi chú cách log request id, action, incident id giả lập và lỗi exception mà không ghi thông tin nhạy cảm như token, password hoặc full presigned URL.<br>- **Kiến thức:** CloudWatch giúp theo dõi Lambda/API, nhưng log cũng phải được viết có chọn lọc để không lộ dữ liệu nhạy cảm.<br>- **Kết quả:** Tôi biết cách tìm log theo thời gian và đọc error stack trace cơ bản.<br>- **Bài học:** Một log tốt cần đủ thông tin debug nhưng không chứa credential hoặc dữ liệu nhạy cảm. | 26/05/2026 | 26/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **EventBridge**<br>- **Công việc:** Tôi học EventBridge event bus, rule, schedule và cách dịch vụ này hỗ trợ kiến trúc event-driven. Tôi xem hai nhóm use case: rule phản ứng theo event từ dịch vụ AWS và schedule chạy theo thời gian định kỳ. Tôi liên hệ kiến thức này với bài toán tạo report định kỳ hoặc phản ứng khi có security finding.<br>- **Kiến thức:** EventBridge giúp tách tác vụ nền khỏi request trực tiếp của người dùng và làm hệ thống linh hoạt hơn.<br>- **Kết quả:** Tôi hiểu cách một rule có thể trigger Lambda hoặc gửi event sang service khác.<br>- **Bài học:** Khi dùng event-driven, cần đặt tên event/rule rõ ràng để sau này debug không bị rối. | 27/05/2026 | 27/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **SNS notification**<br>- **Công việc:** Tôi học Amazon SNS topic, subscription và cách gửi thông báo đến email hoặc endpoint khác. Tôi xem SNS như một lớp publish/subscribe đơn giản, phù hợp khi một Lambda cần thông báo cho người dùng hoặc nhóm vận hành. Tôi cũng ghi chú rằng trong workshop/report không nên đưa email thật nếu không cần thiết, chỉ dùng placeholder.<br>- **Kiến thức:** SNS giúp tách logic phát hiện sự kiện và logic thông báo, tránh Lambda phải tự xử lý quá nhiều kênh gửi.<br>- **Kết quả:** Tôi hiểu topic/subscription và cách publish message ở mức cơ bản.<br>- **Bài học:** Thông báo phải có nội dung vừa đủ, không gửi dữ liệu nhạy cảm hoặc thông tin nội bộ quá chi tiết. | 28/05/2026 | 28/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Ghi chú bảo mật**<br>- **Công việc:** Tôi tổng hợp lại các bài học bảo mật từ IAM, S3, Lambda, CloudWatch, EventBridge và SNS. Nội dung chính gồm: không hard-code credential, không đưa secret lên GitHub, hạn chế quyền IAM, kiểm tra public access, log có kiểm soát và cleanup resource sau lab. Tôi cũng bắt đầu tự tạo checklist để dùng khi viết tài liệu workshop sau này.<br>- **Kiến thức:** Bảo mật không nằm ở một dịch vụ riêng lẻ mà xuất hiện trong từng bước cấu hình và từng dòng tài liệu.<br>- **Kết quả:** Tôi có checklist bảo mật cá nhân cho các lab và dự án cuối.<br>- **Bài học:** Khi xuất bản báo cáo, cần chủ động xóa email đăng nhập, password, access key, secret key, token và API key. | 29/05/2026 | 29/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 6:

- **25/05/2026:** Tôi hiểu được flow tạo presigned URL, browser PUT file lên S3 và backend lưu metadata riêng. Presigned URL cần giới hạn thời gian và không được log/publish công khai.
- **26/05/2026:** Tôi biết cách tìm log theo thời gian và đọc error stack trace cơ bản. Một log tốt cần đủ thông tin debug nhưng không chứa credential hoặc dữ liệu nhạy cảm.
- **27/05/2026:** Tôi hiểu cách một rule có thể trigger Lambda hoặc gửi event sang service khác. Khi dùng event-driven, cần đặt tên event/rule rõ ràng để sau này debug không bị rối.
- **28/05/2026:** Tôi hiểu topic/subscription và cách publish message ở mức cơ bản. Thông báo phải có nội dung vừa đủ, không gửi dữ liệu nhạy cảm hoặc thông tin nội bộ quá chi tiết.
- **29/05/2026:** Tôi có checklist bảo mật cá nhân cho các lab và dự án cuối. Khi xuất bản báo cáo, cần chủ động xóa email đăng nhập, password, access key, secret key, token và API key.
