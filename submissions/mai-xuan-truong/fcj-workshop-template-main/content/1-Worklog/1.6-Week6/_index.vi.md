---
title: "Tuần 6"
date: 2026-05-25
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

**Mốc thời gian:** 25/5 → 29/5 (5 ngày làm việc)

## Ngày 1 - 25/5: S3 Evidence Store

**Công việc đã thực hiện:** Tôi học sâu hơn về S3 trong bài toán lưu evidence file. Tôi ghi chú vì sao file lớn không nên đi qua Lambda trực tiếp mà nên dùng presigned URL để browser upload thẳng lên S3. Tôi cũng xem các cấu hình quan trọng như bucket policy, object key, versioning, lifecycle và CORS cho upload từ trình duyệt.

**Kiến thức đã học:** S3 phù hợp làm evidence store vì bền vững, dễ phân quyền và hỗ trợ presigned URL để giảm tải backend.

**Kết quả đạt được:** Tôi hiểu được flow tạo presigned URL, browser PUT file lên S3 và backend lưu metadata riêng.

**Khó khăn và bài học:** Presigned URL cần giới hạn thời gian và không được log/publish công khai.

## Ngày 2 - 26/5: CloudWatch Logs

**Công việc đã thực hiện:** Tôi thực hành đọc CloudWatch log group, log stream, timestamp và error trace. Trong serverless, log là nguồn thông tin chính để debug vì không có server cố định để truy cập. Tôi ghi chú cách log request id, action, incident id giả lập và lỗi exception mà không ghi thông tin nhạy cảm như token, password hoặc full presigned URL.

**Kiến thức đã học:** CloudWatch giúp theo dõi Lambda/API, nhưng log cũng phải được viết có chọn lọc để không lộ dữ liệu nhạy cảm.

**Kết quả đạt được:** Tôi biết cách tìm log theo thời gian và đọc error stack trace cơ bản.

**Khó khăn và bài học:** Một log tốt cần đủ thông tin debug nhưng không chứa credential hoặc dữ liệu nhạy cảm.

## Ngày 3 - 27/5: EventBridge

**Công việc đã thực hiện:** Tôi học EventBridge event bus, rule, schedule và cách dịch vụ này hỗ trợ kiến trúc event-driven. Tôi xem hai nhóm use case: rule phản ứng theo event từ dịch vụ AWS và schedule chạy theo thời gian định kỳ. Tôi liên hệ kiến thức này với bài toán tạo report định kỳ hoặc phản ứng khi có security finding.

**Kiến thức đã học:** EventBridge giúp tách tác vụ nền khỏi request trực tiếp của người dùng và làm hệ thống linh hoạt hơn.

**Kết quả đạt được:** Tôi hiểu cách một rule có thể trigger Lambda hoặc gửi event sang service khác.

**Khó khăn và bài học:** Khi dùng event-driven, cần đặt tên event/rule rõ ràng để sau này debug không bị rối.

## Ngày 4 - 28/5: SNS notification

**Công việc đã thực hiện:** Tôi học Amazon SNS topic, subscription và cách gửi thông báo đến email hoặc endpoint khác. Tôi xem SNS như một lớp publish/subscribe đơn giản, phù hợp khi một Lambda cần thông báo cho người dùng hoặc nhóm vận hành. Tôi cũng ghi chú rằng trong workshop/report không nên đưa email thật nếu không cần thiết, chỉ dùng placeholder.

**Kiến thức đã học:** SNS giúp tách logic phát hiện sự kiện và logic thông báo, tránh Lambda phải tự xử lý quá nhiều kênh gửi.

**Kết quả đạt được:** Tôi hiểu topic/subscription và cách publish message ở mức cơ bản.

**Khó khăn và bài học:** Thông báo phải có nội dung vừa đủ, không gửi dữ liệu nhạy cảm hoặc thông tin nội bộ quá chi tiết.

## Ngày 5 - 29/5: Ghi chú bảo mật

**Công việc đã thực hiện:** Tôi tổng hợp lại các bài học bảo mật từ IAM, S3, Lambda, CloudWatch, EventBridge và SNS. Nội dung chính gồm: không hard-code credential, không đưa secret lên GitHub, hạn chế quyền IAM, kiểm tra public access, log có kiểm soát và cleanup resource sau lab. Tôi cũng bắt đầu tự tạo checklist để dùng khi viết tài liệu workshop sau này.

**Kiến thức đã học:** Bảo mật không nằm ở một dịch vụ riêng lẻ mà xuất hiện trong từng bước cấu hình và từng dòng tài liệu.

**Kết quả đạt được:** Tôi có checklist bảo mật cá nhân cho các lab và dự án cuối.

**Khó khăn và bài học:** Khi xuất bản báo cáo, cần chủ động xóa email đăng nhập, password, access key, secret key, token và API key.
