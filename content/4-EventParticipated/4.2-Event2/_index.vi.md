---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---
# Bài thu hoạch “Agent Forge - Deepdive Day 1”

### Mục Đích Của Sự Kiện

* Định nghĩa rõ ràng về Agentic AI, hệ thống đa tác tử (Multi-Agent System) và cách đánh giá các mức độ tự chủ của mô hình trí tuệ nhân tạo.
* Khám phá phương pháp xây dựng, mở rộng và chuẩn hóa một hệ thống AI từ bước khái niệm (Proof of Concept) sang môi trường thực tế của doanh nghiệp (Production).
* Đi sâu vào kiến trúc cốt lõi của nền tảng Amazon Bedrock Agent Core thông qua các thành phần: Runtime Environment, Identity (Định danh) và Gateway.

### Danh Sách Diễn Giả

* **Nghĩa** - Chuyên gia từ AWS, phụ trách chính việc phân tích chuyên sâu các kiến thức lý thuyết về Agent Core.
* **Hải Anh** - Chuyên gia từ AWS (phụ trách phần thực hành chuyên môn tiếp nối của sự kiện).

### Nội Dung Nổi Bật

#### Hệ Sinh Thái Agentic AIưa ra các ảnh hưởng tiêu cực của kiến trúc ứng dụng

* **Bản chất của Agentic AI:** Là những hệ thống phần mềm có mức độ tự chủ cao, được trang bị khả năng tự suy luận (reasoning), lập kế hoạch (planning) và tự động thực thi chuỗi tác vụ phức tạp.
* **Cấp độ tự chủ:** Thay đổi linh hoạt từ các Trợ lý đơn giản (Simple Assistant), đi qua các luồng quy trình được kiểm soát (Deterministic Workflow), cho đến hệ thống Multi-Agent nơi các Agent có thể tự phân chia công việc và kết nối với nhau.
* **Giao thức kết nối mới:** Để tối ưu hóa, hệ sinh thái AI hiện đại áp dụng các giao thức tiên tiến như MCP (Model Context Protocol - để Agent giao tiếp với Tool) và A2A (Agent-to-Agent).

#### Chuyển đổi sang kiến trúc ứng dụng mới - Microservice Architecture

Chuyển đổi thành hệ thống modular – từng chức năng là một **dịch vụ độc lập** giao tiếp với nhau qua **sự kiện** với 3 trụ cột cốt lõi:

- **Queue Management**: Xử lý tác vụ bất đồng bộ
- **Caching Strategy:** Tối ưu performance
- **Message Handling:** Giao tiếp linh hoạt giữa services

#### Domain-Driven Design (DDD)

- **Phương pháp 4 bước**: Xác định domain events → sắp xếp timeline → identify actors → xác định bounded contexts
- **Case study bookstore**: Minh họa cách áp dụng DDD thực tế
- **Context mapping**: 7 patterns tích hợp bounded contexts

#### Event-Driven Architecture

- **3 patterns tích hợp**: Publish/Subscribe, Point-to-point, Streaming
- **Lợi ích**: Loose coupling, scalability, resilience
- **So sánh sync vs async**: Hiểu rõ trade-offs (sự đánh đổi)

#### Compute Evolution

- **Shared Responsibility Model**: Từ EC2 → ECS → Fargate → Lambda
- **Serverless benefits**: No server management, auto-scaling, pay-for-value
- **Functions vs Containers**: Criteria lựa chọn phù hợp

#### Amazon Q Developer

- **SDLC automation**: Từ planning đến maintenance
- **Code transformation**: Java upgrade, .NET modernization
- **AWS Transform agents**: VMware, Mainframe, .NET migration

### Những Gì Học Được

#### Tư Duy Thiết Kế

- **Business-first approach**: Luôn bắt đầu từ business domain, không phải technology
- **Ubiquitous language**: Importance của common vocabulary giữa business và tech teams
- **Bounded contexts**: Cách identify và manage complexity trong large systems

#### Kiến Trúc Kỹ Thuật

- **Event storming technique**: Phương pháp thực tế để mô hình hóa quy trình kinh doanh
- Sử dụng **Event-driven communication** thay vì synchronous calls
- **Integration patterns**: Hiểu khi nào dùng sync, async, pub/sub, streaming
- **Compute spectrum**: Criteria chọn từ VM → containers → serverless

#### Chiến Lược Hiện Đại Hóa

- **Phased approach**: Không rush, phải có roadmap rõ ràng
- **7Rs framework**: Nhiều con đường khác nhau tùy thuộc vào đặc điểm của mỗi ứng dụng
- **ROI measurement**: Cost reduction + business agility

### Ứng Dụng Vào Công Việc

- **Áp dụng DDD** cho project hiện tại: Event storming sessions với business team
- **Refactor microservices**: Sử dụng bounded contexts để identify service boundaries
- **Implement event-driven patterns**: Thay thế một số sync calls bằng async messaging
- **Serverless adoption**: Pilot AWS Lambda cho một số use cases phù hợp
- **Try Amazon Q Developer**: Integrate vào development workflow để boost productivity

### Trải nghiệm trong event

Tham gia workshop **“GenAI-powered App-DB Modernization”** là một trải nghiệm rất bổ ích, giúp tôi có cái nhìn toàn diện về cách hiện đại hóa ứng dụng và cơ sở dữ liệu bằng các phương pháp và công cụ hiện đại. Một số trải nghiệm nổi bật:

#### Học hỏi từ các diễn giả có chuyên môn cao

- Các diễn giả đến từ AWS và các tổ chức công nghệ lớn đã chia sẻ **best practices** trong thiết kế ứng dụng hiện đại.
- Qua các case study thực tế, tôi hiểu rõ hơn cách áp dụng **Domain-Driven Design (DDD)** và **Event-Driven Architecture** vào các project lớn.

#### Trải nghiệm kỹ thuật thực tế

- Tham gia các phiên trình bày về **event storming** giúp tôi hình dung cách **mô hình hóa quy trình kinh doanh** thành các domain events.
- Học cách **phân tách microservices** và xác định **bounded contexts** để quản lý sự phức tạp của hệ thống lớn.
- Hiểu rõ trade-offs giữa **synchronous và asynchronous communication** cũng như các pattern tích hợp như **pub/sub, point-to-point, streaming**.

#### Ứng dụng công cụ hiện đại

- Trực tiếp tìm hiểu về **Amazon Q Developer**, công cụ AI hỗ trợ SDLC từ lập kế hoạch đến maintenance.
- Học cách **tự động hóa code transformation** và pilot serverless với **AWS Lambda**, từ đó nâng cao năng suất phát triển.

#### Kết nối và trao đổi

- Workshop tạo cơ hội trao đổi trực tiếp với các chuyên gia, đồng nghiệp và team business, giúp **nâng cao ngôn ngữ chung (ubiquitous language)** giữa business và tech.
- Qua các ví dụ thực tế, tôi nhận ra tầm quan trọng của **business-first approach**, luôn bắt đầu từ nhu cầu kinh doanh thay vì chỉ tập trung vào công nghệ.

#### Bài học rút ra

- Việc áp dụng DDD và event-driven patterns giúp giảm **coupling**, tăng **scalability** và **resilience** cho hệ thống.
- Chiến lược hiện đại hóa cần **phased approach** và đo lường **ROI**, không nên vội vàng chuyển đổi toàn bộ hệ thống.
- Các công cụ AI như Amazon Q Developer có thể **boost productivity** nếu được tích hợp vào workflow phát triển hiện tại.

#### Một số hình ảnh khi tham gia sự kiện

![1785835930694](image/_index.vi/1785835930694.jpg)
