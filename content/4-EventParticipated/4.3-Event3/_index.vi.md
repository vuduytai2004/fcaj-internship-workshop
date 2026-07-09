---
title: "Event 3"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# BÀI THU HOẠCH SỰ KIỆN: FCAJ COMMUNITY DAY NGÀY 27-06-2026

### Mục Đích Của Sự Kiện
Sự kiện là diễn đàn quy tụ các chuyên gia công nghệ từ nhiều doanh nghiệp hàng đầu để chia sẻ kinh nghiệm thực tiễn và các giải pháp kỹ thuật chuyên sâu. Mục đích chính là cung cấp góc nhìn thực tế về lộ trình sự nghiệp trong kỷ nguyên AI và các phương án tối ưu hóa vận hành doanh nghiệp dựa trên nền tảng Cloud.

### Danh Sách Diễn Giả
- **Steve Trần** (CTO Founder CloudThinker): Chia sẻ về lộ trình sự nghiệp và tác động của AI đối với Cloud Engineering, cũng như giải pháp nền tảng Agentic.
- **Danh Hoàng Hiếu Nghị** (AI Engineer Revve Cloud), **Kiệt Trần** (AI Engineer AWS Student Builder Group) & **Trung Đỗ** (CEO Revve AI): Phân tích thách thức và giải pháp kiến trúc Voice AI cho tiếng Việt.
- **Chị Bảo** (Cloud Engineer Cloud Kinetic) & **Nguyên Nguyễn** (Cloud Engineer Cloud Kinetic): Trình bày về AWS DevOps AI Agent giúp tối ưu hóa vận hành hệ thống và giảm thời gian phục hồi (MTTR).
- **Trường (Wayne)** (AI Solution Sales Noventiq) & **Minh Anh** (Solution Sales Noventiq): Giới thiệu ứng dụng Amazon Q trong tự động hóa quy trình quản trị nhân sự (HR).
- **Toàn Nguyễn** (Security Builder) & **Danh Hoàng Hiếu Nghị** (Ai Engineer Revve Cloud): Phân tích kỹ thuật và chi phí khi thiết lập bảo mật kết nối Private cho Amazon Q.

### Nội Dung Nổi Bật
- **Lộ trình sự nghiệp & Tác động của AI**: Thị trường đang ngừng tuyển dụng ồ ạt vị trí Junior, ưu tiên Senior làm chủ AI. Nền tảng Agentic giúp tự động hóa xử lý sự cố (Incident), Code Review và FinOps (tối ưu chi phí), giải quyết bài toán "Nợ hiện đại hóa". Kiến trúc Multi-Agent khắc phục nhược điểm loãng ngữ cảnh của Single Agent.
- **Voice AI cho tiếng Việt**: So với kiến trúc Sound-to-Sound (ưu thế tiếng Anh), kiến trúc SCT-LLM-TTS (Speech-to-Text-to-LLM-to-Speech) tối ưu hơn cho tiếng Việt nhờ khả năng xử lý sắc thái ngôn ngữ và thiết lập Guardrails. Giải pháp đã thành công tại VPBank và VIB.
- **AWS DevOps AI Agent**: Khắc phục tình trạng dữ liệu giám sát phân tán và thời gian MTTR cao. AI Agent tự dựng sơ đồ cấu trúc hệ thống (Topology) để hiểu sâu ngữ cảnh, giúp giảm tới 77% thời gian MTTR (Case study tại Đại học WGU).
- **AI trong Quản trị Nhân sự (HR)**: Sử dụng Amazon Q kết hợp Local Zones tại Việt Nam để đảm bảo chủ quyền dữ liệu. Tự động hóa các khâu từ tạo JD, sàng lọc CV đến làm báo cáo trực quan.
- **Bảo mật kết nối Private**: Việc dùng Private Connection (VPC Connection, Interface Endpoint, Route 53 Resolver, ALB) kết nối MCP Server giúp ngăn chặn các cuộc tấn công DoS và Man-in-the-middle, đảm bảo dữ liệu lưu hành nội bộ an toàn.

### Những Gì Học Được
- **Về tư duy**: Tầm quan trọng của trải nghiệm thực tế từ sớm trước khi AI thay đổi tiêu chuẩn tuyển dụng. AI là công cụ khuếch đại năng lực, nhưng con người vẫn giữ vai trò quyết định cuối cùng (Human-in-the-loop) trong việc phê duyệt an toàn.
- **Về kỹ thuật**: Nền tảng quan sát (Observability) là bắt buộc; AI cần bằng chứng dữ liệu (Logs/Metrics/Traces) sạch để hoạt động chính xác. Kiến trúc Multi-Agent xử lý bài toán phức tạp tốt hơn Single Agent.
- **Về kỹ năng**: Tư duy thực thi (execution) ngay lập tức và tìm kiếm "Champion Customers" để giải quyết vấn đề thực tế quan trọng hơn việc chỉ dừng lại ở ý tưởng.

### Ứng Dụng Vào Công Việc
- **Ứng dụng Multi-Agent**: Xây dựng kiến trúc gồm nhiều AI Agent với vai trò khác nhau thay vì nhồi nhét vào một Agent để tránh loãng ngữ cảnh.
- **Bảo mật ứng dụng AI**: Bắt buộc thiết lập các kết nối mạng Private (VPC, Endpoint) thay vì Public Internet khi triển khai các dịch vụ AI (như Amazon Q) nội bộ để đảm bảo an toàn dữ liệu.
- **Tối ưu quy trình làm việc**: Áp dụng AI vào các khâu như phân tích Logs, viết tài liệu, sàng lọc dữ liệu để rút ngắn thời gian xử lý sự cố và tự động hóa những công việc thủ công lặp lại.

### Một Số Hình Ảnh Tại Sự Kiện
![Hình ảnh 1](/images/4-EventParticipated/4.3-Event3/image1.png)
![Hình ảnh 2](/images/4-EventParticipated/4.3-Event3/image2.png)
![Hình ảnh 3](/images/4-EventParticipated/4.3-Event3/image3.png)
![Hình ảnh 4](/images/4-EventParticipated/4.3-Event3/image4.png)
![Hình ảnh 5](/images/4-EventParticipated/4.3-Event3/image5.png)
![Hình ảnh 6](/images/4-EventParticipated/4.3-Event3/image6.jpg)
![Hình ảnh 7](/images/4-EventParticipated/4.3-Event3/image7.png)
![Hình ảnh 8](/images/4-EventParticipated/4.3-Event3/image8.jpg)
