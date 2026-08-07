---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Khởi động dự án trên local, phụ trách phần xử lý dữ liệu như thiết kế contract, pipeline ETL và kiểm định chất lượng dữ liệu.
* Xây dựng và chuẩn hóa đường ống dữ liệu chứng khoán phục vụ cho Data Lake.
* Nghiên cứu, tối ưu hóa kiến trúc Data Lake và Serverless Data Lake Framework theo định hướng của nhóm trưởng.

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Bắt đầu dự án trên local. <br> - Em chịu trách nhiệm về xử lý dữ liệu cho nhóm:  <br>&emsp; + Thiết kế Data Contract cho dữ liệu OHLCV và News. <br>&emsp; + Định nghĩa schema, partition strategy, manifest và Data Quality rules. <br>&emsp; + Xây dựng manifest và bộ quy tắc Data Quality (DQ) để phục vụ quá trình ingest dữ liệu.                                                                                            | 20/07/2026   | 20/07/2026      |
| 3   | - Xây dựng pipeline ETL chuẩn hóa dữ liệu. <br> - Thực hiện chuẩn hóa dữ liệu OHLCV, xử lý missing values và kiểu dữ liệu. <br> - Tính toán các đặc trưng gồm MA20, RSI và Daily Return. <br> - Chuyển đổi dữ liệu sang định dạng Apache Parquet phục vụ Data Lake.                                            | 21/07/2026   | 21/07/2026      |  |
| 4   | - Triển khai Data Quality (DQ) Validation. <br> - Xây dựng quy trình kiểm tra chất lượng dữ liệu cho khoảng 100 mã cổ phiếu, bao gồm các tiêu chí Completeness, Uniqueness, Range và Freshness. <br> - Thiết lập cơ chế quarantine để tách các bản ghi không hợp lệ và sinh báo cáo DQ. | 22/07/2026   | 22/07/2026      |  |
| 5   | - Nhóm trưởng báo rằng pipeline có vẻ chưa thực sự ổn nên nhờ em tìm hiểu kỹ lại về Data Lake cũng như là Serverless Data Lake Framework. <br> - Viết báo cáo lại cách hoạt động cũng như là việc áp dụng Serverless Data Lake Framework vào project như thế nào.                                                                                          | 23/07/2026   | 23/07/2026      |  |


### Kết quả đạt được tuần 5:

* Thiết kế Data Contract: Định nghĩa thành công schema, partition strategy, manifest và bộ quy tắc Data Quality cho dữ liệu OHLCV và News.

* Xây dựng Pipeline ETL:
  * Thực hiện chuẩn hóa dữ liệu OHLCV, xử lý missing values và định dạng kiểu dữ liệu.
  * Tính toán các chỉ báo kỹ thuật cốt lõi: MA20, RSI và Daily Return.
  * Chuyển đổi và lưu trữ dữ liệu sang định dạng Apache Parquet phục vụ Data Lake.

* Kiểm định chất lượng dữ liệu (Data Quality):

  * Xây dựng quy trình kiểm tra DQ cho khoảng 100 mã cổ phiếu dựa trên các tiêu chí: Completeness, Uniqueness, Range và Freshness.
  * Thiết lập cơ chế quarantine để tách các bản ghi không hợp lệ và tự động sinh báo cáo DQ.

* Nghiên cứu kiến trúc: Tìm hiểu kỹ về Data Lake và Serverless Data Lake Framework, đồng thời hoàn thành báo cáo về cơ chế hoạt động cũng như phương án áp dụng vào dự án.


