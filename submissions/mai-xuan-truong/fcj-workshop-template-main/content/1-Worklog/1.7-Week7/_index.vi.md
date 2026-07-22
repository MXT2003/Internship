---
title: "Tuần 7 Worklog"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

- Tìm hiểu EventBridge, SNS, CloudWatch và các cơ chế giám sát/cảnh báo trên AWS.
- Hiểu luồng event-driven và cách hệ thống phản ứng khi có sự kiện phát sinh.
- Chuẩn bị checklist cho alerting, logging và testing trong IRMS.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 1 | - **Tổng quan AWS SAM**<br>- **Công việc:** Tôi bắt đầu học AWS SAM để hiểu cách mô tả serverless infrastructure bằng code. Tôi đọc cấu trúc project gồm `template.yaml`, thư mục function, `requirements.txt`, parameters, outputs và resource definitions. Tôi so sánh SAM với việc cấu hình thủ công trên Console: SAM khó hơn lúc đầu nhưng giúp deploy lặp lại và dễ kiểm soát thay đổi hơn.<br>- **Kiến thức:** Infrastructure as Code giúp giảm lỗi thao tác tay và làm tài liệu triển khai rõ ràng hơn.<br>- **Kết quả:** Tôi nắm được cấu trúc cơ bản của một project SAM và vai trò của `template.yaml`.<br>- **Bài học:** Cần đặt tên resource, parameter và output nhất quán ngay từ đầu. | 01/06/2026 | 01/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 2 | - **Thực hành sam validate**<br>- **Công việc:** Tôi thực hành dùng `sam validate` để kiểm tra template trước khi build/deploy. Tôi thử đọc lỗi cú pháp, lỗi indent YAML và lỗi khai báo resource thiếu thuộc tính. Việc này giúp tôi thấy rằng một lỗi nhỏ trong YAML có thể làm CloudFormation không tạo stack được.<br>- **Kiến thức:** Validate sớm giúp phát hiện lỗi template trước khi deploy lên AWS, tiết kiệm thời gian debug.<br>- **Kết quả:** Tôi biết cách đọc một số lỗi cơ bản từ SAM/CloudFormation.<br>- **Bài học:** YAML rất nhạy với indent, nên cần format rõ và không sửa vội trong template lớn. | 02/06/2026 | 02/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 3 | - **Thực hành sam build**<br>- **Công việc:** Tôi học `sam build` và cách SAM đóng gói dependency cho Lambda. Tôi xem build artifact được tạo ở đâu, vì sao Python dependency phải nằm trong `requirements.txt`, và vì sao môi trường build cần giống runtime càng nhiều càng tốt. Tôi cũng ghi chú cần kiểm tra artifact trước khi deploy nếu function import thư viện ngoài.<br>- **Kiến thức:** Build là bước trung gian quan trọng để đảm bảo Lambda có đủ code và dependency khi chạy trên AWS.<br>- **Kết quả:** Tôi hiểu hơn vì sao local code chạy được nhưng Lambda có thể lỗi import nếu build sai.<br>- **Bài học:** Cần kiểm tra dependency và runtime version trước khi deploy. | 03/06/2026 | 03/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 4 | - **Thực hành sam deploy**<br>- **Công việc:** Tôi học `sam deploy --guided`, stack name, region, capabilities và CloudFormation outputs. Tôi chú ý cách SAM upload artifact lên S3, tạo/ cập nhật CloudFormation stack và trả output như API endpoint. Tôi cũng ghi lại rằng sau mỗi thay đổi lớn cần biết stack đang ở trạng thái nào để tránh deploy chồng chéo.<br>- **Kiến thức:** Deploy bằng SAM giúp quy trình rõ ràng hơn, nhưng vẫn phải hiểu CloudFormation stack bên dưới.<br>- **Kết quả:** Tôi nắm được luồng validate, build, deploy và kiểm output.<br>- **Bài học:** Nếu deploy fail, cần đọc event của CloudFormation chứ không chỉ nhìn lỗi cuối cùng trong terminal. | 04/06/2026 | 04/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |
| 5 | - **Checklist triển khai**<br>- **Công việc:** Tôi lập checklist cho các lần triển khai sau: kiểm AWS profile/region, chạy validate, build, deploy, lưu output, test API, xem CloudWatch Logs và cleanup resource test. Checklist này được chuẩn bị trước khi vào dự án thật để giảm lỗi thao tác khi nhiều service liên kết với nhau.<br>- **Kiến thức:** Quy trình triển khai có checklist sẽ ổn định hơn, đặc biệt với dự án nhóm có nhiều người cùng thay đổi.<br>- **Kết quả:** Tôi có một quy trình deploy cá nhân để áp dụng cho giai đoạn IRMS sau này.<br>- **Bài học:** Không nên deploy theo trí nhớ; nên ghi lệnh và điều kiện kiểm tra rõ ràng. | 05/06/2026 | 05/06/2026 | AWS Documentation, FCJ labs, ghi chú thực tập |

### Kết quả đạt được trong tuần 7:

- **01/06/2026:** Tôi nắm được cấu trúc cơ bản của một project SAM và vai trò của `template.yaml`. Cần đặt tên resource, parameter và output nhất quán ngay từ đầu.
- **02/06/2026:** Tôi biết cách đọc một số lỗi cơ bản từ SAM/CloudFormation. YAML rất nhạy với indent, nên cần format rõ và không sửa vội trong template lớn.
- **03/06/2026:** Tôi hiểu hơn vì sao local code chạy được nhưng Lambda có thể lỗi import nếu build sai. Cần kiểm tra dependency và runtime version trước khi deploy.
- **04/06/2026:** Tôi nắm được luồng validate, build, deploy và kiểm output. Nếu deploy fail, cần đọc event của CloudFormation chứ không chỉ nhìn lỗi cuối cùng trong terminal.
- **05/06/2026:** Tôi có một quy trình deploy cá nhân để áp dụng cho giai đoạn IRMS sau này. Không nên deploy theo trí nhớ; nên ghi lệnh và điều kiện kiểm tra rõ ràng.
