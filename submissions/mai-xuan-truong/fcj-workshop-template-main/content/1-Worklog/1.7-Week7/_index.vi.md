---
title: "Tuần 7"
date: 2026-06-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

**Mốc thời gian:** 1/6 → 5/6 (5 ngày làm việc)

## Ngày 1 - 1/6: Tổng quan AWS SAM

**Công việc đã thực hiện:** Tôi bắt đầu học AWS SAM để hiểu cách mô tả serverless infrastructure bằng code. Tôi đọc cấu trúc project gồm `template.yaml`, thư mục function, `requirements.txt`, parameters, outputs và resource definitions. Tôi so sánh SAM với việc cấu hình thủ công trên Console: SAM khó hơn lúc đầu nhưng giúp deploy lặp lại và dễ kiểm soát thay đổi hơn.

**Kiến thức đã học:** Infrastructure as Code giúp giảm lỗi thao tác tay và làm tài liệu triển khai rõ ràng hơn.

**Kết quả đạt được:** Tôi nắm được cấu trúc cơ bản của một project SAM và vai trò của `template.yaml`.

**Khó khăn và bài học:** Cần đặt tên resource, parameter và output nhất quán ngay từ đầu.

## Ngày 2 - 2/6: Thực hành sam validate

**Công việc đã thực hiện:** Tôi thực hành dùng `sam validate` để kiểm tra template trước khi build/deploy. Tôi thử đọc lỗi cú pháp, lỗi indent YAML và lỗi khai báo resource thiếu thuộc tính. Việc này giúp tôi thấy rằng một lỗi nhỏ trong YAML có thể làm CloudFormation không tạo stack được.

**Kiến thức đã học:** Validate sớm giúp phát hiện lỗi template trước khi deploy lên AWS, tiết kiệm thời gian debug.

**Kết quả đạt được:** Tôi biết cách đọc một số lỗi cơ bản từ SAM/CloudFormation.

**Khó khăn và bài học:** YAML rất nhạy với indent, nên cần format rõ và không sửa vội trong template lớn.

## Ngày 3 - 3/6: Thực hành sam build

**Công việc đã thực hiện:** Tôi học `sam build` và cách SAM đóng gói dependency cho Lambda. Tôi xem build artifact được tạo ở đâu, vì sao Python dependency phải nằm trong `requirements.txt`, và vì sao môi trường build cần giống runtime càng nhiều càng tốt. Tôi cũng ghi chú cần kiểm tra artifact trước khi deploy nếu function import thư viện ngoài.

**Kiến thức đã học:** Build là bước trung gian quan trọng để đảm bảo Lambda có đủ code và dependency khi chạy trên AWS.

**Kết quả đạt được:** Tôi hiểu hơn vì sao local code chạy được nhưng Lambda có thể lỗi import nếu build sai.

**Khó khăn và bài học:** Cần kiểm tra dependency và runtime version trước khi deploy.

## Ngày 4 - 4/6: Thực hành sam deploy

**Công việc đã thực hiện:** Tôi học `sam deploy --guided`, stack name, region, capabilities và CloudFormation outputs. Tôi chú ý cách SAM upload artifact lên S3, tạo/ cập nhật CloudFormation stack và trả output như API endpoint. Tôi cũng ghi lại rằng sau mỗi thay đổi lớn cần biết stack đang ở trạng thái nào để tránh deploy chồng chéo.

**Kiến thức đã học:** Deploy bằng SAM giúp quy trình rõ ràng hơn, nhưng vẫn phải hiểu CloudFormation stack bên dưới.

**Kết quả đạt được:** Tôi nắm được luồng validate, build, deploy và kiểm output.

**Khó khăn và bài học:** Nếu deploy fail, cần đọc event của CloudFormation chứ không chỉ nhìn lỗi cuối cùng trong terminal.

## Ngày 5 - 5/6: Checklist triển khai

**Công việc đã thực hiện:** Tôi lập checklist cho các lần triển khai sau: kiểm AWS profile/region, chạy validate, build, deploy, lưu output, test API, xem CloudWatch Logs và cleanup resource test. Checklist này được chuẩn bị trước khi vào dự án thật để giảm lỗi thao tác khi nhiều service liên kết với nhau.

**Kiến thức đã học:** Quy trình triển khai có checklist sẽ ổn định hơn, đặc biệt với dự án nhóm có nhiều người cùng thay đổi.

**Kết quả đạt được:** Tôi có một quy trình deploy cá nhân để áp dụng cho giai đoạn IRMS sau này.

**Khó khăn và bài học:** Không nên deploy theo trí nhớ; nên ghi lệnh và điều kiện kiểm tra rõ ràng.
