---
title: "Tuần 8"
date: 2026-06-08
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

**Mốc thời gian:** 8/6 → 12/6 (5 ngày làm việc)

## Ngày 1 - 8/6: Frontend basics

**Công việc đã thực hiện:** Tôi ôn cấu trúc React + Vite, cách chia component, file environment và thư mục build output. Dù không phụ trách toàn bộ frontend, tôi cần hiểu đủ để phối hợp khi frontend gọi API và khi deploy static assets. Tôi ghi chú sự khác nhau giữa dev server local và production build, đặc biệt là API base URL và asset path.

**Kiến thức đã học:** Frontend integration cần thống nhất API contract và environment variables với backend.

**Kết quả đạt được:** Tôi hiểu hơn cách React app được build thành static files để host trên S3/CloudFront.

**Khó khăn và bài học:** Sai base URL hoặc env var lúc build có thể làm bản deploy gọi nhầm API.

## Ngày 2 - 9/6: Luồng xác thực

**Công việc đã thực hiện:** Tôi học cách frontend lưu trạng thái đăng nhập, nhận token từ Cognito và gửi `Authorization: Bearer <token>` khi gọi API. Tôi cũng xem các tình huống token hết hạn, user chưa đăng nhập hoặc API trả 401. Phần này giúp tôi chuẩn bị tốt hơn cho việc test Cognito Authorizer sau này.

**Kiến thức đã học:** Authentication không kết thúc ở màn hình login; token phải đi đúng từ frontend đến API Gateway.

**Kết quả đạt được:** Tôi biết các điểm cần kiểm tra khi API bảo vệ trả 401 hoặc 403.

**Khó khăn và bài học:** Không nên lưu token tùy tiện hoặc log token ra console khi test.

## Ngày 3 - 10/6: CORS troubleshooting

**Công việc đã thực hiện:** Tôi ôn CORS header, preflight request `OPTIONS` và lý do browser có thể chặn request dù backend logic không lỗi. Tôi ghi chú các header quan trọng như `Access-Control-Allow-Origin`, `Access-Control-Allow-Headers` và `Access-Control-Allow-Methods`. Đây là kiến thức rất hữu ích vì frontend/backend tích hợp thường vướng CORS trong giai đoạn đầu.

**Kiến thức đã học:** CORS là kiểm soát phía browser, nên test bằng curl/Postman chưa chắc phản ánh đúng lỗi trên trình duyệt.

**Kết quả đạt được:** Tôi có checklist kiểm tra CORS cho API Gateway và Lambda response.

**Khó khăn và bài học:** Cần test bằng browser thật sau khi deploy stage API Gateway.

## Ngày 4 - 11/6: Ghi chú tích hợp UI

**Công việc đã thực hiện:** Tôi đọc cách chuyển UI mockup hoặc UI được generate thành React component dễ bảo trì. Tôi chú ý việc tách phần hiển thị khỏi phần gọi API, đặt state/loading/error rõ ràng và không hard-code endpoint trong component. Kiến thức này giúp tôi hỗ trợ phần Stitch AI UI integration ở giai đoạn sau.

**Kiến thức đã học:** Một UI đẹp vẫn cần cấu trúc code rõ để dễ tích hợp với backend thật.

**Kết quả đạt được:** Tôi hiểu các trạng thái cần có khi gọi API: loading, success, empty, error và unauthorized.

**Khó khăn và bài học:** Nếu không tách API logic, việc đổi endpoint hoặc auth header sẽ rất khó kiểm soát.

## Ngày 5 - 12/6: Tổng kết tuần

**Công việc đã thực hiện:** Tôi tổng hợp lại các ghi chú về frontend/backend integration, gồm React build, environment variables, auth token, CORS và API error handling. Tôi cũng lập danh sách rủi ro cần kiểm tra trong dự án thật: gọi sai endpoint, thiếu header, token hết hạn, cache frontend cũ và response format không khớp UI.

**Kiến thức đã học:** Frontend và backend phải thống nhất từ contract đến cách xử lý lỗi thì demo mới ổn định.

**Kết quả đạt được:** Tôi có checklist tích hợp để dùng khi nhóm bắt đầu nối frontend với backend IRMS.

**Khó khăn và bài học:** Cần test theo flow người dùng thật, không chỉ test từng API riêng lẻ.
