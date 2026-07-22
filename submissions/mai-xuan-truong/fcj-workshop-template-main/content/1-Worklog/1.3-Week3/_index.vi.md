---
title: "Tuần 3 Worklog"
date: 2026-05-04
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

- Tìm hiểu ECS, Fargate, ALB, NAT Gateway và private subnet để mở rộng góc nhìn về kiến trúc cloud.
- Rèn kỹ năng đọc sơ đồ kiến trúc theo luồng request và boundary của từng lớp dịch vụ.
- Sắp xếp ghi chú học tập thành worklog có cấu trúc rõ ràng hơn.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Tổng quan ECS**<br>- **Công việc:** Tôi học Amazon ECS, cluster, task definition, service và container deployment trên AWS. Dù dự án cuối sau này đi theo serverless nhiều hơn, việc học ECS giúp tôi hiểu thêm cách AWS quản lý workload dạng container. Tôi xem task definition như bản mô tả container cần chạy: image, CPU, memory, port mapping, environment variables và logging.<br>- **Kiến thức:** Container giúp đóng gói ứng dụng nhất quán, còn ECS quản lý việc chạy container ở quy mô lớn.<br>- **Kết quả:** Tôi phân biệt được cluster, task, service và hiểu vì sao service cần health check.<br>- **Bài học:** Khi tài liệu hóa kiến trúc, cần nêu đúng compute model: container, serverless function hay server truyền thống. | 04/05/2026 | 04/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **Fargate và ALB**<br>- **Công việc:** Tôi học Fargate như cách chạy container mà không cần quản lý EC2 host, đồng thời tìm hiểu Application Load Balancer để phân phối traffic. Tôi chú ý cách ALB route request theo listener/rule và kiểm tra health check của target. Phần này giúp tôi hiểu vì sao frontend/backend production thường cần một entry point ổn định thay vì truy cập thẳng vào từng instance/container.<br>- **Kiến thức:** Fargate giảm phần quản trị máy chủ, còn ALB giúp traffic vào hệ thống được kiểm soát và cân bằng hơn.<br>- **Kết quả:** Tôi nắm được vai trò của listener, target group và health check trong luồng request.<br>- **Bài học:** Nếu health check sai path hoặc security group sai, service có thể chạy nhưng vẫn bị xem là unhealthy. | 05/05/2026 | 05/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **NAT và private subnet**<br>- **Công việc:** Tôi ôn lại NAT Gateway và private subnet trong ngữ cảnh workload không nên public ra Internet. Tôi ghi chú tình huống private workload cần tải package hoặc gọi service bên ngoài nhưng không muốn nhận inbound traffic trực tiếp. Đây là phần liên quan chặt đến bảo mật vì nhiều lỗi triển khai đến từ việc đặt workload vào public subnet cho tiện.<br>- **Kiến thức:** Private subnet kết hợp NAT giúp workload ra ngoài khi cần nhưng vẫn giảm bề mặt tấn công inbound.<br>- **Kết quả:** Tôi hiểu rõ hơn sự khác nhau giữa Internet Gateway và NAT Gateway.<br>- **Bài học:** NAT Gateway có thể phát sinh chi phí, nên khi làm lab cần xóa sau khi hoàn tất. | 06/05/2026 | 06/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Đọc kiến trúc cloud**<br>- **Công việc:** Tôi đọc một số kiến trúc AWS mẫu và thử bóc tách thành các lớp quen thuộc: DNS/CDN, security edge, API layer, compute, database, storage, messaging và monitoring. Cách nhìn này giúp tôi không bị rối khi một sơ đồ có nhiều dịch vụ. Tôi cũng bắt đầu ghi chú service nào thuộc global/edge, service nào thuộc regional.<br>- **Kiến thức:** Kiến trúc cloud nên được đọc theo luồng request và theo boundary của từng lớp, không chỉ nhìn logo dịch vụ.<br>- **Kết quả:** Tôi có cách tiếp cận tốt hơn để sau này vẽ sơ đồ kiến trúc IRMS.<br>- **Bài học:** Nếu sơ đồ không có mũi tên và chú thích rõ, người đọc sẽ khó hiểu data flow thật sự. | 07/05/2026 | 07/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Sắp xếp ghi chú workshop**<br>- **Công việc:** Tôi bắt đầu chuyển các ghi chú lab rời rạc thành dạng worklog có cấu trúc hơn. Mỗi ngày tôi cố gắng tách rõ: đã làm gì, học được gì, kết quả và vấn đề gặp phải. Tôi cũng rà lại các câu viết theo kiểu quá cá nhân hoặc quá dài để chỉnh sang văn phong thực tập chuyên nghiệp hơn.<br>- **Kiến thức:** Worklog không nên chỉ kể lại thao tác, mà cần cho thấy quá trình học, vấn đề và bài học rút ra.<br>- **Kết quả:** Tôi có format ghi chú ổn định hơn cho các tuần sau.<br>- **Bài học:** Nếu để ghi chú quá lâu mới biên tập, nội dung dễ bị thiếu chi tiết hoặc lẫn nhiều thông tin không cần công bố. | 08/05/2026 | 08/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 3:

- **04/05/2026:** Tôi phân biệt được cluster, task, service và hiểu vì sao service cần health check. Khi tài liệu hóa kiến trúc, cần nêu đúng compute model: container, serverless function hay server truyền thống.
- **05/05/2026:** Tôi nắm được vai trò của listener, target group và health check trong luồng request. Nếu health check sai path hoặc security group sai, service có thể chạy nhưng vẫn bị xem là unhealthy.
- **06/05/2026:** Tôi hiểu rõ hơn sự khác nhau giữa Internet Gateway và NAT Gateway. NAT Gateway có thể phát sinh chi phí, nên khi làm lab cần xóa sau khi hoàn tất.
- **07/05/2026:** Tôi có cách tiếp cận tốt hơn để sau này vẽ sơ đồ kiến trúc IRMS. Nếu sơ đồ không có mũi tên và chú thích rõ, người đọc sẽ khó hiểu data flow thật sự.
- **08/05/2026:** Tôi có format ghi chú ổn định hơn cho các tuần sau. Nếu để ghi chú quá lâu mới biên tập, nội dung dễ bị thiếu chi tiết hoặc lẫn nhiều thông tin không cần công bố.
