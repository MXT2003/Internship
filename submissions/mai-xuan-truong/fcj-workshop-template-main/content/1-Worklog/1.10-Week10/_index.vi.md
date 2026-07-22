---
title: "Tuần 10 Worklog"
date: 2026-06-22
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu tuần 10:

- Tổng hợp kiến thức trước khi bước vào giai đoạn triển khai IRMS.
- Rà lại các thành phần cần cho kiến trúc serverless: authentication, API, Lambda, DynamoDB, S3, EventBridge, SNS và CloudFront.
- Chuẩn bị cách viết workshop sao cho khớp với quá trình thực hiện cá nhân trong nhóm.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Chuẩn bị chọn đề tài**<br>- **Công việc:** Tôi xem lại các hướng dự án có thể làm dựa trên những dịch vụ AWS đã học. Tôi ưu tiên một đề tài có đủ phần authentication, API, serverless compute, database, storage, event-driven automation, deployment và documentation. Giai đoạn này vẫn là chuẩn bị lựa chọn đề tài, chưa triển khai dự án thật.<br>- **Kiến thức:** Đề tài tốt cho báo cáo thực tập cần vừa có giá trị nghiệp vụ vừa thể hiện được kiến thức AWS đã học.<br>- **Kết quả:** Tôi có tiêu chí chọn đề tài rõ hơn để trao đổi với nhóm.<br>- **Bài học:** Cần chọn phạm vi vừa sức, không quá rộng so với thời gian còn lại. | 22/06/2026 | 22/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **Phác thảo kiến trúc**<br>- **Công việc:** Tôi chuẩn bị bản nháp kiến trúc serverless gồm CloudFront, API Gateway, Cognito, Lambda, DynamoDB, S3, EventBridge, SNS, CloudWatch và Secrets Manager. Bản nháp này dùng để thảo luận chứ chưa phải kiến trúc cuối. Tôi thử đặt các dịch vụ vào từng lớp: frontend delivery, authentication, API layer, compute, data layer, notification và monitoring.<br>- **Kiến thức:** Phác thảo kiến trúc giúp nhóm nhìn được hệ thống trước khi chia việc triển khai.<br>- **Kết quả:** Tôi có bản service mapping ban đầu dựa trên kiến thức đã học.<br>- **Bài học:** Sơ đồ nháp cần được cập nhật sau khi nhóm chốt yêu cầu thực tế. | 23/06/2026 | 23/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **Outline proposal**<br>- **Công việc:** Tôi lập outline cho proposal gồm bối cảnh, vấn đề cần giải quyết, mục tiêu, chức năng dự kiến, service mapping, rủi ro kỹ thuật và deliverables. Tôi cố gắng viết theo hướng dự án nhóm, trong đó phần cá nhân của tôi thiên về AWS infrastructure, deployment, testing và documentation. Nội dung này giúp chuẩn bị cho buổi chốt đề tài chính thức.<br>- **Kiến thức:** Proposal cần thể hiện rõ vấn đề, giải pháp và phạm vi chứ không chỉ liệt kê service AWS.<br>- **Kết quả:** Tôi có khung proposal để nhóm chỉnh sửa và bổ sung.<br>- **Bài học:** Cần tránh hứa quá nhiều tính năng chưa chắc triển khai kịp. | 24/06/2026 | 24/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Lên cấu trúc workshop**<br>- **Công việc:** Tôi dự kiến cách chia workshop thành các phần: giới thiệu, chuẩn bị môi trường, cấu hình hạ tầng, phát triển ứng dụng, triển khai/kiểm thử, frontend integration và cleanup. Tôi cũng ghi chú rằng sidebar cần đánh số rõ ràng và các mục con phải xuất hiện đúng theo cấu trúc Hugo. Đây là bước chuẩn bị để khi dự án bắt đầu, tài liệu không bị rối.<br>- **Kiến thức:** Workshop nên đi theo luồng người đọc thao tác, không nên sắp xếp chỉ theo service riêng lẻ.<br>- **Kết quả:** Tôi có cấu trúc ban đầu cho phần Workshop của báo cáo.<br>- **Bài học:** Nếu numbering không thống nhất từ đầu, về sau sửa sidebar và internal link sẽ mất nhiều thời gian. | 25/06/2026 | 25/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Rà soát trước dự án**<br>- **Công việc:** Tôi rà lại phần mình có thể đóng góp trước khi dự án bắt đầu chính thức: AWS infrastructure, AWS SAM, Cognito, API Gateway, Lambda, DynamoDB integration, EventBridge, SNS, CloudFront, deployment, testing và documentation. Tôi cũng tự kiểm tra lại các ghi chú bảo mật để không đưa credential vào source hoặc report.<br>- **Kiến thức:** Chuẩn bị trước vai trò cá nhân giúp khi vào dự án nhóm không bị ôm quá nhiều hoặc trùng việc với teammate.<br>- **Kết quả:** Tôi sẵn sàng hơn cho tuần bắt đầu IRMS với checklist kỹ thuật và documentation.<br>- **Bài học:** Cần ghi Worklog trung thực: các tuần trước là học và chuẩn bị, còn triển khai IRMS bắt đầu từ tuần có ngày 01/07. | 26/06/2026 | 26/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 10:

- **22/06/2026:** Tôi có tiêu chí chọn đề tài rõ hơn để trao đổi với nhóm. Cần chọn phạm vi vừa sức, không quá rộng so với thời gian còn lại.
- **23/06/2026:** Tôi có bản service mapping ban đầu dựa trên kiến thức đã học. Sơ đồ nháp cần được cập nhật sau khi nhóm chốt yêu cầu thực tế.
- **24/06/2026:** Tôi có khung proposal để nhóm chỉnh sửa và bổ sung. Cần tránh hứa quá nhiều tính năng chưa chắc triển khai kịp.
- **25/06/2026:** Tôi có cấu trúc ban đầu cho phần Workshop của báo cáo. Nếu numbering không thống nhất từ đầu, về sau sửa sidebar và internal link sẽ mất nhiều thời gian.
- **26/06/2026:** Tôi sẵn sàng hơn cho tuần bắt đầu IRMS với checklist kỹ thuật và documentation. Cần ghi Worklog trung thực: các tuần trước là học và chuẩn bị, còn triển khai IRMS bắt đầu từ tuần có ngày 01/07.
