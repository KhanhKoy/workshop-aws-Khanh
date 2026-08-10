---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
### Mục tiêu tuần 7:

- Tích hợp giao diện Streamlit, FastAPI backend và các API quản trị
- Bổ sung xác thực, phân quyền, upload tài liệu và hạ tầng nền bằng AWS services

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                                                                                 | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                 |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | ------------------ | --------------------------------------------------------------------------------- |
| 2    | - Tích hợp giao diện Streamlit với core RAG.<br />- Chỉnh sửa UI, database và luồng hỏi đáp.<br />- Kiểm tra chatbot hoạt động trên giao diện Streamlit.                                                                                                                                                                                                                                                                | 03/08/2026       | 03/08/2026         |                                                                                   |
| 3    | - Bổ sung FastAPI backend cho các API chat, conversation và admin.<br />- Tìm hiểu và tích hợp Amazon Cognito cho xác thực người dùng.<br />- Xây dựng Cognito JWT verification trong FastAPI.                                                                                                                                                                                                                            | 04/08/2026       | 04/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4    | - Thiết kế phân quyền RBAC theo nhóm users, editors và admins.<br />- Viết Cognito admin service để quản lý user và group.<br />- Kiểm thử chức năng list, enable, disable user và add user to group.                                                                                                                                                                                                                   | 05/08/2026       | 05/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5    | - Viết DynamoDB chat repository để lưu conversation metadata và message.<br />- Xây dựng API admin tạo presigned S3 upload.<br />- Tạo S3 manifest chứa metadata, document_id, actor và object_key cho ingestion.                                                                                                                                                                                                             | 06/08/2026       | 06/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6    | - Viết Lambda handler nhận sự kiện S3 hoặc SQS để xử lý tài liệu mới.<br />- Bổ sung cơ chế partial batch failure, retry và DLQ cho Lambda/SQS.<br />- Tạo CloudFormation template cho Cognito, DynamoDB, S3, SQS và DLQ.<br />- Viết bài blog 2.<br />- Viết báo cáo event "AWS FCAJ Agent Forge - Deepdive Ngày 1".<br />- Tiếp tục cập nhật phần workshop.<br />- Thực hiện viết worklog tuần 7. | 07/08/2026       | 07/08/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 7:

- Giao diện Streamlit được tích hợp với core RAG
- FastAPI backend có thêm các API phục vụ chat, conversation và admin
- Bổ sung xác thực Cognito và phân quyền theo nhóm người dùng
- Có CloudFormation template cho các tài nguyên nền Cognito, DynamoDB, S3, SQS và DLQ
- Hoàn thành bài blog 2, báo cáo event và worklog tuần 7.
