---
title: "Tuần 9 Worklog"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

- Củng cố kiến thức bảo mật cloud, logging, cost management và vận hành ứng dụng.
- Liên hệ các bài học AWS với yêu cầu của hệ thống quản lý sự cố an toàn thông tin.
- Chuẩn bị tư duy review tài liệu và kiểm thử theo luồng người dùng.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Nghiên cứu incident management**<br>- **Công việc:** Tôi nghiên cứu vòng đời incident trong hệ thống quản lý sự cố: tạo mới, phân loại mức độ, cập nhật trạng thái, phân công người xử lý, ghi timeline, đính kèm evidence và tạo report. Đây vẫn là giai đoạn chuẩn bị kiến thức, chưa bắt tay triển khai IRMS. Tôi tập trung hiểu logic nghiệp vụ để sau này khi thiết kế API và DynamoDB không bị thiếu entity quan trọng.<br>- **Kiến thức:** Muốn xây hệ thống incident management cần hiểu workflow nghiệp vụ trước khi chọn service AWS.<br>- **Kết quả:** Tôi có danh sách chức năng cốt lõi để thảo luận với nhóm khi bắt đầu dự án.<br>- **Bài học:** Nếu chỉ nghĩ theo service kỹ thuật mà bỏ qua workflow, hệ thống dễ thiếu chức năng quan trọng. | 15/06/2026 | 15/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **Chuẩn bị data model**<br>- **Công việc:** Tôi phác thảo các entity có thể cần cho hệ thống incident như incident, timeline entry, evidence metadata, user và report. Tôi thử suy nghĩ theo access pattern: lấy danh sách incident theo trạng thái, lấy detail theo incidentId, lấy timeline/evidence theo incidentId và lưu metadata để truy xuất nhanh. Nội dung này chỉ là chuẩn bị, chưa phải final design.<br>- **Kiến thức:** Data model NoSQL cần bắt đầu từ cách đọc/ghi dữ liệu thay vì chỉ liệt kê bảng như database quan hệ.<br>- **Kết quả:** Tôi có bản nháp để mang vào buổi thảo luận nhóm về DynamoDB.<br>- **Bài học:** Cần tránh thiết kế quá phức tạp khi chưa rõ phạm vi demo. | 16/06/2026 | 16/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **Chuẩn bị API design**<br>- **Công việc:** Tôi ghi ra các route API có thể cần như tạo incident, lấy danh sách, cập nhật trạng thái, thêm timeline, tạo presigned URL cho evidence và tạo report. Tôi cũng ghi chú request/response nên đơn giản, nhất quán và dễ test bằng frontend. Vì dự án chưa bắt đầu chính thức, phần này đóng vai trò chuẩn bị để tiết kiệm thời gian khi vào sprint triển khai.<br>- **Kiến thức:** API contract là cầu nối giữa frontend và backend, nên cần thống nhất sớm trước khi code nhiều.<br>- **Kết quả:** Tôi có bản nháp endpoint để thảo luận và điều chỉnh cùng nhóm.<br>- **Bài học:** Không nên tạo quá nhiều route vượt phạm vi demo vì sẽ làm testing và documentation nặng hơn. | 17/06/2026 | 17/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Chuẩn bị report và alert flow**<br>- **Công việc:** Tôi ôn cách một hệ thống có thể tạo report định kỳ hoặc phản ứng với sự kiện bảo mật. Tôi liên hệ EventBridge với scheduled report, SNS với notification, Lambda với xử lý logic và S3 với lưu file kết quả. Tôi cũng ghi chú rằng nếu có AI Assistant thì secret của provider phải nằm trong Secrets Manager, không xuất hiện ở frontend hoặc repo.<br>- **Kiến thức:** Report/alert flow thường là tác vụ nền, phù hợp với event-driven serverless hơn là xử lý trực tiếp trong request người dùng.<br>- **Kết quả:** Tôi có hướng sơ bộ cho phần report generation và alert automation.<br>- **Bài học:** Cần phân biệt rõ phần sẽ triển khai thật và phần chỉ là đề xuất mở rộng. | 18/06/2026 | 18/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Tổng kết chuẩn bị dự án**<br>- **Công việc:** Tôi gom toàn bộ ghi chú từ các tuần trước thành checklist trước khi vào dự án: authentication, API Gateway, Lambda handler, DynamoDB access pattern, S3 evidence, EventBridge/SNS, CloudWatch log, frontend integration và deployment. Tôi cũng chuẩn bị các câu hỏi để thảo luận với nhóm về phạm vi tính năng, phân công và timeline.<br>- **Kiến thức:** Giai đoạn chuẩn bị giúp vào dự án nhanh hơn nhưng vẫn cần nhóm thống nhất trước khi triển khai thật.<br>- **Kết quả:** Tôi có checklist kỹ thuật và câu hỏi để dùng trong buổi bắt đầu IRMS ở tuần 11.<br>- **Bài học:** Không nên ghi trong Worklog rằng dự án đã làm từ tuần này; đây chỉ là nghiên cứu và chuẩn bị. | 19/06/2026 | 19/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 9:

- **15/06/2026:** Tôi có danh sách chức năng cốt lõi để thảo luận với nhóm khi bắt đầu dự án. Nếu chỉ nghĩ theo service kỹ thuật mà bỏ qua workflow, hệ thống dễ thiếu chức năng quan trọng.
- **16/06/2026:** Tôi có bản nháp để mang vào buổi thảo luận nhóm về DynamoDB. Cần tránh thiết kế quá phức tạp khi chưa rõ phạm vi demo.
- **17/06/2026:** Tôi có bản nháp endpoint để thảo luận và điều chỉnh cùng nhóm. Không nên tạo quá nhiều route vượt phạm vi demo vì sẽ làm testing và documentation nặng hơn.
- **18/06/2026:** Tôi có hướng sơ bộ cho phần report generation và alert automation. Cần phân biệt rõ phần sẽ triển khai thật và phần chỉ là đề xuất mở rộng.
- **19/06/2026:** Tôi có checklist kỹ thuật và câu hỏi để dùng trong buổi bắt đầu IRMS ở tuần 11. Không nên ghi trong Worklog rằng dự án đã làm từ tuần này; đây chỉ là nghiên cứu và chuẩn bị.
