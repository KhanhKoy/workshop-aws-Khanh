---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---
### Mục tiêu tuần 3:

- Xây dựng luồng hỏi đáp RAG hoàn chỉnh cho chatbot pháp luật
- Tích hợp giao diện Chainlit và thiết kế kiến trúc AWS ban đầu cho ứng dụng

### Các công việc cần triển khai trong tuần này:

| Thứ | Công việc                                                                                                                                                                                                                                                                                                                                                                            | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                                                                                                                                                                                  |
| ---- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2    | - Xây dựng luồng hỏi đáp RAG hoàn chỉnh cho chatbot pháp luật.<br />- Hoàn thiện module retriever.py để truy xuất chunk liên quan.<br />- Kiểm tra kết quả retrieval với dữ liệu pháp luật.                                                                                                                                                                 | 06/07/2026       | 06/07/2026         |                                                                                                                                                                                                    |
| 3    | - Hoàn thiện module prompt.py để tạo prompt dựa trên câu hỏi và context.<br />- Thiết kế prompt phù hợp cho chatbot pháp luật Việt Nam.<br />- Điều chỉnh cách đưa nguồn tài liệu vào câu trả lời.                                                                                                                                                    | 07/07/2026       | 07/07/2026         |                                                                                                                                                                                                    |
| 4    | - Hoàn thiện module generator.py để sinh câu trả lời từ LLM.<br />- Bổ sung khả năng chọn provider Gemini hoặc Amazon Bedrock.<br />- Tìm hiểu Amazon Bedrock Runtime cho phần LLM generation.                                                                                                                                                                      | 08/07/2026       | 08/07/2026         |                                                                                                                                                                                                    |
| 5    | - Hoàn thiện module qa_service.py để kết nối retriever, prompt và generator.<br />- Tạo giao diện chat bằng Chainlit trong app.py.<br />- Tích hợp Chainlit với RAG core.                                                                                                                                                                                              | 09/07/2026       | 09/07/2026         |                                                                                                                                                                                                    |
| 6    | - Tìm hiểu kiến trúc ứng dụng chạy trên Amazon EC2.<br />- Thiết kế sơ đồ kiến trúc AWS ban đầu với ALB, EC2, RDS pgvector và Bedrock.<br />- Cập nhật nội dung workshop theo các công việc đã thực hiện.<br />- Thực hiện viết worklog tuần 3.<br />- Trao đổi với nhóm về luồng RAG, kết quả retrieval và hướng cải thiện chatbot. | 10/07/2026       | 10/07/2026         | [aws.amazon.com/vi/elasticloadbalancing/application-load-balancer](https://aws.amazon.com/vi/elasticloadbalancing/application-load-balancer/)[aws.amazon.com/vi/ec2](https://aws.amazon.com/vi/ec2/) |

### Kết quả đạt được tuần 3:

- Hoàn thiện được luồng hỏi đáp RAG gồm retrieval, prompt và generation.
- Giao diện Chainlit được tích hợp với RAG core.
- Ứng dụng có khả năng nhận câu hỏi và trả lời dựa trên dữ liệu pháp luật.
- Có bản thiết kế kiến trúc AWS ban đầu cho hệ thống.
- Trao đổi với thành viên nhóm về luồng xử lý RAG và cách chia nhiệm vụ giữa phần dữ liệu, backend và giao diện.
- Review kết quả retrieval và phản hồi của chatbot cùng nhóm để xác định hướng cải thiện.
