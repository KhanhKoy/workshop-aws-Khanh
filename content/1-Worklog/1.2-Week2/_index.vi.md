---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
### Mục tiêu tuần 2:

* Hoàn thiện pipeline xử lý dữ liệu pháp luật và tối ưu quá trình build index
* Tìm hiểu RDS PostgreSQL pgvector, Bedrock Titan Embedding và viết proposal cho dự ánHiểu dịch vụ AWS cơ bản, cách dùng console & CL

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                       | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                 |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | ------------------ | --------------------------------------------------------------------------------- |
| 2    | - Tiếp tục hoàn thiện pipeline xử lý dữ liệu pháp luật.<br />- Cải tiến đọc dữ liệu theo streaming/batch để giảm sử dụng RAM.<br />- Tối ưu cách đọc metadata và content parquet theo lô nhỏ.       | 29/06/2026       | 29/06/2026         |                                                                                   |
| 3    | - Tối ưu quá trình build index.<br />- Bổ sung cơ chế commit định kỳ để tránh tràn bộ nhớ.<br />- Kiểm tra và xử lý các vấn đề phát sinh khi build dữ liệu lớn.                                    | 30/06/2026       | 30/06/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4    | - Hoàn thiện logic chunking cho văn bản pháp luật.<br />- Điều chỉnh chunk size, chunk overlap và metadata.<br />- Hoàn thiện EmbeddingService với model embedding tiếng Việt.                                  | 01/07/2026       | 01/07/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5    | - Xây dựng pipeline build index từ document, chunk, embedding đến vector store.<br />- Viết script scripts/build_index.py để tạo vector index.<br />- Chạy thử và kiểm tra kết quả build index.                 | 02/07/2026       | 02/07/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6    | - Tìm hiểu Amazon RDS PostgreSQL và extension pgvector.<br />- Tìm hiểu Amazon Bedrock Titan Embedding.<br />- Thực hiện viết proposal để trình bày ý tưởng dự án.<br />- Thực hiện viết worklog tuần 2. | 03/07/2026       | 03/07/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 2:

* Pipeline build index được hoàn thiện hơn và có khả năng xử lý dữ liệu theo batch.
- Cải thiện khả năng kiểm soát bộ nhớ khi xử lý dữ liệu lớn.
- Hoàn thiện proposal trình bày ý tưởng và định hướng của dự án.
- Nắm được vai trò của RDS pgvector và Bedrock Titan Embedding trong kiến trúc cloud.
