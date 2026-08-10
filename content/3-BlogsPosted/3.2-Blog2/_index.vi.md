---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# PHÁT HIỆN VÀ XỬ LÝ LỖI NGẦM TRONG AI AGENTS VỚI AMAZON BEDROCK AGENTCORE OPTIMIZATION

Khi triển khai các hệ thống AI Agent ở quy mô lớn cho doanh nghiệp, một trong những thách thức lớn nhất mà các kỹ sư phải đối mặt chính là "lỗi ngầm" (silent failures). Bảng điều khiển (dashboard) vẫn hiển thị màu xanh hoàn hảo: tỷ lệ hoàn thành 99%, độ trễ ổn định và không có phản hồi lỗi từ hạ tầng. Tuy nhiên, khách hàng vẫn âm thầm phản ánh về việc đơn hàng không được thực thi, sản phẩm báo "còn hàng" dù API kho bị timeout, hoặc các bước phê duyệt quan trọng bị AI vô tình bỏ qua.

Để giải quyết triệt để vấn đề này, AWS đã giới thiệu tính năng Insights trong **Amazon Bedrock AgentCore Optimization**. Kỹ thuật này giúp chuyển dịch mô hình giám sát từ việc tra vết (trace inspection) bị động sang phát hiện các mẫu hành vi bất thường một cách chủ động, giúp phát hiện, giải thích và sắp xếp thứ tự ưu tiên xử lý cho cả những lỗi không bao giờ phát ra tín hiệu báo lỗi.

Bài viết này sẽ phân tích lý do tại sao các công cụ giám sát truyền thống gặp rào cản, cơ chế phân tích sâu của Amazon Bedrock AgentCore Optimization và cách ứng dụng giải pháp này trong thực tế.

## Thách thức: Tại sao các công cụ giám sát truyền thống thất bại trước "Silent Failures"?

Trong môi trường vận hành thực tế, các AI Agent hoàn thành tác vụ theo góc nhìn của hệ thống (mã phản hồi 200, vượt qua kiểm tra health check), nhưng lại thất bại về mặt hành vi nghiệp vụ. Những lỗi này không phát ra ngoại lệ (exceptions) hay mã lỗi HTTP, do đó chúng hoàn toàn "vô hình" trước các hệ thống giám sát hạ tầng truyền thống và chỉ bộc lộ khi người dùng cuối khiếu nại.

Bên cạnh đó, khi hệ thống AI Agent xử lý hàng nghìn phiên làm việc (sessions) mỗi ngày, các kỹ sư thường gặp phải 2 điểm nghẽn chính:

1. **Rào cản về vết truy vết (Trace Noise):** Lỗi hành vi không thể phát hiện nếu chỉ nhìn vào từng log riêng lẻ. Việc xem xét thủ công từng vết trace chỉ cho biết điều gì đã xảy ra trong một phiên đơn lẻ, chứ không thể trả lời câu hỏi liệu đây là lỗi hệ thống ảnh hưởng đến 30% lưu lượng hay chỉ là một trường hợp góc (edge case) tác động đến 3 phiên.
2. **Liệt ca ưu tiên (Priority Paralysis):** Khi hàng trăm lỗi nhỏ tích lũy trong các phiên làm việc, đội ngũ phát triển thường phải phân loại lỗi theo cảm tính mà không có số liệu cụ thể về quy mô ảnh hưởng của từng nhóm lỗi.

## Giải pháp Amazon Bedrock AgentCore Optimization là gì?

Amazon Bedrock AgentCore Optimization cung cấp tính năng **Insights** hoạt động ở lớp phía trên của hệ thống giám sát hiện có. Thay vì chỉ thu thập log thô, AgentCore Insights tiếp nhận dữ liệu trace và chuyển đổi chúng thành trí tuệ hành vi (behavioral intelligence) có thể hành động được.
Tính năng này cho phép doanh nghiệp đánh giá toàn diện các mô hình tương tác của Agent ở quy mô lớn, tự động phát hiện các điểm sai lệch trong logic xử lý mà không cần phải cài đặt thủ công các bộ lọc hay quy tắc phân loại từ trước.

## Các đặc điểm cốt lõi của AgentCore Optimization:

![1786382920200](image/_index.vi/1786382920200.png)

* **Tự động gom nhóm và phát hiện mẫu lỗi (Ranked Failure Pattern Discovery)**: Phân tích hàng trăm phiên làm việc và gom chúng thành các cụm (clusters) lỗi hành vi, đi kèm giải thích nguyên nhân gốc (root cause analysis) tổng hợp cho từng cụm mà không cần mở từng trace riêng lẻ.
* **Sắp xếp ưu tiên theo mức độ ảnh hưởng:** Các mẫu lỗi được xếp hạng trực tiếp theo tỷ lệ phần trăm phiên làm việc bị ảnh hưởng, giúp kỹ sư phân biệt ngay lập tức giữa lỗi hệ thống nghiêm trọng và lỗi góc hiếm gặp.
* **Phân tích ý định người dùng (User Intent Analysis):** Bóc tách phân bố thực tế về những gì người dùng yêu cầu, giúp phát hiện các khoảng trống về khả năng xử lý (coverage gaps) hoặc các yêu cầu nằm ngoài phạm vi thiết kế của Agent.
* **Giám sát chủ động thay vì thụ động:** Dịch chuyển từ việc đọc vết trace thủ công khi có sự cố sang việc chủ động nắm bắt toàn bộ bức tranh hành vi của Agent theo thời gian thực.

## Tổng quan kiến trúc pipeline phân tích trên Amazon Bedrock AgentCore

![1786381807709](image/_index.vi/1786381807709.png)

Quy trình phân tích đầu-cuối (end-to-end) của AgentCore Optimization diễn ra tự động thông qua các bước cốt lõi:

1. **Trích xuất thuộc tính phiên (Session Attribute Extraction):** Hệ thống thu thập dữ liệu trace từ các phiên làm việc của Agent và trích xuất các thuộc tính hành vi (như chuỗi hành động, lời gọi công cụ tool calls, trạng thái phản hồi).
2. **Phân cụm độc lập (Independent Clustering):** Mỗi phương pháp phân tích phiên sẽ gom nhóm các thuộc tính một cách độc lập để tìm ra các mô hình tương đồng giữa hàng ngàn tương tác.
3. **Tổng hợp và Tóm tắt giải thích (Cluster Summarization & Interpretation):** Tạo ra một bản tóm tắt nguyên nhân duy nhất cho mỗi cụm lỗi, mô tả chính xác vấn đề xảy ra đủ chi tiết để kỹ sư có thể hành động ngay.
4. **Xếp hạng và Báo cáo Insights (Ranked Insights Reporting):** Sắp xếp các cụm theo quy mô tác động, xuất ra báo cáo trực quan giúp đội ngũ phát triển tập trung nguồn lực sửa chữa các lỗi có ảnh hưởng lớn nhất.

## Đặc điểm triển khai và Vận hành

* **Tận dụng hạ tầng giám sát có sẵn:** AgentCore Insights hoạt động dựa trên dữ liệu trace đã được thu thập, không yêu cầu thay đổi mã nguồn hoặc cấu trúc của AI Agent hiện tại.
* **Khả năng mở rộng quy mô lớn:** Hệ thống tự động phân tích hàng ngàn phiên làm việc song song trên hạ tầng quản lý hoàn toàn của AWS, loại bỏ gánh nặng tự duy trì mô hình phân tích hay hạ tầng tính toán phức tạp.
* **Tối ưu năng suất đội ngũ kỹ thuật:** Giúp các kỹ sư loại bỏ hàng giờ làm việc thủ công tra cứu log, tập trung vào việc cải thiện prompt, bổ sung công cụ (tools) hoặc tinh chỉnh logic của Agent.

## Kết quả đo lường được

Việc áp dụng Amazon Bedrock AgentCore Optimization mang lại những giá trị thiết thực cho quy trình vận hành AI của doanh nghiệp:

* **Khoanh vùng sự cố nhanh chóng:** Giảm thời gian phát hiện và phân tích nguyên nhân gốc của các lỗi ngầm từ nhiều tuần xuống chỉ còn vài phút.
* **Tối ưu hóa nguồn lực phát triển:** Giúp đội ngũ kỹ thuật ưu tiên giải quyết đúng các lỗi ảnh hưởng đến số lượng lớn người dùng thay vì lãng phí thời gian vào các lỗi đơn lẻ.
* **Nâng cao độ tin cậy của Agent:** Đảm bảo các AI Agent hoạt động đúng theo thiết kế nghiệp vụ, hạn chế tối đa các rủi ro về mặt trải nghiệm khách hàng và vận hành doanh nghiệp.

## Kết luận

Amazon Bedrock AgentCore Optimization mở ra một bước tiến mới trong việc quản trị và tối ưu hóa hệ thống AI Agent ở quy mô doanh nghiệp. Bằng cách kết hợp giữa phân tích hành vi nâng cao và tự động hóa gom nhóm lỗi, giải pháp này giúp doanh nghiệp làm chủ các "lỗi ngầm" phức tạp, đảm bảo hệ thống AI không chỉ chạy ổn định về hạ tầng mà còn chính xác về nghiệp vụ.

**Link bài viết gốc:** [aws.amazon.com/vi/blogs/machine-learning/detecting-silent-agent-failures-with-amazon-bedrock-agentcore-optimization](https://aws.amazon.com/vi/blogs/machine-learning/detecting-silent-agent-failures-with-amazon-bedrock-agentcore-optimization/)
