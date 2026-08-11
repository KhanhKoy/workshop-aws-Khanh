---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---
### Mục tiêu tuần 8:

- Hoàn thiện cấu hình triển khai EC2/Docker và rà soát bảo mật trước khi tổng kết
- Hoàn thành các phần còn lại của báo cáo cá nhân và báo cáo thực tập

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                 |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------- | ------------------ | --------------------------------------------------------------------------------- |
| 2    | - Hoàn thiện cấu hình triển khai Docker cho môi trường EC2.<br />- Cập nhật deploy/Dockerfile, docker-compose.yml, entrypoint.sh và requirements-deploy.txt.<br />- Kiểm tra cách khởi chạy FastAPI và Streamlit bằng Docker Compose.<br />- Viết bài blog 3.                                                                                                                                                        | 10/08/2026       | 10/08/2026         |                                                                                   |
| 3    | - Viết deploy/README.md hướng dẫn triển khai trên Amazon EC2.<br />- Thiết kế mô hình triển khai FastAPI, Streamlit, RDS pgvector và Bedrock.<br />- Cấu hình ứng dụng sử dụng RDS thay cho SQLite khi chạy cloud.                                                                                                                                                                                                   | 11/08/2026       | 11/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4    | - Viết migration cho app domain trên PostgreSQL/RDS.<br />- Tìm hiểu IAM Instance Role cho EC2 để truy cập Bedrock và S3 an toàn hơn access key.<br />- Rà soát bảo mật cấu hình .env và AUTH_DISABLED.                                                                                                                                                                                                                | 12/08/2026       | 12/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5    | - Chuẩn bị hướng chuyển secret sang AWS Secrets Manager.<br />- Kiểm thử lại chatbot, API, giao diện admin và chức năng xóa session.<br />- Rà soát các lỗi còn lại trong code, database và triển khai.                                                                                                                                                                                                             | 13/08/2026       | 13/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6    | - Hoàn thiện báo cáo thực tập và biên bản liên quan.<br />- Viết báo cáo event.<br />- Hoàn thiện phần workshop tổng hợp công việc thực hiện trong dự án.<br />- Thực hiện viết self-assessment.<br />- Thực hiện viết feedback về chương trình thực tập.<br />- Thực hiện viết worklog tuần 8.<br />- Họp nhóm tổng kết tiến độ, hoàn thiện demo, workshop và báo cáo cuối kỳ. | 14/08/2026       | 14/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 8:

- Hoàn thiện tài liệu và cấu hình triển khai Docker/EC2 cho dự án.
- Ứng dụng được rà soát lại về cấu hình RDS, bảo mật và vận hành cloud.
- Hoàn thành báo cáo workshop, self-assessment, feedback và worklog tuần 8.
- Hoàn thành bài blog 3.
- Họp nhóm tổng kết tiến độ, rà soát các phần còn thiếu của dự án và báo cáo.
- Phối hợp hoàn thiện demo, tài liệu triển khai và nội dung workshop.
- Review báo cáo cuối kỳ, góp ý và chỉnh sửa nội dung giữa các thành viên trong nhóm.
- Tổng hợp được đầy đủ nội dung phục vụ báo cáo thực tập cuối kỳ.
