---
title: "Tuần 5"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

**Mốc thời gian:** 18/5 → 22/5 (5 ngày làm việc)

## Ngày 1 - 18/5: Học Cognito

**Công việc đã thực hiện:** Tôi học Amazon Cognito User Pool, App Client, hosted UI, JWT token và sự khác nhau giữa authentication và authorization. Tôi chú ý cách một user đăng nhập, nhận token và dùng token đó để gọi API được bảo vệ. Tôi cũng đọc các claim cơ bản trong JWT như `sub`, `email`, `groups` và thời gian hết hạn token.

**Kiến thức đã học:** Cognito giúp ứng dụng có xác thực người dùng mà không tự xây toàn bộ hệ thống login/password.

**Kết quả đạt được:** Tôi hiểu được vai trò của User Pool, App Client và JWT trong kiến trúc serverless.

**Khó khăn và bài học:** Cần lưu ý không để client secret trong frontend và phải xử lý lỗi token hết hạn rõ ràng.

## Ngày 2 - 19/5: Học API Gateway

**Công việc đã thực hiện:** Tôi ôn REST API, route, method, stage, CORS, request/response format và cách tích hợp API Gateway với Lambda. Tôi đặc biệt chú ý preflight request vì đây là lỗi rất hay gặp khi frontend gọi API. Tôi cũng xem cách authorizer gắn với route để chỉ cho phép request có JWT hợp lệ đi tiếp.

**Kiến thức đã học:** API Gateway là cửa vào của backend serverless, vừa định tuyến request vừa có thể xử lý xác thực/CORS/throttling.

**Kết quả đạt được:** Tôi biết cần kiểm tra route, method, stage deployment và response header khi API không hoạt động.

**Khó khăn và bài học:** Sau khi đổi cấu hình API Gateway, nhiều trường hợp phải deploy lại stage thì frontend mới nhận thay đổi.

## Ngày 3 - 20/5: Học Lambda

**Công việc đã thực hiện:** Tôi đọc cấu trúc Lambda handler, event object, context, environment variables, IAM role và CloudWatch Logs. Tôi so sánh Lambda với EC2: Lambda không cần giữ server chạy liên tục nhưng phải viết code stateless và xử lý timeout rõ ràng. Tôi cũng ghi chú cách tách từng chức năng nhỏ như CRUD, upload evidence hoặc generate report thành function riêng.

**Kiến thức đã học:** Lambda phù hợp cho tác vụ theo request/event và cần log tốt để debug vì không thể SSH vào server như EC2.

**Kết quả đạt được:** Tôi hiểu cách Lambda nhận request từ API Gateway và trả response cho frontend.

**Khó khăn và bài học:** Cần tránh hard-code secret trong code; các giá trị cấu hình nên đi qua environment variables hoặc Secrets Manager.

## Ngày 4 - 21/5: Học DynamoDB

**Công việc đã thực hiện:** Tôi học partition key, sort key, item, query, scan và cách thiết kế NoSQL theo access pattern. Khác với database quan hệ, DynamoDB yêu cầu nghĩ trước ứng dụng sẽ truy vấn dữ liệu như thế nào. Tôi phác thảo ví dụ đơn giản: incident theo `incidentId`, timeline theo `incidentId + timestamp`, evidence metadata theo incident để dễ lấy danh sách.

**Kiến thức đã học:** DynamoDB mạnh khi access pattern rõ ràng, nhưng nếu thiết kế key sai thì query sẽ khó và tốn chi phí hơn.

**Kết quả đạt được:** Tôi biết phân biệt query và scan, đồng thời hiểu vì sao không nên scan toàn bảng trong API thường xuyên.

**Khó khăn và bài học:** Data model NoSQL cần được bàn sớm với API design, không nên làm sau cùng.

## Ngày 5 - 22/5: Ghi chú service mapping

**Công việc đã thực hiện:** Tôi tạo một ghi chú liên kết Cognito, API Gateway, Lambda, DynamoDB, S3 và CloudWatch thành mô hình serverless cơ bản. Mục tiêu là hiểu request đi từ frontend qua API Gateway, được Cognito Authorizer kiểm tra, Lambda xử lý, DynamoDB/S3 lưu dữ liệu và CloudWatch ghi log. Đây chưa phải triển khai dự án IRMS, mà là bước chuẩn bị kiến thức để sau này áp dụng.

**Kiến thức đã học:** Một hệ thống serverless thực tế cần nhiều dịch vụ phối hợp, không thể học từng service hoàn toàn tách biệt.

**Kết quả đạt được:** Tôi có service mapping đầu tiên để dùng khi thảo luận dự án nhóm.

**Khó khăn và bài học:** Cần ghi rõ đâu là kiến thức chuẩn bị, đâu là phần đã triển khai thật để báo cáo không bị hiểu nhầm.
