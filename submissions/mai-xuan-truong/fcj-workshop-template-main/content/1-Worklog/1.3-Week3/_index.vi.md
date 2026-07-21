---
title: "Tuần 3"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

**Mốc thời gian:** 4/5 → 8/5 (5 ngày làm việc)

## Ngày 1 - 4/5: Tổng quan ECS

**Công việc đã thực hiện:** Tôi học Amazon ECS, cluster, task definition, service và container deployment trên AWS. Dù dự án cuối sau này đi theo serverless nhiều hơn, việc học ECS giúp tôi hiểu thêm cách AWS quản lý workload dạng container. Tôi xem task definition như bản mô tả container cần chạy: image, CPU, memory, port mapping, environment variables và logging.

**Kiến thức đã học:** Container giúp đóng gói ứng dụng nhất quán, còn ECS quản lý việc chạy container ở quy mô lớn.

**Kết quả đạt được:** Tôi phân biệt được cluster, task, service và hiểu vì sao service cần health check.

**Khó khăn và bài học:** Khi tài liệu hóa kiến trúc, cần nêu đúng compute model: container, serverless function hay server truyền thống.

## Ngày 2 - 5/5: Fargate và ALB

**Công việc đã thực hiện:** Tôi học Fargate như cách chạy container mà không cần quản lý EC2 host, đồng thời tìm hiểu Application Load Balancer để phân phối traffic. Tôi chú ý cách ALB route request theo listener/rule và kiểm tra health check của target. Phần này giúp tôi hiểu vì sao frontend/backend production thường cần một entry point ổn định thay vì truy cập thẳng vào từng instance/container.

**Kiến thức đã học:** Fargate giảm phần quản trị máy chủ, còn ALB giúp traffic vào hệ thống được kiểm soát và cân bằng hơn.

**Kết quả đạt được:** Tôi nắm được vai trò của listener, target group và health check trong luồng request.

**Khó khăn và bài học:** Nếu health check sai path hoặc security group sai, service có thể chạy nhưng vẫn bị xem là unhealthy.

## Ngày 3 - 6/5: NAT và private subnet

**Công việc đã thực hiện:** Tôi ôn lại NAT Gateway và private subnet trong ngữ cảnh workload không nên public ra Internet. Tôi ghi chú tình huống private workload cần tải package hoặc gọi service bên ngoài nhưng không muốn nhận inbound traffic trực tiếp. Đây là phần liên quan chặt đến bảo mật vì nhiều lỗi triển khai đến từ việc đặt workload vào public subnet cho tiện.

**Kiến thức đã học:** Private subnet kết hợp NAT giúp workload ra ngoài khi cần nhưng vẫn giảm bề mặt tấn công inbound.

**Kết quả đạt được:** Tôi hiểu rõ hơn sự khác nhau giữa Internet Gateway và NAT Gateway.

**Khó khăn và bài học:** NAT Gateway có thể phát sinh chi phí, nên khi làm lab cần xóa sau khi hoàn tất.

## Ngày 4 - 7/5: Đọc kiến trúc cloud

**Công việc đã thực hiện:** Tôi đọc một số kiến trúc AWS mẫu và thử bóc tách thành các lớp quen thuộc: DNS/CDN, security edge, API layer, compute, database, storage, messaging và monitoring. Cách nhìn này giúp tôi không bị rối khi một sơ đồ có nhiều dịch vụ. Tôi cũng bắt đầu ghi chú service nào thuộc global/edge, service nào thuộc regional.

**Kiến thức đã học:** Kiến trúc cloud nên được đọc theo luồng request và theo boundary của từng lớp, không chỉ nhìn logo dịch vụ.

**Kết quả đạt được:** Tôi có cách tiếp cận tốt hơn để sau này vẽ sơ đồ kiến trúc IRMS.

**Khó khăn và bài học:** Nếu sơ đồ không có mũi tên và chú thích rõ, người đọc sẽ khó hiểu data flow thật sự.

## Ngày 5 - 8/5: Sắp xếp ghi chú workshop

**Công việc đã thực hiện:** Tôi bắt đầu chuyển các ghi chú lab rời rạc thành dạng worklog có cấu trúc hơn. Mỗi ngày tôi cố gắng tách rõ: đã làm gì, học được gì, kết quả và vấn đề gặp phải. Tôi cũng rà lại các câu viết theo kiểu quá cá nhân hoặc quá dài để chỉnh sang văn phong thực tập chuyên nghiệp hơn.

**Kiến thức đã học:** Worklog không nên chỉ kể lại thao tác, mà cần cho thấy quá trình học, vấn đề và bài học rút ra.

**Kết quả đạt được:** Tôi có format ghi chú ổn định hơn cho các tuần sau.

**Khó khăn và bài học:** Nếu để ghi chú quá lâu mới biên tập, nội dung dễ bị thiếu chi tiết hoặc lẫn nhiều thông tin không cần công bố.
