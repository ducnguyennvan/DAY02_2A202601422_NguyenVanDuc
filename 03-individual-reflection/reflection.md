# 03 — Individual Reflection

## Đóng góp của Nguyễn Văn Đức trong nhóm

| Hoạt động | Nguyễn Văn Đức đã làm gì? | Kết quả |
|---|---|---|
| Scan cá nhân | Đưa ra 10 problems xoay quanh pain point vận hành chuỗi cửa hàng bán lẻ đa chi nhánh | Nhóm có nhiều candidate về vận hành doanh nghiệp, tồn kho, báo cáo và giám sát chất lượng |
| Gom trùng / cluster | Gom 15 candidates của 5 thành viên vào 4 cluster chính | Nhóm thấy rõ pattern chung, dễ so sánh và shortlist |
| Chọn candidate problem | Lập luận chọn bài Feedback & Giám sát vì cần NLP/LLM xử lý ngôn ngữ tự nhiên tiếng Việt | Nhóm đồng thuận chọn đề tài Agent thay vì Workflow |
| Validation / research | Tìm Google Business Profile API, Brand24, Zendesk CRM để đối chiếu giải pháp hiện có | Nhóm thấy cần tự xây module NLP tiếng Việt, không dùng nguyên tool ngoại |
| Problem Statement | Đóng góp viết field Actor, Bottleneck, Boundary trong PS v0 và v1 | PS v1 có boundary rõ: AI không tự đăng phản hồi, SM phải duyệt |
| Decision | Đề xuất pilot nhỏ nhất: chạy thử 1 chi nhánh trong 2 tuần, đối chiếu với cách làm thủ công | Nhóm chốt Go với exit criteria rõ ràng |

## Bảng dùng AI trong reflection

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Gợi ý thêm problems theo góc nhìn chủ chuỗi bán lẻ đa chi nhánh | Giúp nhớ thêm các pain point như kiểm kê lệch số liệu, duyệt chi tiêu lẻ tẻ qua Zalo | Gợi ý vài ý quá chung chung kiểu "quản lý nhân sự toàn diện" | Bỏ các ý không có dấu hiệu thật từ trải nghiệm quan sát được |
| Problem Card | Nhờ AI phản biện 3 Problem Cards của tôi | Chỉ ra metric của Card #1 (tồn kho) quá phụ thuộc vào dữ liệu POS real-time | AI đề xuất xây dashboard phức tạp ngay từ đầu | Giữ scope nhỏ, tập trung vào cảnh báo và lệnh điều chuyển đơn giản |
| Workflow | Nhờ AI chuyển mô tả current/future state thành dạng flow text có thời gian | Nhanh hơn khi format các bước và gắn thời gian vào từng bước | AI gộp bước "SM xác minh" và "SM duyệt phản hồi" thành một bước | Tách lại vì đây là 2 hành động khác nhau: xác minh nội bộ vs phản hồi khách hàng |
| Research | Tìm tool giám sát review và sentiment analysis cho tiếng Việt | Gợi ý Brand24, Zendesk, Google Business Profile API | Claim Brand24 hỗ trợ tốt tiếng Việt nhưng thực tế phân tích sentiment tiếng Việt còn yếu | Chỉ giữ link chính thức, ghi rõ khoảng trống "tiếng Việt chưa tốt" |
| Problem Statement | Nhờ AI phản biện field Boundary và Success Metric | Chỉ ra boundary ban đầu chưa nói rõ "AI không được tự post phản hồi" | AI đề xuất thêm quá nhiều metric phụ không cần thiết | Chỉ giữ 2 metric chính: thời gian phát hiện < 15 phút và rating >= 4.5/5 sao |
| Rule / Workflow / Agent | Nhờ AI so sánh 3 mức giải pháp cho bài toán sentiment tiếng Việt | Giải thích rõ vì sao keyword filter bỏ sót câu mỉa mai, ẩn ý | AI mặc định Agent là tốt nhất mà không phân tích rủi ro đủ sâu | Tự bổ sung rủi ro: AI phân loại sai sentiment, draft phản hồi thiếu chuẩn mực → cần SM duyệt |
| Decision | Nhờ AI gợi ý pilot plan và exit criteria | Gợi ý chạy thử trên 1 chi nhánh trước, đo tỷ lệ phân loại đúng | AI đề xuất triển khai toàn bộ chuỗi ngay | Thu hẹp về pilot 1 chi nhánh, 2 tuần, có exit criteria nếu sai > 30% |

## Bài học của Nguyễn Văn Đức

- Problem tốt nhất cho AI không phải problem có nhiều dữ liệu nhất, mà là problem mà dữ liệu đầu vào mang tính phi cấu trúc (ngôn ngữ tự nhiên, cảm xúc, ẩn ý) — nơi Rule và Workflow thông thường không đủ.
- Vẽ workflow trước giúp thấy rõ: bước nào Rule đủ (quét API lấy review), bước nào cần AI (phân tích sentiment tiếng Việt), và bước nào bắt buộc phải có con người (SM duyệt phản hồi).
- Agent không phải lúc nào cũng là "overkill". Trong bài toán này, Agent là mức cần thiết vì feedback tiếng Việt chứa nhiều sắc thái cảm xúc, châm biếm và từ ngữ địa phương mà Workflow keyword-filter không bắt được.
- Research giúp nhóm tránh "xây lại bánh xe": đã có API lấy review, đã có CRM gán ticket — nhóm chỉ cần xây phần AI phân tích sentiment và cảnh báo.

Nếu làm lại:

```text
Tôi sẽ phỏng vấn thêm nhiều chủ chuỗi và SM hơn trước khi chốt metric "3 ngày → 15 phút", vì baseline hiện tại chủ yếu dựa trên quan sát cá nhân và một vài cuộc phỏng vấn nhanh. Ngoài ra, tôi sẽ thử chạy một bài test sentiment analysis tiếng Việt thực tế ngay trong buổi lab để kiểm chứng xem LLM có thực sự hiểu được các câu mỉa mai kiểu "phục vụ nhanh như rùa" hay không.
```
