---
title: "Tuần 5 Worklog"
date: 2026-05-18
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

- Tập trung vào các dịch vụ serverless chính: Cognito, API Gateway, Lambda, DynamoDB và S3.
- Hiểu cách thiết kế xác thực, API contract, xử lý nghiệp vụ và lưu trữ file an toàn.
- Chuẩn bị kiến thức nền cho phần hạ tầng AWS của dự án IRMS.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Học Cognito**<br>- **Công việc:** Tôi học Amazon Cognito User Pool, App Client, hosted UI, JWT token và sự khác nhau giữa authentication và authorization. Tôi chú ý cách một user đăng nhập, nhận token và dùng token đó để gọi API được bảo vệ. Tôi cũng đọc các claim cơ bản trong JWT như `sub`, `email`, `groups` và thời gian hết hạn token.<br>- **Kiến thức:** Cognito giúp ứng dụng có xác thực người dùng mà không tự xây toàn bộ hệ thống login/password.<br>- **Kết quả:** Tôi hiểu được vai trò của User Pool, App Client và JWT trong kiến trúc serverless.<br>- **Bài học:** Cần lưu ý không để client secret trong frontend và phải xử lý lỗi token hết hạn rõ ràng. | 18/05/2026 | 18/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **Học API Gateway**<br>- **Công việc:** Tôi ôn REST API, route, method, stage, CORS, request/response format và cách tích hợp API Gateway với Lambda. Tôi đặc biệt chú ý preflight request vì đây là lỗi rất hay gặp khi frontend gọi API. Tôi cũng xem cách authorizer gắn với route để chỉ cho phép request có JWT hợp lệ đi tiếp.<br>- **Kiến thức:** API Gateway là cửa vào của backend serverless, vừa định tuyến request vừa có thể xử lý xác thực/CORS/throttling.<br>- **Kết quả:** Tôi biết cần kiểm tra route, method, stage deployment và response header khi API không hoạt động.<br>- **Bài học:** Sau khi đổi cấu hình API Gateway, nhiều trường hợp phải deploy lại stage thì frontend mới nhận thay đổi. | 19/05/2026 | 19/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **Học Lambda**<br>- **Công việc:** Tôi đọc cấu trúc Lambda handler, event object, context, environment variables, IAM role và CloudWatch Logs. Tôi so sánh Lambda với EC2: Lambda không cần giữ server chạy liên tục nhưng phải viết code stateless và xử lý timeout rõ ràng. Tôi cũng ghi chú cách tách từng chức năng nhỏ như CRUD, upload evidence hoặc generate report thành function riêng.<br>- **Kiến thức:** Lambda phù hợp cho tác vụ theo request/event và cần log tốt để debug vì không thể SSH vào server như EC2.<br>- **Kết quả:** Tôi hiểu cách Lambda nhận request từ API Gateway và trả response cho frontend.<br>- **Bài học:** Cần tránh hard-code secret trong code; các giá trị cấu hình nên đi qua environment variables hoặc Secrets Manager. | 20/05/2026 | 20/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Học DynamoDB**<br>- **Công việc:** Tôi học partition key, sort key, item, query, scan và cách thiết kế NoSQL theo access pattern. Khác với database quan hệ, DynamoDB yêu cầu nghĩ trước ứng dụng sẽ truy vấn dữ liệu như thế nào. Tôi phác thảo ví dụ đơn giản: incident theo `incidentId`, timeline theo `incidentId + timestamp`, evidence metadata theo incident để dễ lấy danh sách.<br>- **Kiến thức:** DynamoDB mạnh khi access pattern rõ ràng, nhưng nếu thiết kế key sai thì query sẽ khó và tốn chi phí hơn.<br>- **Kết quả:** Tôi biết phân biệt query và scan, đồng thời hiểu vì sao không nên scan toàn bảng trong API thường xuyên.<br>- **Bài học:** Data model NoSQL cần được bàn sớm với API design, không nên làm sau cùng. | 21/05/2026 | 21/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Ghi chú service mapping**<br>- **Công việc:** Tôi tạo một ghi chú liên kết Cognito, API Gateway, Lambda, DynamoDB, S3 và CloudWatch thành mô hình serverless cơ bản. Mục tiêu là hiểu request đi từ frontend qua API Gateway, được Cognito Authorizer kiểm tra, Lambda xử lý, DynamoDB/S3 lưu dữ liệu và CloudWatch ghi log. Đây chưa phải triển khai dự án IRMS, mà là bước chuẩn bị kiến thức để sau này áp dụng.<br>- **Kiến thức:** Một hệ thống serverless thực tế cần nhiều dịch vụ phối hợp, không thể học từng service hoàn toàn tách biệt.<br>- **Kết quả:** Tôi có service mapping đầu tiên để dùng khi thảo luận dự án nhóm.<br>- **Bài học:** Cần ghi rõ đâu là kiến thức chuẩn bị, đâu là phần đã triển khai thật để báo cáo không bị hiểu nhầm. | 22/05/2026 | 22/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 5:

- **18/05/2026:** Tôi hiểu được vai trò của User Pool, App Client và JWT trong kiến trúc serverless. Cần lưu ý không để client secret trong frontend và phải xử lý lỗi token hết hạn rõ ràng.
- **19/05/2026:** Tôi biết cần kiểm tra route, method, stage deployment và response header khi API không hoạt động. Sau khi đổi cấu hình API Gateway, nhiều trường hợp phải deploy lại stage thì frontend mới nhận thay đổi.
- **20/05/2026:** Tôi hiểu cách Lambda nhận request từ API Gateway và trả response cho frontend. Cần tránh hard-code secret trong code; các giá trị cấu hình nên đi qua environment variables hoặc Secrets Manager.
- **21/05/2026:** Tôi biết phân biệt query và scan, đồng thời hiểu vì sao không nên scan toàn bảng trong API thường xuyên. Data model NoSQL cần được bàn sớm với API design, không nên làm sau cùng.
- **22/05/2026:** Tôi có service mapping đầu tiên để dùng khi thảo luận dự án nhóm. Cần ghi rõ đâu là kiến thức chuẩn bị, đâu là phần đã triển khai thật để báo cáo không bị hiểu nhầm.
