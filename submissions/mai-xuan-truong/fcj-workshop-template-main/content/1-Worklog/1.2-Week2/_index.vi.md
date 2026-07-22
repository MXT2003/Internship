---
title: "Tuần 2 Worklog"
date: 2026-04-27
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

- Củng cố kiến thức về VPC, EC2 networking, RDS và các thành phần serverless cơ bản.
- Hiểu cách các tầng network, compute, database và storage phối hợp trong kiến trúc AWS.
- Tổng hợp checklist lỗi thường gặp và cách cleanup tài nguyên sau lab.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Nền tảng VPC**<br>- **Công việc:** Tôi tập trung học Amazon VPC, subnet, route table, Internet Gateway, NAT Gateway, Security Group và Network ACL. Tôi hình dung VPC như mạng riêng trên AWS, trong đó public subnet dùng cho thành phần cần Internet còn private subnet dùng cho workload nội bộ. Khi làm lab, tôi tạo VPC, chia subnet, gắn Internet Gateway và chỉnh route table để kiểm tra đường đi của traffic.<br>- **Kiến thức:** Network design quyết định workload nào được public, workload nào nên giữ private và cách các tầng ứng dụng giao tiếp với nhau.<br>- **Kết quả:** Tôi hiểu rõ hơn vai trò của route table, gateway và security group trong việc cho phép hoặc chặn traffic.<br>- **Bài học:** Nếu route hoặc security group sai, lỗi kết nối có thể giống lỗi ứng dụng, nên cần debug theo từng tầng. | 27/04/2026 | 27/04/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **Lab EC2 và networking**<br>- **Công việc:** Tôi thực hành tạo EC2 trong VPC, gắn security group và kiểm tra kết nối từ máy local. Tôi thử mở port cần thiết, kiểm tra inbound/outbound rule và ghi lại các lỗi thường gặp như wrong key file, port chưa mở, instance nằm sai subnet hoặc route table chưa trỏ ra Internet Gateway. Tôi cũng đọc thêm về Session Manager như một lựa chọn truy cập EC2 an toàn hơn SSH truyền thống.<br>- **Kiến thức:** Security Group hoạt động như firewall ở cấp instance, còn subnet và route table quyết định đường đi mạng rộng hơn.<br>- **Kết quả:** Tôi có thể tự kiểm tra nguyên nhân khi EC2 không truy cập được từ bên ngoài.<br>- **Bài học:** Không nên chỉ mở port cho xong; cần hiểu vì sao port đó được mở và mở cho IP nào. | 28/04/2026 | 28/04/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **RDS và database**<br>- **Công việc:** Tôi học Amazon RDS như một dịch vụ cơ sở dữ liệu quan hệ được AWS quản lý. Trong lab, tôi xem các lựa chọn engine, DB subnet group, security group riêng cho database, backup/snapshot và endpoint kết nối. Tôi đặc biệt chú ý việc RDS nên nằm trong subnet private và chỉ cho phép EC2 hoặc application layer truy cập, không mở trực tiếp ra Internet.<br>- **Kiến thức:** Managed database giúp giảm công vận hành như patching, backup và restore, nhưng vẫn cần thiết kế network/security đúng.<br>- **Kết quả:** Tôi hiểu cách ứng dụng kết nối RDS qua endpoint và vì sao cần tách security group của app và database.<br>- **Bài học:** Database là tài nguyên dễ phát sinh chi phí, nên sau lab phải kiểm tra trạng thái và xóa snapshot/instance nếu không dùng. | 29/04/2026 | 29/04/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Giới thiệu serverless**<br>- **Công việc:** Tôi bắt đầu đọc các khái niệm serverless gồm Lambda, API Gateway, DynamoDB và CloudWatch Logs. Mục tiêu là hiểu vì sao nhiều hệ thống hiện đại không cần giữ server chạy liên tục mà chỉ xử lý khi có request hoặc event. Tôi so sánh nhanh giữa EC2 truyền thống và Lambda: EC2 kiểm soát nhiều hơn nhưng cần vận hành server, còn Lambda nhẹ hơn cho API nhỏ hoặc event-driven task.<br>- **Kiến thức:** Serverless phù hợp khi workload có thể tách thành function nhỏ, scale theo request và không cần quản lý máy chủ.<br>- **Kết quả:** Tôi có nền tảng để chuẩn bị cho các tuần sau liên quan đến API Gateway, Lambda và DynamoDB.<br>- **Bài học:** Cần thiết kế stateless và log tốt, vì Lambda không phù hợp với mọi loại workload. | 30/04/2026 | 30/04/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Tổng hợp kiến thức**<br>- **Công việc:** Tôi gom lại ghi chú từ IAM, S3, EC2, VPC, RDS và serverless thành một bảng so sánh nhỏ: service dùng để làm gì, cấu hình quan trọng, lỗi dễ gặp và cách cleanup. Tôi cũng đánh dấu những phần sẽ có ích cho dự án cuối như authentication, API layer, compute, database, storage, monitoring và cost management.<br>- **Kiến thức:** Các dịch vụ AWS không đứng riêng lẻ; khi làm hệ thống thật, chúng phải kết nối thành kiến trúc hoàn chỉnh.<br>- **Kết quả:** Tôi có tài liệu ghi chú tốt hơn để dùng khi viết Worklog và Workshop sau này.<br>- **Bài học:** Ghi chú ngay sau lab giúp nhớ lỗi thật tốt hơn nhiều so với chỉ lưu link bài học. | 01/05/2026 | 01/05/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 2:

- **27/04/2026:** Tôi hiểu rõ hơn vai trò của route table, gateway và security group trong việc cho phép hoặc chặn traffic. Nếu route hoặc security group sai, lỗi kết nối có thể giống lỗi ứng dụng, nên cần debug theo từng tầng.
- **28/04/2026:** Tôi có thể tự kiểm tra nguyên nhân khi EC2 không truy cập được từ bên ngoài. Không nên chỉ mở port cho xong; cần hiểu vì sao port đó được mở và mở cho IP nào.
- **29/04/2026:** Tôi hiểu cách ứng dụng kết nối RDS qua endpoint và vì sao cần tách security group của app và database. Database là tài nguyên dễ phát sinh chi phí, nên sau lab phải kiểm tra trạng thái và xóa snapshot/instance nếu không dùng.
- **30/04/2026:** Tôi có nền tảng để chuẩn bị cho các tuần sau liên quan đến API Gateway, Lambda và DynamoDB. Cần thiết kế stateless và log tốt, vì Lambda không phù hợp với mọi loại workload.
- **01/05/2026:** Tôi có tài liệu ghi chú tốt hơn để dùng khi viết Worklog và Workshop sau này. Ghi chú ngay sau lab giúp nhớ lỗi thật tốt hơn nhiều so với chỉ lưu link bài học.
