---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---

# BÀI THU HOẠCH SỰ KIỆN: FCAJ COMMUNITY DAY ngày 23-05-2026

### Mục Đích Của Sự Kiện
Sự kiện nhằm mục đích tạo không gian để cộng đồng công nghệ giao lưu, kết nối và truyền cảm hứng cho nhau. Thông qua các phiên chia sẻ, sự kiện mong muốn trang bị cho người tham gia từ định hướng nghề nghiệp trong bối cảnh thị trường thay đổi, đến các kiến thức chuyên sâu về Cloud (AWS), tích hợp AI thực tiễn và tư duy triển khai hệ thống cho doanh nghiệp.

### Danh Sách Diễn Giả
- **Nguyễn Gia Hưng**: Solution Architect AWS Việt Nam, chia sẻ về tổng quan thị trường việc làm IT và định hướng kỹ năng cốt lõi.
- **Tịnh Trương**: Platform Engineer tại Gotam X, trình bày về tầm quan trọng của ngữ cảnh (Context) khi giao tiếp với AI và tư duy tránh lạm dụng tool.
- **Hải Anh**: Kỹ sư từ Pacific Việt Nam, giới thiệu giải pháp dùng Amazon Q để phân tích dữ liệu tự động.
- **Anh Tịnh**: DevOps Engineer, đi sâu vào Amazon CloudFront, bảo mật và tối ưu chi phí hạ tầng mạng.
- **Uyển & Thảo (Team UTM)**: Nhóm thí sinh chia sẻ kinh nghiệm thực chiến từ cuộc thi Hackathon 36 giờ với dự án UI Editor bằng AI.
- **Anh Đức**: Solution Architect – Cloud Kinetiss, phân tích kỹ thuật về tham số Temperature và bản chất không xác định (probabilistic) của AI.
- **Chị Vy**: Senior Business Systems Analyst, phân tích chuyên sâu về hệ thống Multi-Agent System trong môi trường Enterprise, cụ thể là bài toán đánh giá tín dụng Startup và chia sẻ một kinh nghiệm khi làm việc trong ngân hàng.

### Nội Dung Nổi Bật
- **Xu hướng việc làm & Kỹ năng cốt lõi**: AI làm giảm chi phí tạo phần mềm, dẫn đến lượng phần mềm bùng nổ, kéo theo nhu cầu khổng lồ về các kỹ sư biết vận hành, sửa lỗi (fix code) và duy trì hệ thống. Bằng đại học, kiến thức nền tảng và việc xây dựng sản phẩm thực tế để giải quyết bài toán doanh nghiệp là yêu cầu bắt buộc hiện nay.
- **Tối ưu LLM & Prompt**: Việc nhồi nhét mã nguồn vô tội vạ ("Internet Builder") khiến AI bị mất ngữ cảnh. Kể cả khi thiết lập độ ngẫu nhiên của AI (temperature = 0), kết quả trả về vẫn có thể khác nhau ở mỗi lần chạy do quá trình tối ưu hóa suy luận (inference optimization) của nhà cung cấp API và sai số phần cứng.
- **Tối ưu hạ tầng AWS**: Việc sử dụng phương pháp tính giá cố định (Flat-rate pricing) của Amazon CloudFront giúp doanh nghiệp tránh rủi ro "hóa đơn khổng lồ" do lưu lượng truy cập tăng vọt hoặc bị tấn công DDoS.
- **Kiến trúc Multi-Agent trong Doanh nghiệp**: Thay vì dùng một con AI xử lý mọi việc, hệ thống doanh nghiệp cần nhiều AI đóng các vai trò khác nhau (nhân viên phân tích tài chính, nhân viên đánh giá rủi ro...) để vượt qua giới hạn bộ nhớ ngữ cảnh.

### Những Gì Học Được
- **Không phó mặc hoàn toàn cho AI**: Nếu chỉ dùng AI bằng cách "Ctrl C, Ctrl V" mù quáng mà không hiểu kiến trúc phần mềm, hệ thống sẽ gãy đổ và rất khó bảo trì.
- **Tầm quan trọng của Bảo mật (Security) & Tuân thủ (Compliance)**: Trong môi trường Enterprise, bảo mật dữ liệu, kiểm soát luồng thông tin (guardrails) chống bị bơm mã độc (Prompt Injection) và quản lý lưu vết (audit trail) quan trọng hơn cả sức mạnh của công nghệ AI.
- **Chiến lược Hackathon**: Phải biết kiềm chế mong muốn thêm quá nhiều tính năng (over generation) trong thời gian ngắn; cần tập trung giải quyết triệt để một vấn đề cốt lõi nhất mang lại giá trị thực tế.

### Ứng Dụng Vào Công Việc
- **Cung cấp ngữ cảnh chuẩn xác cho AI**: Bổ sung các thông tin riêng biệt của dự án, công ty (blueprint, style code) vào Prompt thay vì chỉ hỏi những câu chung chung để nhận được phản hồi chất lượng hơn.
- **Thiết lập các chốt chặn AI (Guardrails)**: Áp dụng kỹ thuật kiểm tra và lọc cả dữ liệu đầu vào lẫn kết quả đầu ra của AI trước khi trả về cho hệ thống, đảm bảo không rò rỉ dữ liệu nhạy cảm.
- **Xây dựng giải pháp phải đi từ người dùng (Working Backward)**: Luôn phải trả lời được câu hỏi "Ai xài? Xài cái gì? Tại sao phải xài?" trước khi xin kinh phí triển khai công nghệ mới.

### Trải nghiệm trong event
Sự kiện diễn ra với không khí cực kỳ thực tế và thẳng thắn. Thay vì chỉ nói về những điều hoa mỹ của AI, các diễn giả mang đến góc nhìn chân thực của người làm nghề: từ những hóa đơn "khủng" do lỡ tay cấu hình sai, sự cố copy code AI gây lỗi hệ thống, cho đến sức ép bảo mật từ các ngân hàng lớn. Trải nghiệm lớn nhất là sự dịch chuyển tư duy: Xây dựng hệ thống không chỉ cần chạy được, mà phải chạy một cách an toàn, đáng tin cậy và thực sự phục vụ người dùng.

### Một Số Hình Ảnh Tại Sự Kiện

![Hình ảnh 1](/images/4-EventParticipated/4.2-Event2/media__1782219173007.png)
![Hình ảnh 2](/images/4-EventParticipated/4.2-Event2/media__1782219187039.png)
![Hình ảnh 3](/images/4-EventParticipated/4.2-Event2/media__1782219199498.png)
![Hình ảnh 4](/images/4-EventParticipated/4.2-Event2/media__1782219204672.png)
![Hình ảnh 5](/images/4-EventParticipated/4.2-Event2/media__1782219212668.png)
![Hình ảnh 6](/images/4-EventParticipated/4.2-Event2/media__1782219648962.png)
![Hình ảnh 7](/images/4-EventParticipated/4.2-Event2/media__1782219655208.png)
![Hình ảnh 8](/images/4-EventParticipated/4.2-Event2/media__1782219660218.png)
![Hình ảnh 9](/images/4-EventParticipated/4.2-Event2/media__1782219665248.png)
