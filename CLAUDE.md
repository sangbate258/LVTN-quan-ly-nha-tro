# Đề tài: Ứng dụng di động quản lý nhà trọ quy mô nhỏ (LVTN)

## Công nghệ đã chốt (không đổi, không thêm công nghệ khác khi chưa hỏi)
- Mobile: React Native, Expo, TypeScript
- Backend: Node.js, Express.js, TypeScript
- CSDL: MySQL, Prisma ORM 7

## Cấu trúc repo
- `backend/`: API Express + Prisma
- `mobile/`: ứng dụng Expo
- `docs/`: đặc tả. ĐỌC TRƯỚC KHI CODE.
  - `docs/schema.prisma`: thiết kế CSDL đã chốt (36 bảng). Dùng làm gốc cho `backend/prisma/schema.prisma`, không tự đổi tên bảng/cột.
  - `docs/00-HUONG-DAN-va-quy-uoc.md`: quy ước và các chi tiết nghiệp vụ đã thống nhất.
  - `docs/08*`, `docs/09*`, `docs/10*`, `docs/11*`, `docs/12*`: bảng dữ liệu, use case, sơ đồ tuần tự, hoạt động, kịch bản kiểm thử.

## Nguyên tắc làm việc
- Chọn giải pháp đơn giản nhất đáp ứng yêu cầu. Không thêm chức năng, thư viện hay công nghệ ngoài đặc tả. Muốn thêm thì hỏi trước.
- Làm từng module nhỏ, chạy được và kiểm tra được rồi mới sang module tiếp theo.
- Chỉ sửa trong phạm vi được yêu cầu. Thấy vấn đề khác thì báo lại, không tự sửa.
- Sau mỗi module, ghi ngắn vào `docs/NOTES.md`: đã làm gì, file nào, cách chạy thử.
- Không commit file `.env` hay bất kỳ khóa bí mật nào.
- Khi đặc tả mâu thuẫn hoặc thiếu, hỏi người dùng thay vì tự đoán.

## Quy tắc nghiệp vụ chính (chi tiết xem docs/)
- Hai vai trò: Chủ trọ và Khách thuê. Mỗi Chủ trọ quản lý một nhà trọ.
- Tiền lưu dạng số nguyên VND. Khóa chính là INT tự tăng.
- Phiếu báo phí chỉ có hai trạng thái: Nháp và Đã phát hành. Phiếu đã có thanh toán bị khóa; sai lệch ghi bằng bảng `invoice_adjustments`.
- Tiền cọc giữ chỗ cấn trừ một lần vào tiền thuê kỳ đầu; phần dư hoàn lại người đặt cọc.
- Tiền cọc thuê phòng tách riêng, không tính là doanh thu.
- Xác nhận chuyển khoản tự động chỉ khi khớp đủ khóa, tài khoản, mã tham chiếu, thời gian, số tiền, và mã giao dịch ngân hàng chưa dùng.

## Người dùng
Sinh viên làm luận văn, mới học lập trình. Giải thích ngắn gọn, rõ ràng, từng bước, và nói rõ cách chạy thử sau mỗi thay đổi.

## graphify

This project has a knowledge graph at graphify-out/ with god nodes, community structure, and cross-file relationships.

Rules:
- When graphify-out/graph.json exists, run `graphify query "<question>"` before your first grep, search or source-file read for a codebase question, and put this rule in every subagent prompt that explores code. Read raw files only for lines the graph or an earlier read already located. Use `graphify path "<A>" "<B>"` for relationships and `graphify explain "<concept>"` for focused concepts. When the answer is under a Markdown heading, `graphify section "<heading>"` prints that section's text, so the .md need not be opened. These return a scoped subgraph, usually much smaller than GRAPH_REPORT.md or raw grep output.
- If graphify-out/wiki/index.md exists, use it for broad navigation instead of raw source browsing.
- Read graphify-out/GRAPH_REPORT.md only for broad architecture review or when query/path/explain do not surface enough context.
- After modifying code, run `graphify update .` to keep the graph current (AST-only, no API cost).
- A committed graphify-out/graph.json is rewritten whole on every build, so a large diff to it in a pull request is expected. Do not flag it as churn or suggest skipping the graph rebuild or its hooks.
