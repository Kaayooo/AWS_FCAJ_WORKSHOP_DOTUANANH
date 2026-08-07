---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7:

* Xử lý sự cố mất credit trên AWS Organization.
* Thiết kế lại architecture chia theo layers.
* Khắc phục lỗi kỹ thuật phát sinh khi chạy thử nghiệm Glue Job với đa định dạng file.
* Hoàn thiện hệ thống.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Nhóm em gặp sự cố về mất credit khi sử dụng AWS Organization nên chúng em tìm cách tạo account mới để tiếp tục sử dụng các services. <br> - Nhóm có đưa architecture lên thì mấy anh có note là chia theo layers. <br> - Thiết kế lại architecture của nhóm theo layers. <br> - Họp team để đưa ra giải pháp về account và cũng như phân chia công việc.                                                                                             | 03/08/2026   | 03/08/2026      |
| 3   | - Chạy thử nghiệm hệ thống thì phát hiện ra lỗi Glue job không thể xử lý bucket raw khi có 2 định dạng file khác nhau. <br> - Tìm cách fix Glue Job.                                            | 04/08/2026   | 04/08/2026      |  |
| 4   | - Tìm hiểu về Step function và làm lab để hiểu rõ về Step function <br> - Áp dụng Step function vào project.   | 05/08/2026   | 05/08/2026      | <https://000047.awsstudygroup.com/vi/> |
| 5   | - Cấu hình lại Glue Job và Glue Crawler sau khi nhóm quyết định S3 bucket raw chỉ chứa file csv. <br> - Cấu hình EventBridge tự động kích hoạt flow để cào data định kỳ vào 16:30.                  | 06/08/2026   | 06/08/2026      |  |
| 6   | - Review lại hệ thống và chạy thử nghiệm xem có lỗi gì không. <br> - Viết blog đăng trên AWS Study group                  | 07/08/2026   | 07/08/2026      |  |


### Kết quả đạt được tuần 7:

* Về quản trị tài nguyên & kiến trúc: Giải quyết dứt điểm vấn đề mất credit bằng cách tạo account mới; thiết kế lại bản vẽ architecture phân thành các layers rõ ràng theo đúng nhận xét từ các anh/chị hướng dẫn; họp team phân chia lại công việc hiệu quả.

* Về xử lý sự cố & tối ưu Glue: Phát hiện và khắc phục thành công lỗi Glue job không thể xử lý bucket raw khi chứa các định dạng file khác nhau; đi đến thống nhất cấu hình lại S3 bucket raw chỉ chứa định dạng file .csv, đồng thời cấu hình lại Glue Job và Glue Crawler cho đồng bộ.

* Về kiểm thử và tổng kết: Tiến hành review toàn diện lại hệ thống, chạy thử nghiệm kiểm tra lỗi sau khi fix.


