---
title: "Tuần 9"
date: 2026-06-15
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

**Mốc thời gian:** 15/6 → 19/6 (5 ngày làm việc)

## Ngày 1 - 15/6: Nghiên cứu incident management

**Công việc đã thực hiện:** Tôi nghiên cứu vòng đời incident trong hệ thống quản lý sự cố: tạo mới, phân loại mức độ, cập nhật trạng thái, phân công người xử lý, ghi timeline, đính kèm evidence và tạo report. Đây vẫn là giai đoạn chuẩn bị kiến thức, chưa bắt tay triển khai IRMS. Tôi tập trung hiểu logic nghiệp vụ để sau này khi thiết kế API và DynamoDB không bị thiếu entity quan trọng.

**Kiến thức đã học:** Muốn xây hệ thống incident management cần hiểu workflow nghiệp vụ trước khi chọn service AWS.

**Kết quả đạt được:** Tôi có danh sách chức năng cốt lõi để thảo luận với nhóm khi bắt đầu dự án.

**Khó khăn và bài học:** Nếu chỉ nghĩ theo service kỹ thuật mà bỏ qua workflow, hệ thống dễ thiếu chức năng quan trọng.

## Ngày 2 - 16/6: Chuẩn bị data model

**Công việc đã thực hiện:** Tôi phác thảo các entity có thể cần cho hệ thống incident như incident, timeline entry, evidence metadata, user và report. Tôi thử suy nghĩ theo access pattern: lấy danh sách incident theo trạng thái, lấy detail theo incidentId, lấy timeline/evidence theo incidentId và lưu metadata để truy xuất nhanh. Nội dung này chỉ là chuẩn bị, chưa phải final design.

**Kiến thức đã học:** Data model NoSQL cần bắt đầu từ cách đọc/ghi dữ liệu thay vì chỉ liệt kê bảng như database quan hệ.

**Kết quả đạt được:** Tôi có bản nháp để mang vào buổi thảo luận nhóm về DynamoDB.

**Khó khăn và bài học:** Cần tránh thiết kế quá phức tạp khi chưa rõ phạm vi demo.

## Ngày 3 - 17/6: Chuẩn bị API design

**Công việc đã thực hiện:** Tôi ghi ra các route API có thể cần như tạo incident, lấy danh sách, cập nhật trạng thái, thêm timeline, tạo presigned URL cho evidence và tạo report. Tôi cũng ghi chú request/response nên đơn giản, nhất quán và dễ test bằng frontend. Vì dự án chưa bắt đầu chính thức, phần này đóng vai trò chuẩn bị để tiết kiệm thời gian khi vào sprint triển khai.

**Kiến thức đã học:** API contract là cầu nối giữa frontend và backend, nên cần thống nhất sớm trước khi code nhiều.

**Kết quả đạt được:** Tôi có bản nháp endpoint để thảo luận và điều chỉnh cùng nhóm.

**Khó khăn và bài học:** Không nên tạo quá nhiều route vượt phạm vi demo vì sẽ làm testing và documentation nặng hơn.

## Ngày 4 - 18/6: Chuẩn bị report và alert flow

**Công việc đã thực hiện:** Tôi ôn cách một hệ thống có thể tạo report định kỳ hoặc phản ứng với sự kiện bảo mật. Tôi liên hệ EventBridge với scheduled report, SNS với notification, Lambda với xử lý logic và S3 với lưu file kết quả. Tôi cũng ghi chú rằng nếu có AI Assistant thì secret của provider phải nằm trong Secrets Manager, không xuất hiện ở frontend hoặc repo.

**Kiến thức đã học:** Report/alert flow thường là tác vụ nền, phù hợp với event-driven serverless hơn là xử lý trực tiếp trong request người dùng.

**Kết quả đạt được:** Tôi có hướng sơ bộ cho phần report generation và alert automation.

**Khó khăn và bài học:** Cần phân biệt rõ phần sẽ triển khai thật và phần chỉ là đề xuất mở rộng.

## Ngày 5 - 19/6: Tổng kết chuẩn bị dự án

**Công việc đã thực hiện:** Tôi gom toàn bộ ghi chú từ các tuần trước thành checklist trước khi vào dự án: authentication, API Gateway, Lambda handler, DynamoDB access pattern, S3 evidence, EventBridge/SNS, CloudWatch log, frontend integration và deployment. Tôi cũng chuẩn bị các câu hỏi để thảo luận với nhóm về phạm vi tính năng, phân công và timeline.

**Kiến thức đã học:** Giai đoạn chuẩn bị giúp vào dự án nhanh hơn nhưng vẫn cần nhóm thống nhất trước khi triển khai thật.

**Kết quả đạt được:** Tôi có checklist kỹ thuật và câu hỏi để dùng trong buổi bắt đầu IRMS ở tuần 11.

**Khó khăn và bài học:** Không nên ghi trong Worklog rằng dự án đã làm từ tuần này; đây chỉ là nghiên cứu và chuẩn bị.
