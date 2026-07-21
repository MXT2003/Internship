---
title: "Tuần 4"
date: 2026-05-11
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

**Mốc thời gian:** 11/5 → 15/5 (5 ngày làm việc)

## Ngày 1 - 11/5: Route 53 và DNS

**Công việc đã thực hiện:** Tôi học Route 53, hosted zone, record type và cách DNS đưa người dùng đến ứng dụng. Tôi tìm hiểu sự khác nhau giữa A record, CNAME, alias record và vì sao AWS thường dùng alias khi trỏ domain về CloudFront hoặc ALB. Phần này giúp tôi hiểu hơn bước đầu tiên của một request trước khi vào hệ thống backend.

**Kiến thức đã học:** DNS là lớp vào đầu tiên của người dùng, nên cấu hình sai DNS có thể làm ứng dụng không truy cập được dù backend vẫn chạy.

**Kết quả đạt được:** Tôi hiểu cách domain, record và target AWS liên kết với nhau.

**Khó khăn và bài học:** Cần kiểm tra TTL và propagation khi debug lỗi domain không cập nhật ngay.

## Ngày 2 - 12/5: CloudFront concepts

**Công việc đã thực hiện:** Tôi học CloudFront như CDN dùng để phân phối nội dung từ edge location đến người dùng gần hơn. Tôi chú ý các khái niệm origin, behavior, cache policy, default root object, HTTPS và invalidation. Khi đọc lại các lỗi thường gặp, tôi thấy cache là nguyên nhân dễ gây nhầm vì source đã sửa nhưng trình duyệt vẫn nhận bundle cũ.

**Kiến thức đã học:** CloudFront không chỉ tăng tốc static asset mà còn giúp che origin và chuẩn hóa HTTPS cho frontend.

**Kết quả đạt được:** Tôi nắm được vì sao sau khi deploy frontend thường cần invalidation.

**Khó khăn và bài học:** Khi kiểm tra lỗi sau deploy, cần phân biệt lỗi build, lỗi upload, lỗi cache và lỗi gọi API.

## Ngày 3 - 13/5: WAF và bảo vệ web

**Công việc đã thực hiện:** Tôi đọc AWS WAF, web ACL, rule group và managed rules. Tôi tập trung vào vai trò của WAF ở lớp edge, nơi có thể chặn request xấu trước khi vào ứng dụng. Dù chưa triển khai chuyên sâu trong lab, tôi ghi chú các use case như chặn pattern tấn công phổ biến, rate limit và bảo vệ endpoint public.

**Kiến thức đã học:** Bảo mật web nên có nhiều lớp; WAF giúp giảm rủi ro ở lớp HTTP trước khi request đi vào backend.

**Kết quả đạt được:** Tôi hiểu vị trí của WAF khi đặt trước CloudFront/API Gateway.

**Khó khăn và bài học:** Không nên ghi WAF như đã triển khai production nếu trong dự án chỉ đưa vào phần đề xuất hoặc future enhancement.

## Ngày 4 - 14/5: Static web hosting review

**Công việc đã thực hiện:** Tôi thực hành lại ý tưởng hosting frontend bằng S3 và phân phối qua CloudFront. Tôi xem cách file `index.html`, JavaScript bundle và static assets được phục vụ. Tôi cũng ghi chú vấn đề SPA routing: khi refresh một route con, CloudFront/S3 cần được cấu hình để trả về `index.html` thay vì 404.

**Kiến thức đã học:** Frontend SPA cần cấu hình hosting khác với website tĩnh đơn giản vì routing nằm phía client.

**Kết quả đạt được:** Tôi hiểu rõ hơn mối quan hệ giữa S3 bucket, CloudFront origin và browser cache.

**Khó khăn và bài học:** Khi deploy frontend cần kiểm tra cả trang chủ, route con và asset path.

## Ngày 5 - 15/5: Tài liệu hóa trong tuần

**Công việc đã thực hiện:** Tôi chuyển các nội dung Route 53, CloudFront, WAF và S3 hosting thành ghi chú ngắn có thể dùng cho báo cáo. Tôi cố gắng viết theo kiểu service nào giải quyết vấn đề gì, dùng ở đâu trong kiến trúc và có rủi ro/cấu hình cần chú ý nào. Việc này giúp các tuần sau khi làm dự án dễ chọn service hơn.

**Kiến thức đã học:** Ghi chú theo vai trò service trong kiến trúc giúp nhớ lâu hơn việc chỉ học từng menu trong Console.

**Kết quả đạt được:** Tôi có danh sách các dịch vụ edge/network có thể dùng cho phần frontend deployment.

**Khó khăn và bài học:** Không nên đưa quá nhiều lý thuyết rời rạc vào Worklog; cần gắn với quá trình học và mục tiêu thực tập.
