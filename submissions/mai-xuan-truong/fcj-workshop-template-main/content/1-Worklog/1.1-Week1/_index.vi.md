---
title: "Tuần 1"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

**Mốc thời gian:** 20/4 → 24/4 (5 ngày làm việc)

## Ngày 1 - 20/4: Thiết lập tài khoản AWS

**Công việc đã thực hiện:** Tôi bắt đầu tuần đầu bằng việc chuẩn bị môi trường học AWS, kiểm tra quyền truy cập và làm quen với AWS Console. Vì đây là giai đoạn đầu của kỳ thực tập nên tôi dành thời gian đọc kỹ các mục liên quan đến billing, region và bảo mật tài khoản. Trong quá trình tạo và kích hoạt tài khoản, tôi gặp một số vướng mắc nên phải kiểm tra lại thông tin xác thực và cách AWS xử lý trạng thái tài khoản. Tôi chọn region `ap-southeast-1` để thống nhất với các bài lab sau này.

**Kiến thức đã học:** Tôi hiểu rằng trước khi học dịch vụ AWS, việc quản lý tài khoản, billing alert và bảo mật root account là nền tảng rất quan trọng.

**Kết quả đạt được:** Tài khoản và môi trường học được chuẩn bị ổn định hơn, đủ để bắt đầu các lab cơ bản.

**Khó khăn và bài học:** Không nên dùng root account cho thao tác thường ngày và cần bật cảnh báo chi phí sớm để tránh phát sinh ngoài ý muốn.

## Ngày 2 - 21/4: IAM fundamentals

**Công việc đã thực hiện:** Tôi học IAM User, Group, Policy, Role, MFA và nguyên tắc least privilege. Thay vì chỉ làm theo lab, tôi thử đọc nội dung policy JSON để hiểu quyền nào cho phép hành động nào. Tôi cũng ghi chú lại sự khác nhau giữa user dùng cho người thật, role dùng cho service hoặc quyền tạm thời, và group dùng để gom quyền cho nhiều user. Đây là phần hơi khó lúc đầu vì các khái niệm dễ bị nhầm nếu chỉ nhìn giao diện Console.

**Kiến thức đã học:** IAM là lớp kiểm soát truy cập trung tâm của AWS; policy cần được viết theo nhu cầu thực tế thay vì cấp quyền quá rộng.

**Kết quả đạt được:** Tôi nắm rõ hơn cách phân quyền và biết vì sao các service như Lambda hoặc EC2 cần IAM role riêng.

**Khó khăn và bài học:** Bài học quan trọng là luôn bắt đầu từ quyền tối thiểu, sau đó mở thêm khi có lỗi rõ ràng.

## Ngày 3 - 22/4: S3 và lưu trữ

**Công việc đã thực hiện:** Tôi thực hành tạo S3 bucket, upload object, kiểm tra block public access, versioning và xóa tài nguyên sau lab. Tôi chú ý nhiều đến phần quyền truy cập vì S3 rất dễ bị cấu hình public sai nếu không hiểu rõ bucket policy và object permission. Ngoài thao tác cơ bản, tôi cũng đọc thêm về cách S3 dùng cho static website, lưu file bằng object key và phục vụ dữ liệu cho các dịch vụ khác.

**Kiến thức đã học:** S3 không phải thư mục truyền thống mà là object storage; access control và lifecycle cần được thiết kế ngay từ đầu.

**Kết quả đạt được:** Tôi biết cách tạo bucket an toàn hơn, kiểm tra object và dọn tài nguyên để tránh chi phí phát sinh.

**Khó khăn và bài học:** Không bật public access theo thói quen; nếu cần public website thì phải có thiết kế rõ ràng với CloudFront/WAF ở phía trước.

## Ngày 4 - 23/4: Giới thiệu EC2

**Công việc đã thực hiện:** Tôi học EC2 instance, AMI, instance type, key pair, security group và cách SSH vào máy chủ Linux. Phần thực hành giúp tôi hiểu EC2 giống một máy chủ trên cloud nhưng có thêm nhiều thành phần AWS bao quanh như VPC, subnet, security group và IAM role. Tôi cũng thử xem các lỗi thường gặp như sai key pair, port 22 chưa mở hoặc mở security group quá rộng.

**Kiến thức đã học:** EC2 cho cảm giác gần với server truyền thống, nhưng bảo mật và chi phí phụ thuộc rất nhiều vào cấu hình network và lifecycle.

**Kết quả đạt được:** Tôi hiểu được flow tạo EC2, kết nối, kiểm tra trạng thái và dọn tài nguyên sau khi dùng.

**Khó khăn và bài học:** Cần tránh mở SSH cho toàn Internet và nên stop/delete instance khi không còn sử dụng.

## Ngày 5 - 24/4: Tổng kết tuần và kiểm tra chi phí

**Công việc đã thực hiện:** Tôi tổng hợp lại nội dung tuần đầu, kiểm tra các tài nguyên đã tạo trong nhiều region và rà billing để tránh bỏ sót service. Trong quá trình này, tôi nhận ra một số dịch vụ lab nếu quên xóa hoặc tạo ở region khác có thể phát sinh chi phí dù mình nghĩ đã cleanup. Tôi ghi lại quy trình kiểm tra: xem Billing, kiểm từng region, xóa resource còn chạy và ghi chú nguyên nhân để lần sau cẩn thận hơn.

**Kiến thức đã học:** Chi phí AWS không chỉ đến từ service đang dùng trong region hiện tại; cần kiểm tra nhiều region và nhiều loại tài nguyên.

**Kết quả đạt được:** Tôi có checklist cleanup đầu tiên và bắt đầu viết worklog theo cấu trúc rõ hơn.

**Khó khăn và bài học:** Bài học lớn nhất của tuần đầu là học AWS phải đi kèm thói quen kiểm chi phí và dọn tài nguyên.
