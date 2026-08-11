---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---
# PHÁT HIỆN VÀ NGĂN CHẶN GIAN LẬN TÀI LIỆU TRONG VÀI GIÂY VỚI INSCRIBE VÀ AMAZON BEDROCK

Trong ngành tài chính và fintech, việc xác minh tính chân thực của các tài liệu như sao kê ngân hàng, bảng lương, tờ khai thuế hay giấy tờ tùy thân là bước then chốt trong quy trình thẩm định tín dụng và quản lý rủi ro. Tuy nhiên, sự phát triển bùng nổ của các công cụ chỉnh sửa kỹ thuật số và Generative AI đã khiến thủ đoạn gian lận tài liệu trở nên vô cùng tinh vi. Kẻ gian có thể dễ dàng sửa đổi con số, tên tuổi, số dư tài khoản hay lịch sử giao tiếp mà không để lại vết phỏng hay lỗi định dạng rõ ràng.

Để giải quyết thách thức này, Inscribe—nền tảng phát hiện gian lận tài liệu hàng đầu—đã hợp tác với AWS để tích hợp **Amazon Bedrock** vào hệ thống phân tích của mình. Sự kết hợp này cho phép xử lý và kiểm tra hàng triệu tài liệu tài chính phức tạp chỉ trong vài giây, giúp các tổ chức tài chính ngăn chặn rủi ro gian lận ngay từ khâu tiếp nhận.

Bài viết này sẽ phân tích lý do tại sao các phương pháp kiểm tra tài liệu truyền thống không còn hiệu quả, cách Inscribe ứng dụng Amazon Bedrock để phân tích ngữ cảnh tài liệu và cấu trúc kiến trúc triển khai giải pháp trên AWS.

## Thách thức: Tại sao các công cụ kiểm tra tài liệu truyền thống thất bại trước gian lận hiện đại?

Trước đây, các quy trình kiểm duyệt tài liệu thường phụ thuộc vào công nghệ OCR (Optical Character Recognition) cơ bản kết hợp với quy tắc (rule-based) hoặc kiểm tra thủ công bởi chuyên viên thẩm định. Phương pháp này bộc lộ nhiều hạn chế nghiêm trọng khi đối mặt với các thủ đoạn gian lận thế hệ mới:

1. **Gian lận về mặt logic và số liệu:** Kẻ gian không chỉ chỉnh sửa ảnh mà còn thay đổi các con số tổng, số dư cuối kỳ hoặc danh sách giao dịch. Quy trình OCR truyền thống chỉ đọc được văn bản chứ không kiểm tra được tính logic toán học xuyên suốt giữa các dòng giao dịch.
2. **Quy trình thẩm định thủ công chậm chạp:** Việc giao cho chuyên viên đọc và đối chiếu từng trang tài liệu tốn từ nhiều giờ đến hàng ngày, tạo ra điểm nghẽn lớn trong trải nghiệm đăng ký dịch vụ của khách hàng.
3. **Sự biến hóa của tài liệu tổng hợp (Synthetic Documents):** Kẻ tấn công có thể dùng Generative AI để tạo ra các tài liệu hoàn toàn mới với định dạng chuẩn mực, vượt qua các bộ lọc đối soát mẫu (template matching) cố định.

## Giải pháp Inscribe kết hợp Amazon Bedrock là gì?

Inscribe tích hợp các mô hình ngôn ngữ lớn (Foundation Models) tiên tiến trên **Amazon Bedrock** (như Anthropic Claude) vào nền tảng kiểm tra rủi ro của mình. Thay vì chỉ quét ký tự bề mặt, hệ thống tận dụng khả năng suy luận ngữ cảnh sâu của LLM để "thấu hiểu" cấu trúc, logic toán học và tính toàn vẹn của dữ liệu tài chính.

## Các đặc điểm cốt lõi của giải pháp:

* **Kiểm tra tính hợp lý toán học và ngữ cảnh (Contextual & Mathematical Verification):** LLM trên Amazon Bedrock tự động tính toán lại các phép cộng, trừ số dư, đối chiếu tỷ lệ thuế, lương thực nhận và phát hiện các điểm mâu thuẫn ẩn trong báo cáo.
* **Xử lý đa dạng loại tài liệu:** Phân tích linh hoạt trên nhiều biểu mẫu tài chính khác nhau như sao kê ngân hàng (bank statements), bảng lương (paystubs), tờ khai thuế (tax forms) và giấy tờ cá nhân mà không cần cấu hình mẫu cứng cho từng ngân hàng hay tổ chức phát hành.
* **Giải thích nguyên nhân gian lận bằng ngôn ngữ tự nhiên:** Hệ thống không chỉ trả về điểm số rủi ro mà còn đưa ra lý do chi tiết (ví dụ:  *"Số dư đầu kỳ không khớp với tổng giao dịch trong tháng"* ), giúp chuyên viên ra quyết định nhanh chóng.
* **Xử lý theo thời gian thực (Real-time Processing):** Rút ngắn thời gian phân tích tài liệu phức tạp từ nhiều giờ xuống chỉ còn vài giây.

## Tổng quan kiến trúc pipeline phân tích gian lận của Inscribe trên AWS

![1786422614378](image/_index.vi/1786422614378.png)

Kiến trúc giải pháp được thiết kế theo mô hình hoàn toàn tự động, kết hợp các dịch vụ điện toán đám mây của AWS để đảm bảo hiệu năng và độ tin cậy cao:

1. **Tiếp nhận tài liệu (Document Ingestion):** Khách hàng tải tài liệu (PDF, hình ảnh) lên hệ thống thông qua API được bảo mật, dữ liệu được lưu trữ an toàn tại  **Amazon S3** .
2. **Trích xuất và Tiền xử lý (Extraction & Layout Analysis):** Nền tảng Inscribe trích xuất cấu trúc văn bản, vị trí các trường dữ liệu và siêu dữ liệu (metadata) của tệp tin để phát hiện dấu vết chỉnh sửa phần mềm (như Photoshop hay Acrobat).
3. **Phân tích ngữ cảnh bằng Amazon Bedrock:** Dữ liệu trích xuất cùng với các prompt chuyên biệt được gửi tới các mô hình LLM trên  **Amazon Bedrock** . Mô hình sẽ thực hiện đối soát logic, kiểm tra tính nhất quán của giao dịch và phát hiện các bất thường về mặt nội dung.
4. **Chấm điểm rủi ro và Xuất kết quả (Risk Scoring & Decisioning):** Hệ thống tổng hợp các tín hiệu gian lận về hạ tầng tệp tin và tín hiệu ngữ cảnh từ Bedrock để đưa ra chỉ số rủi ro cuối cùng, tự động phê duyệt hoặc chuyển sang luồng kiểm tra thủ công.

## Đặc điểm triển khai và Vận hành

* **Bảo mật và Tuân thủ dữ liệu nghiêm ngặt:** Sử dụng Amazon Bedrock đảm bảo dữ liệu nhạy cảm của khách hàng tài chính không bị sử dụng để huấn luyện lại các mô hình công cộng, tuân thủ các tiêu chuẩn bảo mật khắt khe như SOC 2 và GDPR.
* **Khả năng mở rộng Serverless:** Tận dụng hạ tầng quản lý hoàn toàn của AWS giúp Inscribe dễ dàng mở rộng quy mô để xử lý hàng triệu tài liệu trong các đợt cao điểm tín dụng mà không lo tắc nghẽn hệ thống.
* **Tối ưu hóa chi phí và Năng suất:** Giảm đáng kể khối lượng công việc kiểm tra thủ công cho đội ngũ Risk & Operations, giúp doanh nghiệp cắt giảm chi phí vận hành và tăng tỷ lệ chuyển đổi khách hàng.

## Kết quả đo lường được

Ứng dụng Amazon Bedrock giúp Inscribe mang lại những kết quả vượt trội cho các khách hàng tổ chức tài chính:

* **Tốc độ xử lý siêu nhanh:** Giảm thời gian xác minh tài liệu xuống dưới  **vài giây** , cho phép phê duyệt khoản vay hoặc mở tài khoản tức thì.
* **Tăng tỷ lệ phát hiện gian lận:** Nhận diện chính xác các trường hợp gian lận tinh vi mà mắt thường và các công cụ OCR truyền thống hoàn toàn bỏ sót.
* **Tối ưu chi phí vận hành:** Cắt giảm đến **80%** thời gian xem xét thủ công của chuyên viên thẩm định.

## Kết luận

Việc Inscribe ứng dụng Amazon Bedrock vào quy trình phát hiện gian lận tài liệu chứng minh sức mạnh thực tế của Generative AI trong việc giải quyết các bài toán rủi ro phức tạp. Bằng cách kết hợp phân tích siêu dữ liệu tệp tin với khả năng suy luận ngữ cảnh của LLM trên hạ tầng an toàn của AWS, giải pháp này giúp các tổ chức tài chính chủ động bảo vệ hệ thống trước các thủ đoạn gian lận ngày càng tinh vi.


**Link bài viết gốc:** [https://aws.amazon.com/vi/blogs/machine-learning/how-inscribe-uses-amazon-bedrock-to-stop-document-fraud-in-seconds/](https://aws.amazon.com/vi/blogs/machine-learning/how-inscribe-uses-amazon-bedrock-to-stop-document-fraud-in-seconds/)
