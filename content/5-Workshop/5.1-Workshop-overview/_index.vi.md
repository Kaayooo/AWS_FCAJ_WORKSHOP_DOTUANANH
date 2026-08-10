---
title: "Giới thiệu Hệ thống Thu Thập và Phân tích Dữ liệu Tài chính Chứng khoán Việt Nam"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 5.1. </b>"
---

# TỔNG QUAN DỰ ÁN

### 1. Giới thiệu chung
Hệ thống là một giải pháp toàn diện (end-to-end) được triển khai trên nền tảng AWS Serverless. Dự án được thiết kế nhằm tự động thu thập, lưu trữ, chuẩn hóa và phân tích dữ liệu tài chính của các doanh nghiệp niêm yết trên cả ba sàn HOSE, HNX và UPCOM. Nhờ ứng dụng kiến trúc serverless, hệ thống tối ưu hóa khả năng xử lý quy mô lớn, dễ dàng mở rộng và tiết kiệm đáng kể chi phí vận hành.

### 2. Mục tiêu và Phạm vi
**Mục tiêu cốt lõi:**
* Tự động hóa quá trình thu thập báo cáo tài chính (BCTC) và giá cổ phiếu từ nhiều nguồn uy tín (vnstock, CafeF, VCI, MAS, v.v.).
* Làm sạch, chuẩn hóa dữ liệu theo một cấu trúc (schema) thống nhất và lưu trữ tối ưu dưới định dạng Parquet trong mô hình Data Lake trên Amazon S3 (phân chia theo các lớp: Raw, Curated, Feature).
* Tính toán các bộ chỉ số tài chính (Thanh khoản, Sinh lời, Đòn bẩy, Quy mô & Tăng trưởng) và gán nhãn rủi ro bằng phương pháp Rule-based kết hợp mô hình Altman Z-Score.
* Chuẩn bị dữ liệu đầu vào và huấn luyện các mô hình Machine Learning (XGBoost, LightGBM, CatBoost) để dự báo nguy cơ kiệt quệ tài chính (Financial Distress), tập trung tối ưu chỉ số Recall.
* Cung cấp API truy vấn tốc độ cao, hỗ trợ Dashboard trực quan hóa và thiết lập cơ chế cảnh báo tự động qua email/SMS.

**Giới hạn phạm vi (Out of scope):** 
Dự án tập trung vào mức độ PoC (Proof of Concept), do đó không bao gồm: huấn luyện mô hình ML phân tán quy mô lớn, phân tích dữ liệu thời gian thực (real-time/HFT), triển khai dự phòng đa vùng (multi-region/DR), hoặc các cơ chế xác thực production-grade phức tạp.

### 3. Kiến trúc hệ thống và Luồng dữ liệu
Hệ thống vận hành tự động theo kiến trúc 5 tầng chuyên biệt:
* **Tầng Thu thập (Ingestion & Raw):** Sử dụng Amazon EventBridge và AWS Step Functions để điều phối AWS Lambda/ECS chạy các crawler/API fetcher định kỳ. Dữ liệu JSON thô được tải về, kiểm soát rate-limit, lọc lỗi và lưu trữ vào phân vùng thời gian trên S3 Raw.
* **Tầng Lưu trữ (Storage):** Toàn bộ dữ liệu được quản lý tập trung thông qua Amazon S3 và định dạng danh mục bằng Glue Data Catalog.
* **Tầng Xử lý (Processing & Curated):** Các AWS Glue Jobs (Python/Spark) thực thi ETL để đọc dữ liệu thô, khử trùng lặp, xử lý dữ liệu khuyết thiếu/ngoại lai (Winsorize), tính toán chỉ số kỹ thuật và lưu lại dưới định dạng Parquet theo phân vùng mã chứng khoán (ticker).
* **Tầng Truy vấn & ML (Query & ML):** Dữ liệu được truy vấn ad-hoc qua Amazon Athena và hệ thống API (FastAPI/Lambda kết hợp DuckDB) để xuất dữ liệu nhanh chóng phục vụ Frontend. Song song, dữ liệu feature được đẩy vào pipeline để huấn luyện và đánh giá mô hình ML.
* **Tầng Ứng dụng (Application & Alerting):** Người dùng tương tác qua giao diện React (quản lý bởi AWS Amplify), kết nối với Backend thông qua Amazon API Gateway. Hệ thống sử dụng Amazon Cognito để xác thực cơ bản và Amazon SES để gửi cảnh báo.

![architecture](/images/5-Workshop/5.1-Workshop-overview/architecture_overview.jpg)

### 4. Triển khai và Vận hành
* **Quản lý cơ sở hạ tầng:** Sử dụng Terraform (Infrastructure as Code) để triển khai môi trường đám mây.
* **Đóng gói & Phụ thuộc:** Môi trường PoC được container hóa bằng Docker (khởi chạy qua lệnh `docker compose up --build`) và khóa chặt các thư viện phụ thuộc bằng `uv.lock` trên nền Python 3.12, đảm bảo tính nhất quán khi tái lập môi trường.

### 5. Lợi ích và Đối tượng sử dụng
* **Lợi ích mang lại:** Tăng tốc đáng kể quy trình chuẩn hóa và phân tích BCTC, phát hiện sớm các rủi ro tài chính tiềm ẩn, từ đó hỗ trợ công tác quản trị rủi ro và ra quyết định đầu tư chính xác. 
* **Đối tượng hướng tới:** Các nhà đầu tư, chuyên viên phân tích tài chính, kỹ sư dữ liệu và các tổ chức đang tìm kiếm một hệ thống giám sát, cảnh báo rủi ro đáng tin cậy trên thị trường doanh nghiệp Việt Nam.

