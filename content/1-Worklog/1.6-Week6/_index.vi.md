---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
### Mục tiêu tuần 6:

- Hoàn thiện và kiểm thử chatbot RAG end-to-end
- Tìm hiểu logging, monitoring, alerting và lưu lịch sử hội thoại bằng các dịch vụ AWS

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                          | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                 |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | ------------------ | --------------------------------------------------------------------------------- |
| 2    | - Hoàn thiện chatbot hỏi đáp pháp luật với luồng RAG end-to-end.<br />- Kiểm thử chức năng hỏi đáp sau khi dữ liệu đã được nạp vào vector store.<br />- Debug lỗi retrieval và embedding dimension.                                    | 27/07/2026       | 27/07/2026         |                                                                                   |
| 3    | - Debug lỗi kết nối database và truy vấn RDS.<br />- Tối ưu chất lượng câu trả lời bằng cách điều chỉnh top_k, prompt template và chunk size.<br />- Kiểm tra lại timeout của retrieval và LLM.                                            | 28/07/2026       | 28/07/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4    | - Tìm hiểu Amazon CloudWatch để theo dõi log và hiệu năng ứng dụng.<br />- Tìm hiểu Amazon SNS để gửi cảnh báo khi hệ thống phát sinh lỗi.<br />- Thiết kế luồng CloudWatch Alarm và SNS notification.                                   | 29/07/2026       | 29/07/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5    | - Tìm hiểu Amazon DynamoDB để lưu lịch sử hội thoại.<br />- Thiết kế bảng lưu chat history theo conversation, message, user index, admin date index và TTL.<br />- Viết tài liệu kế hoạch cải thiện tốc độ và áp dụng kiến trúc AWS. | 30/07/2026       | 30/07/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6    | - Tiếp tục kiểm thử và sửa lỗi giao diện/chatbot.<br />- Viết bài blog 1.<br />- Viết báo cáo event.<br />- Tiếp tục cập nhật phần workshop.<br />- Thực hiện viết worklog tuần 6.                                                        | 31/07/2026       | 31/07/2026         | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Kết quả đạt được tuần 6:

- Chatbot RAG hoạt động ổn định hơn sau quá trình debug và kiểm thử.
- Hoàn thiện thiết kế lưu lịch sử hội thoại bằng DynamoDB.
- Có định hướng monitoring/alerting bằng CloudWatch và SNS.
- Hoàn thành bài blog 1, báo cáo event và worklog tuần 6.
- Phối hợp với nhóm kiểm thử chatbot end-to-end và ghi nhận các lỗi phát sinh.
- Trao đổi kết quả test, latency và chất lượng câu trả lời để thống nhất các điểm cần tối ưu.
