# 02 — Group Problem Statement


## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|-----|-----------|-------------|--------------------|
| 1   | Nguyễn Minh Hiếu          |  2A202601816         |           Đầu tư         |
| 2   | Nguyễn Văn Đức          | 2A202601422            |           Đầu tư         |
| 3   | Đào Hải Đăng          | 2A202601814            |  Pitching                  |
| 4   | Vũ Xuân Đức          |  2A202601668           |   Đầu tư                 |
| 5   | Nguyễn Tuấn Trường          | 2A202601842            |  Pitching                  |

## Group convergence

Nhóm 5 người, mỗi người share top 3. Tổng cộng 15 candidates.

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Báo cáo & Tổng hợp thông tin | Weekly Report, Weekly Progress Report, Báo cáo Tổng hợp & So sánh Hiệu số đa chi nhánh, Extract Action Items sau họp | Gom thông tin từ nhiều nguồn rời rạc (Jira, Sheets, Slack, cuộc họp, POS) và viết báo cáo/tóm tắt cho người khác đọc. |
| Học tập & Soạn thảo tài liệu | Active Recall AI Tutor (Slide/PDF), Exercise Prep, Review PRD | Đọc tài liệu dài, bài giảng, PRD để tự tạo đề cương, câu hỏi ôn tập, chuẩn bị bài tập hoặc chỉ ra thiếu sót. |
| Tìm kiếm & Phản hồi thông tin | Slack Search, Search Engine, Chatbot AI, Gom & Chuẩn hóa thông báo | Tìm kiếm, truy xuất thông tin hoặc hỏi đáp tự động từ các nguồn dữ liệu bị phân mảnh. |
| Vận hành doanh nghiệp & Kiểm chuẩn | Lệch tồn kho & Cân bằng hàng hóa giữa các Chi nhánh, Đồng bộ hóa Tiêu chuẩn Vận hành & Phản hồi Khách hàng, Chuẩn hóa & Xếp TKB, Checklist Validation bài nộp | Kiểm chuẩn quy trình, xếp ca/xếp lịch, cân bằng nguồn lực và giám sát chất lượng vận hành. |

## Shortlist và score

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Weekly Report | 5 | 5 | 4 | 5 | 5 | 5 | 4 | 33 |
| Active Recall AI Tutor | 4 | 4 | 5 | 4 | 4 | 4 | 5 | 30 |
| Đồng bộ hóa Tiêu chuẩn Vận hành & Phản hồi Khách hàng | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 35 |

Nhóm chọn: **Đồng bộ hóa Tiêu chuẩn Vận hành & Phản hồi Khách hàng (Trợ lý Lắng nghe Feedback & Giám sát Tiêu chuẩn Chuỗi)**.

Vì sao chọn:
- Đây là vấn đề sống còn khi nhân rộng chuỗi: Chất lượng dịch vụ bị "pha loãng" và không đồng đều khi mở rộng thêm nhiều chi nhánh.
- Phản hồi từ khách hàng mang tính phi cấu trúc, giàu cảm xúc và tiếng lóng, rất thích hợp với thế mạnh xử lý ngôn ngữ tự nhiên của LLM/AI Agent.
- Workflow rõ ràng và có metric đo lường cực kỳ tốt (thời gian phát hiện/xử lý crisis và rating sao trung bình).

Vì sao không chọn các bài khác:
- **Weekly Report**: Dù có quy trình rõ ràng nhưng đây là bài toán khá phổ biến, tính thử thách về mặt công nghệ AI không cao bằng việc giải quyết phản hồi thực tế thời gian thực.
- **Active Recall AI Tutor**: Dù rất hữu ích cho học sinh nhưng việc truy cập, trích xuất dữ liệu chính xác từ các tài liệu PDF/Slide phức tạp chứa nhiều công thức, sơ đồ kỹ thuật và code block có độ rủi ro sai sót rất lớn, khó đảm bảo độ chính xác trong phạm vi một buổi lab ngắn.

## Quick validation

Nhóm hỏi nhanh các stakeholders.

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Phỏng vấn Chủ chuỗi | 3 | Cả 3 chủ chuỗi đều xác nhận họ không thể có mặt 24/7 ở chi nhánh phụ, và thường chỉ biết khách chê phục vụ khi crisis đã lan rộng trên Maps/Social. | 1 người cho biết họ thuê nhân viên trực check review nhưng vẫn bị sót review ngoài giờ hành chính. | Tập trung vào tính năng tự động hóa giám sát review thời gian thực (24/7) và cơ chế cảnh báo khẩn cấp (alerting). |
| Mini poll với các SM | 8 | 6/8 SM đồng ý rằng họ quá tải công việc vận hành tại cửa hàng, không có thời gian online để check review Maps liên tục. | Một số SM lo ngại AI có thể phân tích sentiment sai các trường hợp khách dùng từ ngữ mỉa mai, ẩn ý. | Thêm boundary nghiêm ngặt: AI Agent chỉ đóng vai trò phân tích, gắn thẻ và cảnh báo khẩn cấp cho SM, không tự ý đăng phản hồi khi chưa được duyệt. |

Insight sau validation:
```text
Pain thật không chỉ nằm ở việc "biết khách chê". Nó nằm ở tốc độ phát hiện đánh giá tiêu cực và độ chính xác trong việc phân loại lỗi để cảnh báo đúng SM chịu trách nhiệm xử lý tức thì trước khi crisis lan rộng.
```

## Research giải pháp

Nhóm tìm các hướng đã có sẵn, không giả định phải tự build từ đầu.

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Google Business Profile API | https://developers.google.com/my-business/content/reviews | Lấy dữ liệu review từ Google Maps | Dữ liệu chính xác, chính thống, thời gian thực | Chỉ cung cấp text thô, không phân tích sentiment hay phân loại lỗi | Dùng làm nguồn dữ liệu đầu vào (Input) cho AI Agent |
| Brand24 | https://brand24.com | Quét đề cập thương hiệu trên social media | Quét diện rộng trên nhiều nền tảng | Chi phí cao, phân tích tiếng Việt chưa tốt, không có cơ chế phân quyền cảnh báo theo chi nhánh | Phải tự xây dựng module phân tích NLP/LLM tối ưu cho tiếng Việt |
| Zendesk CRM | https://www.zendesk.com | Biến phản hồi thành ticket hỗ trợ | Quy trình xử lý, gán trách nhiệm rõ ràng | Cần nhập liệu thủ công hoặc cấu hình rule thô sơ, không tự động phân loại sâu sắc | AI Agent đóng vai trò cầu nối tự động phân tích và chuyển cảnh báo về Zalo/Telegram của đúng SM |

Research takeaway:
```text
Không tự động hóa hoàn toàn việc phản hồi khách hàng bằng AI. Giải pháp tối ưu là AI Agent đóng vai trò trợ lý thông minh: Quét review -> Phân tích sentiment & Phân loại lỗi -> Gửi cảnh báo khẩn cấp kèm draft phản hồi -> SM phê duyệt và phản hồi.
```

## Workflow before/after

Nội dung workflow:

```text
CURRENT STATE — 7 bước, 3 ngày (72 tiếng)

[1 Khách post review tiêu cực trên Google Maps/Social: 0']
→ [2 Review bị trôi, không ai nhận được thông báo ngay lập tức: 1-2 ngày]
→ [3 Chủ chuỗi hoặc SM tình cờ đọc được review xấu: 2-3 ngày]
→ [4 Chủ chuỗi chụp ảnh gửi vào group Zalo chung để hỏi sự tình: 15']
→ [5 SM liên hệ nhân viên ca đó để xác minh vụ việc tại cửa hàng: 2-4 tiếng]
→ [6 SM báo cáo lại cho chủ chuỗi phương án giải quyết: 1 tiếng]
→ [7 SM phản hồi chính thức xin lỗi khách hàng và đền bù: 1 tiếng]

FUTURE STATE — 6 bước, < 22 phút

[1 Khách post review tiêu cực trên Google Maps/Social: 0']
→ [2 API tự động quét review mới mỗi 5 phút: 5']  -- Rule
→ [3 AI Agent phân tích sentiment, phân loại lỗi và xác định chi nhánh: 1']  -- Agent step
→ [4 AI Agent tự động gửi cảnh báo và draft phản hồi qua Telegram/Zalo cho đúng SM: 1']  -- Agent step
→ [5 SM xem cảnh báo, xác minh nhanh với nhân viên tại chỗ: 10']  -- Human action
→ [6 SM duyệt draft phản hồi của AI hoặc chỉnh sửa để gửi khách: 5']  -- Human boundary

Fallback:
AI Agent phân loại sai sentiment (ví dụ: khen kháy mà tưởng tích cực) → Không gửi cảnh báo khẩn cấp → SM vẫn định kỳ quét thủ công vào cuối ngày để tránh bỏ sót.

Bottleneck mới:
Thời gian SM xác minh vụ việc thực tế với nhân viên tại cửa hàng. Đây là bottleneck chấp nhận được vì liên quan đến yếu tố con người và vận hành thực tế.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Tổng thời gian | 3 ngày | < 15–30 phút | Target chính để dập tắt crisis |
| Số bước | 7 | 6 | Giảm bước chờ đợi và trôi tin nhắn |
| Bước thủ công | 6/7 | 2/6 | SM chỉ tập trung vào xác minh và phê duyệt |
| Bottleneck chính | Phát hiện review chậm (3 ngày) | SM xác minh thực tế với nhân viên | Điểm kiểm soát chất lượng bằng con người |
| Risk mới | Không có AI hallucination | Có rủi ro AI phân loại sai hoặc draft phản hồi không khéo | Cần có SM kiểm duyệt trước khi post phản hồi |

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Chủ chuỗi cửa hàng bán lẻ và Store Managers (SM) của các chi nhánh. |
| **Workflow** | Khách hàng đăng review -> Hệ thống quét review -> Phân tích sentiment & lỗi -> Gửi cảnh báo cho SM & Chủ chuỗi -> SM xác minh & trả lời khách hàng. |
| **Bottleneck** | Phát hiện review tiêu cực quá muộn (mất 2-3 ngày) do kiểm tra thủ công, dẫn đến crisis lan rộng và ảnh hưởng thương hiệu. |
| **Impact** | Làm giảm điểm rating trung bình các chi nhánh phụ xuống dưới 4.0/5 sao, giảm lượng khách mới đến quán, mất doanh thu tiềm năng. |
| **Success Metric** | Giảm thời gian phát hiện và cảnh báo review xấu từ 3 ngày xuống < 15 phút; Tăng điểm rating trung bình các chi nhánh phụ lên >= 4.5/5 sao sau 2 tháng vận hành. |
| **Boundary** | Hệ thống không tự động đăng câu trả lời phản hồi khách hàng công khai; không thay SM quyết định phương án đền bù khách hàng. |

## Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Gửi thông báo cho SM mỗi khi có review mới bất kể nội dung tốt xấu | Đủ nếu số lượng review cực kỳ ít (1-2 review/tuần) | Quá nhiều review tích cực làm loãng thông tin, gây loãng cảnh báo (alert fatigue) và bị bỏ qua review xấu | Không chọn làm giải pháp chính |
| **Workflow** | Dùng công cụ lọc từ khóa cứng (ví dụ: "tệ", "dở", "chậm") để lọc review và gửi cảnh báo | Khách hàng chỉ dùng từ ngữ ngắn gọn, rõ ràng, không dùng ẩn ý hay từ địa phương | Bỏ sót các review mỉa mai, từ ngữ châm biếm ("phục vụ nhanh như rùa", "thái độ lồi lõm", "chờ cả thanh xuân") | Không chọn |
| **Agent** | AI Agent sử dụng LLM đọc hiểu ngữ cảnh review, phân tích sentiment, phân loại lỗi và tự động soạn draft phản hồi gửi SM duyệt | Cần thiết vì feedback tiếng Việt có độ mơ hồ cao, chứa nhiều từ viết tắt, tiếng lóng và sắc thái cảm xúc phức tạp | AI Agent có thể soạn draft phản hồi sai lệch hoặc bịa thông tin chính sách của cửa hàng | Chọn |

Mức chọn:
```text
Agent.
```

Vì sao:
- Phản hồi của khách hàng là ngôn ngữ tự nhiên, mang nhiều ẩn ý và cảm xúc phi cấu trúc, đòi hỏi khả năng đọc hiểu ngữ cảnh sâu sắc của LLM mà Rule hay Workflow đơn thuần không thể đáp ứng.
- AI Agent hỗ trợ đắc lực ở bước phân loại lỗi và đề xuất draft phản hồi, giúp giảm thiểu tối đa thời gian soạn thảo cho SM.
- Rủi ro được kiểm soát chặt chẽ thông qua bước phê duyệt thủ công của SM (Human-in-the-loop).

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Chủ chuỗi cửa hàng bán lẻ và Store Managers (SM) của các chi nhánh. |
| **Workflow** | Khách hàng đăng review -> Hệ thống quét dữ liệu -> AI Agent phân tích ngữ cảnh, sentiment & loại lỗi -> Đẩy cảnh báo qua Telegram/Zalo cho SM & Chủ chuỗi kèm draft phản hồi -> SM xác minh nội bộ & duyệt/sửa phản hồi gửi khách. |
| **Bottleneck** | Phát hiện review tiêu cực quá muộn (mất 2-3 ngày) do kiểm tra thủ công, gây trễ phản hồi xử lý crisis. |
| **Impact** | Uy tín thương hiệu bị ảnh hưởng tiêu cực, rating trung bình giảm, mất khách hàng tiềm năng. |
| **Success Metric** | Thời gian từ lúc review xấu xuất hiện đến khi SM nhận cảnh báo < 15 phút. Điểm rating các chi nhánh đạt >= 4.5/5 sao sau 2 tháng. |
| **Boundary** | AI tuyệt đối không tự động post phản hồi lên social/Google Maps mà không có sự phê duyệt của SM; chỉ sử dụng thông tin chính thống về chính sách đền bù của chuỗi. |
| **AI intervention point** | Sau khi quét được review mới, AI Agent can thiệp để đọc hiểu ngữ cảnh, phân tích cảm xúc, gán nhãn lỗi và tạo draft phản hồi. |
| **Mức chọn** | Agent (AI Agent phân tích ngữ cảnh phức tạp và soạn thảo văn bản). |
| **Rủi ro & người thật kiểm tra** | Risk: AI phân loại nhầm sắc thái cảm xúc hoặc soạn draft phản hồi thiếu chuẩn mực. Người thật kiểm tra: SM bắt buộc phải đọc lại review gốc và chỉnh sửa draft phản hồi trước khi gửi khách. |

## Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Đã xác định rõ SM/Chủ chuỗi và luồng xử lý |
| Baseline và success metric đã đo được chưa? | Yes | Baseline 3 ngày, Target nhận cảnh báo < 15 phút |
| Có data/input đủ dùng chưa? | Yes | Dùng Google Business Profile API hoặc cào dữ liệu công khai từ Google Maps/Social |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes | Vì có SM kiểm duyệt trước khi đăng phản hồi chính thức |
| Có người review/owner vận hành không? | Yes | SM của từng chi nhánh phụ trách duyệt và phản hồi |
| Có cách non-AI đơn giản hơn không? | No | Lọc từ khóa cứng (rule-based) không xử lý được ngôn ngữ tự nhiên nhiều ẩn ý của tiếng Việt |

Decision:
```text
Go.
```

Lý do:
- Vấn đề chất lượng dịch vụ ảnh hưởng trực tiếp đến sự sống còn và tốc độ nhân rộng của chuỗi bán lẻ.
- Workflow rõ ràng, rủi ro kiểm soát hoàn toàn được thông qua vai trò kiểm duyệt của SM (human boundary).

Pilot nhỏ nhất:
- Chạy thử nghiệm trên 1 chi nhánh mới mở có tỷ lệ review biến động cao nhất.
- Thu thập dữ liệu review của chi nhánh này trong 2 tuần qua, cho AI Agent chạy offline để phân loại sentiment và tạo draft phản hồi, đối chiếu thời gian và chất lượng với cách làm thủ công của SM.

Exit / rollback:
- Nếu AI Agent phân loại sai sentiment trên 30% tổng số review trong 2 tuần liên tiếp, hoặc liên tục soạn thảo phản hồi thiếu chuẩn mực, nhóm sẽ tạm dừng hệ thống cảnh báo tự động và quay về dùng công cụ giám sát bằng từ khóa (Rule-based) kết hợp SM kiểm tra định kỳ mỗi tối.
