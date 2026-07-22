---
title: "Tuần 4 Worklog"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

- Ôn lại các dịch vụ AWS đã học và liên hệ với những mô hình triển khai ứng dụng thực tế.
- Chuẩn bị nền tảng kiến thức cho authentication, API, compute, database và monitoring.
- Ghi nhận các điểm cần áp dụng khi bước vào dự án IRMS ở giai đoạn sau.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Route 53 và DNS**<br>- **Công việc:** Tôi học Route 53, hosted zone, record type và cách DNS đưa người dùng đến ứng dụng. Tôi tìm hiểu sự khác nhau giữa A record, CNAME, alias record và vì sao AWS thường dùng alias khi trỏ domain về CloudFront hoặc ALB. Phần này giúp tôi hiểu hơn bước đầu tiên của một request trước khi vào hệ thống backend.<br>- **Kiến thức:** DNS là lớp vào đầu tiên của người dùng, nên cấu hình sai DNS có thể làm ứng dụng không truy cập được dù backend vẫn chạy.<br>- **Kết quả:** Tôi hiểu cách domain, record và target AWS liên kết với nhau.<br>- **Bài học:** Cần kiểm tra TTL và propagation khi debug lỗi domain không cập nhật ngay. | 11/05/2026 | 11/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **CloudFront concepts**<br>- **Công việc:** Tôi học CloudFront như CDN dùng để phân phối nội dung từ edge location đến người dùng gần hơn. Tôi chú ý các khái niệm origin, behavior, cache policy, default root object, HTTPS và invalidation. Khi đọc lại các lỗi thường gặp, tôi thấy cache là nguyên nhân dễ gây nhầm vì source đã sửa nhưng trình duyệt vẫn nhận bundle cũ.<br>- **Kiến thức:** CloudFront không chỉ tăng tốc static asset mà còn giúp che origin và chuẩn hóa HTTPS cho frontend.<br>- **Kết quả:** Tôi nắm được vì sao sau khi deploy frontend thường cần invalidation.<br>- **Bài học:** Khi kiểm tra lỗi sau deploy, cần phân biệt lỗi build, lỗi upload, lỗi cache và lỗi gọi API. | 12/05/2026 | 12/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **WAF và bảo vệ web**<br>- **Công việc:** Tôi đọc AWS WAF, web ACL, rule group và managed rules. Tôi tập trung vào vai trò của WAF ở lớp edge, nơi có thể chặn request xấu trước khi vào ứng dụng. Dù chưa triển khai chuyên sâu trong lab, tôi ghi chú các use case như chặn pattern tấn công phổ biến, rate limit và bảo vệ endpoint public.<br>- **Kiến thức:** Bảo mật web nên có nhiều lớp; WAF giúp giảm rủi ro ở lớp HTTP trước khi request đi vào backend.<br>- **Kết quả:** Tôi hiểu vị trí của WAF khi đặt trước CloudFront/API Gateway.<br>- **Bài học:** Không nên ghi WAF như đã triển khai production nếu trong dự án chỉ đưa vào phần đề xuất hoặc future enhancement. | 13/05/2026 | 13/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Static web hosting review**<br>- **Công việc:** Tôi thực hành lại ý tưởng hosting frontend bằng S3 và phân phối qua CloudFront. Tôi xem cách file `index.html`, JavaScript bundle và static assets được phục vụ. Tôi cũng ghi chú vấn đề SPA routing: khi refresh một route con, CloudFront/S3 cần được cấu hình để trả về `index.html` thay vì 404.<br>- **Kiến thức:** Frontend SPA cần cấu hình hosting khác với website tĩnh đơn giản vì routing nằm phía client.<br>- **Kết quả:** Tôi hiểu rõ hơn mối quan hệ giữa S3 bucket, CloudFront origin và browser cache.<br>- **Bài học:** Khi deploy frontend cần kiểm tra cả trang chủ, route con và asset path. | 14/05/2026 | 14/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Tài liệu hóa trong tuần**<br>- **Công việc:** Tôi chuyển các nội dung Route 53, CloudFront, WAF và S3 hosting thành ghi chú ngắn có thể dùng cho báo cáo. Tôi cố gắng viết theo kiểu service nào giải quyết vấn đề gì, dùng ở đâu trong kiến trúc và có rủi ro/cấu hình cần chú ý nào. Việc này giúp các tuần sau khi làm dự án dễ chọn service hơn.<br>- **Kiến thức:** Ghi chú theo vai trò service trong kiến trúc giúp nhớ lâu hơn việc chỉ học từng menu trong Console.<br>- **Kết quả:** Tôi có danh sách các dịch vụ edge/network có thể dùng cho phần frontend deployment.<br>- **Bài học:** Không nên đưa quá nhiều lý thuyết rời rạc vào Worklog; cần gắn với quá trình học và mục tiêu thực tập. | 15/05/2026 | 15/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 4:

- **11/05/2026:** Tôi hiểu cách domain, record và target AWS liên kết với nhau. Cần kiểm tra TTL và propagation khi debug lỗi domain không cập nhật ngay.
- **12/05/2026:** Tôi nắm được vì sao sau khi deploy frontend thường cần invalidation. Khi kiểm tra lỗi sau deploy, cần phân biệt lỗi build, lỗi upload, lỗi cache và lỗi gọi API.
- **13/05/2026:** Tôi hiểu vị trí của WAF khi đặt trước CloudFront/API Gateway. Không nên ghi WAF như đã triển khai production nếu trong dự án chỉ đưa vào phần đề xuất hoặc future enhancement.
- **14/05/2026:** Tôi hiểu rõ hơn mối quan hệ giữa S3 bucket, CloudFront origin và browser cache. Khi deploy frontend cần kiểm tra cả trang chủ, route con và asset path.
- **15/05/2026:** Tôi có danh sách các dịch vụ edge/network có thể dùng cho phần frontend deployment. Không nên đưa quá nhiều lý thuyết rời rạc vào Worklog; cần gắn với quá trình học và mục tiêu thực tập.
