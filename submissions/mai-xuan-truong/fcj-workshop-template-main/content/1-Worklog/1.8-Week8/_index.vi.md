---
title: "Tuần 8 Worklog"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8:

- Ôn React, Vite, biến môi trường frontend và cách tích hợp API có xác thực.
- Nắm các lỗi thường gặp khi kết nối frontend với backend như CORS, token và response format.
- Chuẩn bị checklist tích hợp UI và triển khai web cho dự án cuối.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Frontend basics**<br>- **Công việc:** Tôi ôn cấu trúc React + Vite, cách chia component, file environment và thư mục build output. Dù không phụ trách toàn bộ frontend, tôi cần hiểu đủ để phối hợp khi frontend gọi API và khi deploy static assets. Tôi ghi chú sự khác nhau giữa dev server local và production build, đặc biệt là API base URL và asset path.<br>- **Kiến thức:** Frontend integration cần thống nhất API contract và environment variables với backend.<br>- **Kết quả:** Tôi hiểu hơn cách React app được build thành static files để host trên S3/CloudFront.<br>- **Bài học:** Sai base URL hoặc env var lúc build có thể làm bản deploy gọi nhầm API. | 08/06/2026 | 08/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **Luồng xác thực**<br>- **Công việc:** Tôi học cách frontend lưu trạng thái đăng nhập, nhận token từ Cognito và gửi `Authorization: Bearer <token>` khi gọi API. Tôi cũng xem các tình huống token hết hạn, user chưa đăng nhập hoặc API trả 401. Phần này giúp tôi chuẩn bị tốt hơn cho việc test Cognito Authorizer sau này.<br>- **Kiến thức:** Authentication không kết thúc ở màn hình login; token phải đi đúng từ frontend đến API Gateway.<br>- **Kết quả:** Tôi biết các điểm cần kiểm tra khi API bảo vệ trả 401 hoặc 403.<br>- **Bài học:** Không nên lưu token tùy tiện hoặc log token ra console khi test. | 09/06/2026 | 09/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **CORS troubleshooting**<br>- **Công việc:** Tôi ôn CORS header, preflight request `OPTIONS` và lý do browser có thể chặn request dù backend logic không lỗi. Tôi ghi chú các header quan trọng như `Access-Control-Allow-Origin`, `Access-Control-Allow-Headers` và `Access-Control-Allow-Methods`. Đây là kiến thức rất hữu ích vì frontend/backend tích hợp thường vướng CORS trong giai đoạn đầu.<br>- **Kiến thức:** CORS là kiểm soát phía browser, nên test bằng curl/Postman chưa chắc phản ánh đúng lỗi trên trình duyệt.<br>- **Kết quả:** Tôi có checklist kiểm tra CORS cho API Gateway và Lambda response.<br>- **Bài học:** Cần test bằng browser thật sau khi deploy stage API Gateway. | 10/06/2026 | 10/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Ghi chú tích hợp UI**<br>- **Công việc:** Tôi đọc cách chuyển UI mockup hoặc UI được generate thành React component dễ bảo trì. Tôi chú ý việc tách phần hiển thị khỏi phần gọi API, đặt state/loading/error rõ ràng và không hard-code endpoint trong component. Kiến thức này giúp tôi hỗ trợ phần Stitch AI UI integration ở giai đoạn sau.<br>- **Kiến thức:** Một UI đẹp vẫn cần cấu trúc code rõ để dễ tích hợp với backend thật.<br>- **Kết quả:** Tôi hiểu các trạng thái cần có khi gọi API: loading, success, empty, error và unauthorized.<br>- **Bài học:** Nếu không tách API logic, việc đổi endpoint hoặc auth header sẽ rất khó kiểm soát. | 11/06/2026 | 11/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Tổng kết tuần**<br>- **Công việc:** Tôi tổng hợp lại các ghi chú về frontend/backend integration, gồm React build, environment variables, auth token, CORS và API error handling. Tôi cũng lập danh sách rủi ro cần kiểm tra trong dự án thật: gọi sai endpoint, thiếu header, token hết hạn, cache frontend cũ và response format không khớp UI.<br>- **Kiến thức:** Frontend và backend phải thống nhất từ contract đến cách xử lý lỗi thì demo mới ổn định.<br>- **Kết quả:** Tôi có checklist tích hợp để dùng khi nhóm bắt đầu nối frontend với backend IRMS.<br>- **Bài học:** Cần test theo flow người dùng thật, không chỉ test từng API riêng lẻ. | 12/06/2026 | 12/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 8:

- **08/06/2026:** Tôi hiểu hơn cách React app được build thành static files để host trên S3/CloudFront. Sai base URL hoặc env var lúc build có thể làm bản deploy gọi nhầm API.
- **09/06/2026:** Tôi biết các điểm cần kiểm tra khi API bảo vệ trả 401 hoặc 403. Không nên lưu token tùy tiện hoặc log token ra console khi test.
- **10/06/2026:** Tôi có checklist kiểm tra CORS cho API Gateway và Lambda response. Cần test bằng browser thật sau khi deploy stage API Gateway.
- **11/06/2026:** Tôi hiểu các trạng thái cần có khi gọi API: loading, success, empty, error và unauthorized. Nếu không tách API logic, việc đổi endpoint hoặc auth header sẽ rất khó kiểm soát.
- **12/06/2026:** Tôi có checklist tích hợp để dùng khi nhóm bắt đầu nối frontend với backend IRMS. Cần test theo flow người dùng thật, không chỉ test từng API riêng lẻ.
