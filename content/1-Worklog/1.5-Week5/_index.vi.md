---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---
### Mục tiêu tuần 5:

- Chuyển vector store sang Amazon RDS PostgreSQL pgvector
- Tối ưu truy vấn vector search và bắt đầu đo hiệu năng hệ thống

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                              | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                      |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------- | ------------------ | ------------------------------------------------------ |
| 2    | - Chuyển hướng vector store từ local sang Amazon RDS PostgreSQL pgvector.<br />- Cấu hình các biến môi trường kết nối RDS.<br />- Kiểm tra kết nối PostgreSQL từ ứng dụng.                                                                         | 20/07/2026       | 20/07/2026         |                                                        |
| 3    | - Cập nhật VectorStore hỗ trợ FAISS/SQLite khi chạy local và PostgreSQL pgvector khi triển khai cloud.<br />- Tạo bảng legal_chunks và cột embedding dạng vector trong PostgreSQL.<br />- Kiểm tra quá trình insert chunk và embedding vào database. | 21/07/2026       | 21/07/2026         |                                                        |
| 4    | - Tìm hiểu và triển khai tìm kiếm cosine similarity bằng pgvector.<br />- Tối ưu truy vấn RDS.<br />- Bổ sung timeout cho truy vấn PostgreSQL.                                                                                                            | 22/07/2026       | 22/07/2026         | [aws.amazon.com/vi/rds](https://aws.amazon.com/vi/rds/) |
| 5    | - Tìm hiểu và thử nghiệm index HNSW/IVFFlat cho pgvector.<br />- Viết script create_hnsw_index.py và create_ivfflat_index.py.<br />- Bổ sung benchmark và đo latency cho retrieval, embedding, DB search và LLM.                                           | 23/07/2026       | 23/07/2026         |                                                        |
| 6    | - Kiểm thử lại pipeline hỏi đáp sau khi kết nối RDS pgvector.<br />- Cập nhật README mô tả kiến trúc RDS/pgvector và cách chạy dự án.<br />- Tiếp tục cập nhật phần workshop.<br />- Thực hiện viết worklog tuần 5.                      | 24/07/2026       | 24/07/2026         |                                                        |

### Kết quả đạt được tuần 5:

- Ứng dụng hỗ trợ lưu và tìm kiếm vector bằng PostgreSQL pgvector.
- Cấu hình RDS được đưa vào hệ thống qua biến môi trường.
- Có script phục vụ tạo HNSW/IVFFlat index cho pgvector.
- Hoàn thành cập nhật worklog tuần 5.
