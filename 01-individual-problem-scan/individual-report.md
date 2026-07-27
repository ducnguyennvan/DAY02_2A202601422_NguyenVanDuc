# 01-Invididual Problem Scan

## Scan rộng
Pain point của nhân viên và chủ của chuỗi cửa hàng bán lẻ, có từ 2 chi nhánh trở lên
- Khoảng cách địa lí
- Chênh lệch số liệu
- Chênh lệch chất lượng phục vụ

| Stt | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Pain từ người khác | Chênh lệch phân phối mặt hàng giữa các chi nhánh. Có chi nhánh thừa hàng tồn kho trong khi có những chi nhánh hết hàng | Store manager (SM), Chủ chuỗi | Mất thời gian nhắn tin, gọi điện trao đổi hàng hoá |
| 2 | Lặp lại | So sánh doanh thu, chi phí thực tế mỗi ca (sáng, tối) | Chủ chuỗi, Quản lí khu vực | Mất nhiều thời gian check POS/sheet mỗi chi nhánh để kiểm tra |
| 3 | AI có thể tốt hơn | Khách phàn nàn dịch vụ/thái độ ở chi nhánh này nhưng chủ chuỗi không biết để xử lý đồng bộ | Chủ chuỗi, Trưởng ca | Review Google Maps/Social bị bỏ sót, 2–3 ngày sau mới phát hiện ra crisis |
| 4 | Tốn thời gian | Nhân viên chi nhánh mới làm sai giá/chương trình KM do bảng giá update chưa đồng bộ | Nhân viên thu ngân, Khách hàng | Khách cãi nhau tại thu ngân 15–20 phút/lần, tính sai tiền phải bù đắp |
| 5 | Tốn thời gian | Kiểm kê hàng hóa giữa kho trung tâm và các chi nhánh lệch số liệu (lệch sổ sách vs thực tế) | Kho tổng, SM các chi nhánh | Đóng cửa kiểm kê 1 lần/tháng, mất 4–6 tiếng/lần, phát hiện lệch nhưng không rõ nguyên nhân |
| 6 | Lặp lại | Duyệt chi tiêu khẩn cấp tại các chi nhánh (sửa bóng đèn, mua túi in, chi tiếp khách local) | SM, Chủ chuỗi | Chat Zalo xin duyệt lẻ tẻ 10–15 tin/ngày, dễ trôi tin, khó đối soát cuối tháng |
| 7 | Pain từ người khác | Thái độ phục vụ và tiêu chuẩn vệ sinh/trưng bày giữa chi nhánh chính và chi nhánh phụ không đồng đều | Chủ chuỗi, Khách hàng | chi nhánh gốc 9/10 điểm, chi nhánh mới mở chỉ đạt 6/10; chủ phải đi lượn từng nơi để "soi" |
| 8 | Lặp lại | Nhắc nhở và gom lịch xếp ca làm việc tuần mới cho nhân viên part-time ở các chi nhánh | SM các chi nhánh | Nhắn tin giục đăng ký ca 3–4 lần/tuần, trùng ca hoặc thiếu người giờ cao điểm |
| 9 | AI có thể tốt hơn | Không dự đoán được lượng NV cần thiết cho từng chi nhánh theo thời tiết/ngày lễ | SM, Chủ chuỗi | chi nhánh thì rảnh ngồi lướt điện thoại, chi nhánh thì quá tải khách bỏ về |
| 10 | Pain từ người khác | Nhân viên tự ý cho nợ/bán ngoài hệ thống POS tại chi nhánh xa chủ | Chủ chuỗi | Thất thoát dòng tiền, phát hiện muộn khi đối soát tiền mặt cuối thánng |

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Lệch tồn kho & Cân bằng hàng hóa giữa các Chi nhánh | Chi nhánh thừa - chi nhánh thiếu gây đọng vốn và mất doanh số | Tần suất cập nhật dữ liệu POS/Sheets giữa các chi nhánh có đủ "real-time" không |
|2 | Báo cáo Tổng hợp & So sánh Hiệu số đa chi nhánh | Chủ chuỗi mất nhiều thời gian nhất mỗi ca (sáng, chiều), càng mở thêm chi nhánh càng kiệt sức | Công thức tính KPI hiệu quả giữa các chi nhánh có cố định không |
|3 | Đồng bộ hóa Tiêu chuẩn Vận hành & Phản hồi Khách hàng | Vấn đề sống còn khi nhân rộng chuỗi: Chất lượng dịch vụ bị "pha loãng" khi mở rộng thêm nhiều chi nhánh | Khả năng thu thập feedback tự động từ Google/Social của từng chi nhánh |

# 02 — Problem Cards & Boundary Definition

## Problem Card 1: Điều phối & Cân bằng Tồn kho đa chi nhánh (Rank 1)

**Problem Statement:** Khi có từ 2 chi nhánh trở lên, tình trạng "chi nhánh A đứt hàng hotsale nhưng chi nhánh B lại ngâm hàng đọng vốn" diễn ra liên tục. SM phải chat thủ công vào nhóm chung để hỏi xin hàng, mất 1–2 ngày mới hoàn thành 1 lệnh luân chuyển nội bộ, khiến chuỗi mất trung bình 10–15% doanh số tiềm năng/tháng do hết hàng tại điểm bán.

**Metric:**
- **Primary Metric:** Giảm thời gian xử lý 1 lệnh luân chuyển hàng giữa 2 chi nhánh từ 24–48 giờ down xuống < 2 giờ.
- **Secondary Metric:** Giảm 50% tỷ lệ đứt hàng (Out-of-Stock) các SKU key tại từng chi nhánh.

**Boundary (In-Scope & Out-of-Scope):**
- **In-Scope:** Cảnh báo tự động khi chi nhánh A dưới định mức (Safety Stock) và chi nhánh B dư tồn kho; Tự động tạo Lệnh điều chuyển (Transfer Order) trình chủ chuỗi/SM duyệt.
- **Out-of-Scope:** Không tự động đặt hàng mới từ Nhà cung cấp (Vendor) bên ngoài.

**Lựa chọn giải pháp:** WORKFLOW (Automation)

**Lý do chọn:** Bài toán này hoàn toàn dựa trên dữ liệu định lượng và quy tắc kinh doanh rõ ràng (Số lượng tồn kho, ngưỡng định mức, vị trí kho). Không cần trí tuệ nhân tạo để suy luận mơ hồ. Workflow tự động chạy theo kịch bản: Trigger (Tồn kho chi nhánh A < Min & chi nhánh B > Max) -> Query POS -> Generate Draft Transfer Request -> Send App Notification for Approval. Đúng logic, chính xác 100%, xử lý tức thì.

## Problem Card 2: Báo cáo Tổng hợp & So sánh Hiệu số Chuỗi (Rank 2)

**Problem Statement:** Chủ chuỗi đang mất 60–90 phút mỗi tối để đăng nhập vào hệ thống của từng chi nhánh (hoặc đợi SM từng nơi gửi file), sau đó chép số liệu thủ công ra Excel để so sánh doanh thu, chi phí ca, và tỷ lệ chốt đơn. Việc này khiến báo cáo bị chậm, chủ chuỗi không kịp ra quyết định điều chỉnh chính sách bán hàng cho ngày hôm sau.

**Metric:**
- **Primary Metric:** Giảm thời gian tổng hợp báo cáo đa chi nhánh từ 90 phút down xuống 0 phút (Tự động gửi lúc 22h30).
- **Secondary Metric:** Tỷ lệ báo cáo trễ hạn/sai lệch số liệu giữa các chi nhánh = 0%.

**Boundary (In-Scope & Out-of-Scope):**
- **In-Scope:** Tự động quét dữ liệu từ các chi nhánh, nén lại thành 1 Dashboard/Bản tin tóm tắt trên Zalo/Telegram của Chủ chuỗi kèm so sánh % tăng trưởng giữa các chi nhánh.
- **Out-of-Scope:** Không làm thay nghiệp vụ kiểm toán thuế hay quyết toán tài chính năm.

**Lựa chọn giải pháp:** WORKFLOW (Automation)

**Lý do chọn:** Quy trình lấy số liệu từ các chi nhánh và cộng tổng/tính trung bình là kịch bản chuẩn hóa 100%. Dùng Workflow scheduled (hẹn giờ) để gọi API các điểm bán, gom dữ liệu và gửi thẳng về máy chủ chuỗi là phương án tiết kiệm nhất, chạy ổn định và không xảy ra sai số.

## Problem Card 3: Trợ lý Lắng nghe Feedback & Giám sát Tiêu chuẩn Chuỗi (Rank 3)

**Problem Statement:** Khi mở rộng thêm chi nhánh, chủ chuỗi không thể có mặt trực tiếp để giám sát. Chất lượng dịch vụ bị lệch: chi nhánh mới mở thường xuyên bị khách đánh giá 1-2 sao trên Google Maps/Facebook vì nhân viên thái độ hoặc phục vụ chậm, nhưng 3–4 ngày sau chủ chuỗi mới phát hiện ra, gây ảnh hưởng xấu tới uy tín thương hiệu chung.

**Metric:**
- **Primary Metric:** Giảm thời gian phát hiện và xử lý feedback tiêu cực từ 3 ngày down xuống < 15 phút.
- **Secondary Metric:** Tăng điểm đánh giá trung bình (Rating) của các chi nhánh phụ lên >= 4.5/5 sao.

**Boundary (In-Scope & Out-of-Scope):**
- **In-Scope:** Quét review/phản hồi từ Google Map/Fanpage của tất cả chi nhánh; phân tích sentiment (tích cực/tiêu cực); tự động phân loại lỗi (thái độ, chất lượng, giá) và cảnh báo khẩn cấp cho Chủ chuỗi & SM phụ trách chi nhánh đó.
- **Out-of-Scope:** Không tự động nhắn tin xin lỗi khách hàng khi chưa có sự xác nhận nguyên nhân từ SM.

**Lựa chọn giải pháp:** AGENT (LLM / AI Agent)

**Lý do chọn:** Phản hồi của khách hàng là văn bản tự nhiên, chứa nhiều cảm xúc, ẩn ý hoặc từ ngữ địa phương (ví dụ: "Đồ ăn tạm được nhưng bé thu ngân mặt như mất sổ gạo"). Rule hay Workflow thông thường không thể hiểu được ngữ cảnh này. Cần một AI Agent có khả năng xử lý ngôn ngữ tự nhiên (NLP/LLM) để đọc hiểu, đánh giá mức độ nghiêm trọng và trích xuất đúng bản chất vấn đề để báo cáo cho chủ chuỗi.
