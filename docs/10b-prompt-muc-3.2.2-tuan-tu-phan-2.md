PROMPT 10b – MỤC 3.2.2 SƠ ĐỒ TUẦN TỰ (dán toàn bộ nội dung dưới đây cho AI Word; chỉ dùng sau khi đã chạy xong Prompt 10a)

VAI TRÒ: Bạn là người triển khai nội dung vào tài liệu LVTN.docx. Toàn bộ nội dung dưới đây đã được phân tích và chốt. Bạn chèn đúng nguyên văn từng chữ. Không tự viết thêm, không diễn đạt lại, không rút gọn, không suy luận, không sửa phần khác của tài liệu.

PHẠM VI: Chỉ làm việc trong mục "3.2.2 Sơ đồ tuần tự" (từ tiêu đề 3.2.2 đến trước tiêu đề "3.2.3 Sơ đồ hoạt động").

VIỆC 1 – Không xóa gì.

VIỆC 2 – CHÈN nối tiếp ngay sau mục 3.2.2.8 (trước tiêu đề "3.2.3 Sơ đồ hoạt động") các mục con 3.2.2.9 đến 3.2.2.17 theo đúng thứ tự dưới đây.

ĐỊNH DẠNG:
- Tiêu đề mục con: dùng đúng kiểu và cách đánh số tự động của tiêu đề cấp 4 (như "2.3.1.5 Quy trình đổi mật khẩu"); số mục sẽ là 3.2.2.1 đến 3.2.2.17.
- Dòng bắt đầu bằng "GẠCH ĐẦU DÒNG:" là một gạch đầu dòng, dùng đúng kiểu gạch đầu dòng đang có ở mục 3.2.2 (dòng "Cập nhật thông tin tài khoản" sắp bị xóa); chỉ ghi phần chữ sau dấu hai chấm.
- Khối mô tả sơ đồ: chèn nguyên văn từ dòng "[[MÔ TẢ SƠ ĐỒ: ...]]" đến dòng "[[HẾT MÔ TẢ]]", mỗi dòng là một đoạn riêng, phông Consolas cỡ 10, căn trái, giữ nguyên khoảng trắng đầu dòng. Đây là chỗ giữ chỗ cho hình.
- Chú thích hình: đặt ngay dưới khối mô tả sơ đồ, tạo bằng cơ chế chú thích có trường đánh số tự động, đúng kiểu chú thích hình đang có. Không gõ tay số hình.
- Thứ tự: Tiêu đề mục con → (Gạch đầu dòng → Khối mô tả → Chú thích) lặp lại cho từng chức năng.


===== MỤC 3.2.2.9 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case tra cứu thông tin thuê
GẠCH ĐẦU DÒNG: Tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Khách thuê → Ứng dụng di động: Mở giao diện Khách thuê
2. Ứng dụng di động → Máy chủ API: GET /api/tenant/contracts
3. Máy chủ API → Cơ sở dữ liệu: Lấy contracts mà users là thành viên (contract_members.user_id)
[Khung alt – điều kiện: Chưa có hợp đồng]
  4. Máy chủ API ⇢ Ứng dụng di động: Danh sách rỗng
  5. Ứng dụng di động ⇢ Khách thuê: Thông báo chưa có dữ liệu thuê
[Nhánh khác – điều kiện: Có hợp đồng]
  6. Máy chủ API ⇢ Ứng dụng di động: Danh sách hợp đồng
  7. Khách thuê → Ứng dụng di động: Chọn hợp đồng, phiếu báo phí, chỉ số hoặc lịch sử thanh toán
  8. Ứng dụng di động → Máy chủ API: GET /api/tenant/invoices/:id (hoặc /contracts/:id, /meter-readings, /payments)
  9. Máy chủ API → Máy chủ API: Kiểm tra tài khoản là thành viên của hợp đồng sở hữu dữ liệu
  [Khung alt – điều kiện: Ngoài phạm vi quyền]
    10. Máy chủ API ⇢ Ứng dụng di động: 403
    11. Ứng dụng di động ⇢ Khách thuê: Thông báo không có quyền truy cập
  [Nhánh khác – điều kiện: Trong phạm vi]
    12. Máy chủ API → Cơ sở dữ liệu: Lấy dữ liệu, nghĩa vụ theo chế độ thanh toán, lịch sử chỉnh sửa (audit_logs) và invoice_adjustments của phiếu
    13. Máy chủ API ⇢ Ứng dụng di động: 200 Dữ liệu
    14. Ứng dụng di động ⇢ Khách thuê: Hiển thị thông tin, dấu “Đã điều chỉnh” và khoản điều chỉnh riêng nếu có
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê

===== MỤC 3.2.2.10 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case thanh toán VietQR và báo chuyển khoản
GẠCH ĐẦU DÒNG: Tạo yêu cầu thanh toán VietQR
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự tạo yêu cầu thanh toán VietQR]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Khách thuê → Ứng dụng di động: Mở phiếu, chọn “Thanh toán”, chọn nghĩa vụ và số tiền
2. Ứng dụng di động → Máy chủ API: POST /api/payment-requests {invoiceId, obligationId hoặc mã tổng, amount}
3. Máy chủ API → Cơ sở dữ liệu: Lấy invoice_obligations (số dư) và boarding_houses (tài khoản nhận)
4. Máy chủ API → Máy chủ API: Kiểm tra quyền, 0 < số tiền ≤ số dư còn phải trả
[Khung alt – điều kiện: Không hợp lệ hoặc chưa có tài khoản nhận tiền]
  5. Máy chủ API ⇢ Ứng dụng di động: 400/409
  6. Ứng dụng di động ⇢ Khách thuê: Hiển thị lỗi hoặc thông báo chưa thể tạo mã
[Nhánh khác – điều kiện: Hợp lệ]
  7. Máy chủ API → Máy chủ API: Sinh reference_code riêng, expires_at = thời điểm tạo + 15 phút
  8. Máy chủ API → Cơ sở dữ liệu: Lưu payment_requests (PENDING)
  9. Máy chủ API ⇢ Ứng dụng di động: 201 Dữ liệu VietQR (tài khoản, số tiền, nội dung = reference_code)
  10. Ứng dụng di động ⇢ Khách thuê: Hiển thị mã VietQR và thời gian còn lại
[Hết khung]
[Khung opt – điều kiện: Hết 15 phút chưa có giao dịch xác nhận]
  11. Máy chủ API → Cơ sở dữ liệu: Cập nhật payment_requests.status = EXPIRED
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự tạo yêu cầu thanh toán VietQR
GẠCH ĐẦU DÒNG: Báo chuyển khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự báo chuyển khoản]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Khách thuê → Ứng dụng di động: Chọn “Tôi đã chuyển”, đính kèm ảnh chứng từ
2. Ứng dụng di động → Máy chủ API: POST /api/payment-requests/:id/report {image}
3. Máy chủ API → Cơ sở dữ liệu: Lấy payment_requests
[Khung alt – điều kiện: Yêu cầu đã được xác nhận tự động]
  4. Máy chủ API ⇢ Ứng dụng di động: 409 Đã thanh toán
  5. Ứng dụng di động ⇢ Khách thuê: Hiển thị trạng thái đã thanh toán
[Nhánh khác – điều kiện: Chưa xác nhận]
  6. Máy chủ API → Cơ sở dữ liệu: Cập nhật report_status = REPORTED, reported_at; lưu attachments
  7. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Chủ trọ
  8. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Chủ trọ
  9. Máy chủ API ⇢ Ứng dụng di động: 200
  10. Ứng dụng di động ⇢ Khách thuê: Hiển thị trạng thái chờ xác nhận
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự báo chuyển khoản

===== MỤC 3.2.2.11 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case xác nhận thanh toán và đối chiếu giao dịch
GẠCH ĐẦU DÒNG: Xác nhận báo chuyển khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự xác nhận báo chuyển khoản]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở báo chuyển khoản
2. Chủ trọ → Chủ trọ: Kiểm tra số tiền thực nhận trong tài khoản ngân hàng
[Khung alt – điều kiện: Đã nhận đúng khoản tiền]
  3. Chủ trọ → Ứng dụng di động: Chọn “Xác nhận”
  4. Ứng dụng di động → Máy chủ API: POST /api/payment-requests/:id/confirm
  5. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  6. Máy chủ API → Cơ sở dữ liệu: Kiểm tra payments chưa có payment_request_id này
  [Khung alt – điều kiện: Đã ghi nhận trước đó]
    7. Máy chủ API → Cơ sở dữ liệu: Hủy giao dịch dữ liệu
    8. Máy chủ API ⇢ Ứng dụng di động: 409 Đã ghi nhận
  [Nhánh khác – điều kiện: Chưa ghi nhận]
    9. Máy chủ API → Cơ sở dữ liệu: Tạo payments, payment_allocations; cập nhật invoice_obligations.amount_paid, status
    10. Máy chủ API → Cơ sở dữ liệu: Cập nhật payment_requests (PAID, report_status = CONFIRMED)
    11. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
    12. Máy chủ API ⇢ Ứng dụng di động: 200
  [Hết khung]
[Nhánh khác – điều kiện: Chưa nhận hoặc không khớp]
  13. Chủ trọ → Ứng dụng di động: Chọn “Từ chối”, nhập lý do
  14. Ứng dụng di động → Máy chủ API: POST /api/payment-requests/:id/reject {reason}
  15. Máy chủ API → Cơ sở dữ liệu: Cập nhật report_status = REJECTED, reject_reason
  16. Máy chủ API ⇢ Ứng dụng di động: 200
[Hết khung]
17. Máy chủ API → Cơ sở dữ liệu: Tạo notifications kết quả cho Khách thuê
18. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự xác nhận báo chuyển khoản
GẠCH ĐẦU DÒNG: Tự động xác nhận giao dịch ngân hàng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự tự động xác nhận giao dịch ngân hàng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Dịch vụ thông báo biến động số dư | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Dịch vụ thông báo biến động số dư → Máy chủ API: POST /api/webhooks/bank/:token (header Authorization: Apikey ...; dữ liệu giao dịch)
2. Máy chủ API → Cơ sở dữ liệu: Tìm boarding_houses theo webhook_token
3. Máy chủ API → Máy chủ API: So khớp khóa xác thực với webhook_key_hash
[Khung alt – điều kiện: Khóa không hợp lệ]
  4. Máy chủ API ⇢ Dịch vụ thông báo biến động số dư: 401
[Nhánh khác – điều kiện: Khóa hợp lệ]
  5. Máy chủ API → Cơ sở dữ liệu: Tìm bank_transactions theo (house_id, provider_txn_id)
  [Khung alt – điều kiện: Đã ghi nhận]
    6. Máy chủ API ⇢ Dịch vụ thông báo biến động số dư: 200 Bỏ qua
  [Nhánh khác – điều kiện: Giao dịch mới]
    7. Máy chủ API → Cơ sở dữ liệu: Lưu bank_transactions
    8. Máy chủ API → Cơ sở dữ liệu: Tìm payments TRANSFER_REPORT đã xác nhận thủ công khớp tài khoản nhận, số tiền, thời điểm, mã tham chiếu
    9. Máy chủ API → Cơ sở dữ liệu: Tìm payment_requests theo reference_code trong nội dung
    [Khung alt – điều kiện: Nghi trùng khoản đã xác nhận thủ công]
      10. Máy chủ API → Cơ sở dữ liệu: Cập nhật bank_transactions (NEED_RECONCILE, reason)
    [Nhánh khác – điều kiện: Đủ điều kiện (tài khoản nhận, mã tham chiếu, thời điểm trong [tạo, hết hạn], số tiền khớp, nghĩa vụ còn đủ số dư)]
      11. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
      12. Máy chủ API → Cơ sở dữ liệu: Tạo payments (AUTO_BANK, bank_transaction_id), payment_allocations theo thứ tự danh sách; cập nhật invoice_obligations, payment_requests = PAID, bank_transactions.result = AUTO_CONFIRMED
      13. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
      14. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Khách thuê và Chủ trọ
      15. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
    [Nhánh khác – điều kiện: Không đủ điều kiện]
      16. Máy chủ API → Cơ sở dữ liệu: Cập nhật bank_transactions (NEED_RECONCILE, reason)
      17. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Chủ trọ
      18. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Chủ trọ
    [Hết khung]
    19. Máy chủ API ⇢ Dịch vụ thông báo biến động số dư: 200
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự tự động xác nhận giao dịch ngân hàng
GẠCH ĐẦU DÒNG: Đối chiếu thủ công giao dịch không khớp
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự đối chiếu thủ công giao dịch không khớp]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở “Giao dịch cần đối chiếu”
2. Ứng dụng di động → Máy chủ API: GET /api/bank-transactions?result=NEED_RECONCILE
3. Máy chủ API → Cơ sở dữ liệu: Lấy bank_transactions theo house_id
4. Máy chủ API ⇢ Ứng dụng di động: Danh sách kèm nguyên nhân
5. Chủ trọ → Ứng dụng di động: Chọn một giao dịch
[Khung alt – điều kiện: Không liên quan hoặc đã được ghi nhận trước đó]
  6. Chủ trọ → Ứng dụng di động: Chọn “Không liên quan”, nhập lý do
  7. Ứng dụng di động → Máy chủ API: POST /api/bank-transactions/:id/unrelated {reason}
  8. Máy chủ API → Cơ sở dữ liệu: Cập nhật bank_transactions (UNRELATED, reason, handled_by, handled_at)
  9. Máy chủ API ⇢ Ứng dụng di động: 200
[Nhánh khác – điều kiện: Là khoản thanh toán tiền thuê]
  10. Chủ trọ → Ứng dụng di động: Chọn phòng, nghĩa vụ, chọn “Xác nhận”
  11. Ứng dụng di động → Máy chủ API: POST /api/bank-transactions/:id/reconcile {obligationIds}
  12. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  13. Máy chủ API → Cơ sở dữ liệu: Kiểm tra payments chưa có bank_transaction_id này
  14. Máy chủ API → Cơ sở dữ liệu: Tạo payments (RECONCILE), payment_allocations; cập nhật invoice_obligations
  15. Máy chủ API → Máy chủ API: Phần lớn hơn số còn thiếu cộng vào credit_balance của người trả
  16. Máy chủ API → Cơ sở dữ liệu: Cập nhật bank_transactions (RECONCILED, handled_by, handled_at)
  17. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
  18. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Khách thuê
  19. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
  20. Máy chủ API ⇢ Ứng dụng di động: 200
[Hết khung]
21. Ứng dụng di động ⇢ Chủ trọ: Giao dịch rời danh sách chờ, vẫn tra cứu được trong lịch sử
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự đối chiếu thủ công giao dịch không khớp
GẠCH ĐẦU DÒNG: Ghi nhận thanh toán tiền mặt
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự ghi nhận thanh toán tiền mặt]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Chủ trọ: Nhận và kiểm đếm tiền mặt
2. Chủ trọ → Ứng dụng di động: Mở phiếu, chọn “Thu tiền mặt”, nhập số tiền, chọn người trả, nghĩa vụ
3. Ứng dụng di động → Máy chủ API: POST /api/invoices/:id/cash-payments {amount, payerMemberId, obligationIds}
4. Máy chủ API → Máy chủ API: Kiểm tra số tiền lớn hơn 0, nghĩa vụ thuộc phiếu
[Khung alt – điều kiện: Không hợp lệ]
  5. Máy chủ API ⇢ Ứng dụng di động: 400
  6. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  7. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  8. Máy chủ API → Cơ sở dữ liệu: Tạo payments (CASH), payment_allocations; cập nhật invoice_obligations
  9. Máy chủ API → Máy chủ API: Phần lớn hơn số còn thiếu cộng vào credit_balance của người trả
  10. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
  11. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Khách thuê liên quan
  12. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
  13. Máy chủ API ⇢ Ứng dụng di động: 201
  14. Ứng dụng di động ⇢ Chủ trọ: Hiển thị số đã trả, số còn thiếu
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự ghi nhận thanh toán tiền mặt

===== MỤC 3.2.2.12 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case theo dõi công nợ và nhắc thanh toán
GẠCH ĐẦU DÒNG: Theo dõi công nợ và nhắc thanh toán
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự theo dõi công nợ và nhắc thanh toán]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Vào mục “Công nợ”
2. Ứng dụng di động → Máy chủ API: GET /api/debts
3. Máy chủ API → Cơ sở dữ liệu: Tổng hợp invoices ISSUED và invoice_obligations chưa trả đủ theo phòng
4. Máy chủ API → Máy chủ API: Đánh dấu quá hạn khi ngày hiện tại sau due_date
5. Máy chủ API ⇢ Ứng dụng di động: Danh sách công nợ
6. Ứng dụng di động ⇢ Chủ trọ: Hiển thị số phải trả, đã trả, còn thiếu, hạn, trạng thái
[Khung opt – điều kiện: Nhắc thanh toán]
  7. Chủ trọ → Ứng dụng di động: Chọn “Nhắc thanh toán”
  8. Ứng dụng di động → Máy chủ API: POST /api/invoices/:id/remind
  9. Máy chủ API → Cơ sở dữ liệu: Lấy thành viên của các phần còn thiếu
  10. Máy chủ API → Cơ sở dữ liệu: Tạo notifications (PAYMENT_REMINDER) cho từng người
  11. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
  12. Máy chủ API ⇢ Ứng dụng di động: 200
[Hết khung]
[Khung opt – điều kiện: Xử lý khoản trả dư]
  13. Chủ trọ → Ứng dụng di động: Chọn bù trừ kỳ sau hoặc ghi nhận hoàn tiền
  14. Ứng dụng di động → Máy chủ API: POST /api/members/:id/credit {action}
  15. Máy chủ API → Cơ sở dữ liệu: Cập nhật contract_members.credit_balance; ghi audit_logs
  16. Máy chủ API ⇢ Ứng dụng di động: 200
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự theo dõi công nợ và nhắc thanh toán

===== MỤC 3.2.2.13 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý sự cố
GẠCH ĐẦU DÒNG: Gửi yêu cầu sự cố
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự gửi yêu cầu sự cố]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Chọn “Tạo yêu cầu”, nhập mô tả, mức độ, hình ảnh
2. Ứng dụng di động → Máy chủ API: POST /api/incidents {description, severity, roomId}
3. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu và quyền với phòng
[Khung alt – điều kiện: Không hợp lệ]
  4. Máy chủ API ⇢ Ứng dụng di động: 400
  5. Ứng dụng di động ⇢ Người dùng: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Cơ sở dữ liệu: Lưu incidents (NEW), incident_updates, attachments
  7. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Chủ trọ
  8. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Chủ trọ
  9. Máy chủ API ⇢ Ứng dụng di động: 201
  10. Ứng dụng di động ⇢ Người dùng: Hiển thị yêu cầu trong danh sách sự cố
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự gửi yêu cầu sự cố
GẠCH ĐẦU DÒNG: Xử lý sự cố và ghi nhận chi phí
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự xử lý sự cố và ghi nhận chi phí]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở yêu cầu Mới, chọn “Tiếp nhận”
2. Ứng dụng di động → Máy chủ API: POST /api/incidents/:id/accept
3. Máy chủ API → Cơ sở dữ liệu: Cập nhật incidents.status = IN_PROGRESS; thêm incident_updates
4. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Khách thuê
[Khung opt – điều kiện: Cập nhật tiến độ]
  5. Chủ trọ → Ứng dụng di động: Nhập nguyên nhân, tiến độ
  6. Ứng dụng di động → Máy chủ API: POST /api/incidents/:id/updates {content}
  7. Máy chủ API → Cơ sở dữ liệu: Thêm incident_updates
[Hết khung]
8. Chủ trọ → Ứng dụng di động: Nhập kết quả, chi phí, bên chịu chi phí
9. Ứng dụng di động → Máy chủ API: POST /api/incidents/:id/resolve {result, costAmount, costBearer}
10. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
[Khung opt – điều kiện: Có chi phí]
  [Khung alt – điều kiện: Chủ trọ chịu]
    11. Máy chủ API → Cơ sở dữ liệu: Tạo finance_entries (EXPENSE, INCIDENT)
  [Nhánh khác – điều kiện: Khách thuê chịu]
    12. Máy chủ API → Cơ sở dữ liệu: Tạo extra_charges cho hợp đồng
  [Hết khung]
[Hết khung]
[Khung alt – điều kiện: Yêu cầu do Khách thuê tạo]
  13. Máy chủ API → Cơ sở dữ liệu: Cập nhật incidents (AWAITING_CONFIRM, result, cost); thêm incident_updates
  14. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo kết quả đến thiết bị Khách thuê
[Nhánh khác – điều kiện: Yêu cầu do Chủ trọ tự tạo]
  15. Máy chủ API → Cơ sở dữ liệu: Cập nhật incidents (DONE, closed_at); thêm incident_updates
[Hết khung]
16. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
17. Máy chủ API ⇢ Ứng dụng di động: 200
18. Ứng dụng di động ⇢ Chủ trọ: Hiển thị trạng thái mới
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự xử lý sự cố và ghi nhận chi phí
GẠCH ĐẦU DÒNG: Xác nhận kết quả xử lý sự cố
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự xác nhận kết quả xử lý sự cố]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Khách thuê → Ứng dụng di động: Mở yêu cầu Chờ khách xác nhận
2. Ứng dụng di động → Máy chủ API: GET /api/incidents/:id
3. Máy chủ API → Cơ sở dữ liệu: Lấy incidents và incident_updates
4. Máy chủ API ⇢ Ứng dụng di động: Kết quả, chi phí, bên chịu
[Khung alt – điều kiện: Đã khắc phục]
  5. Khách thuê → Ứng dụng di động: Chọn “Xác nhận”
  6. Ứng dụng di động → Máy chủ API: POST /api/incidents/:id/confirm
  7. Máy chủ API → Cơ sở dữ liệu: Cập nhật incidents (DONE, closed_at); thêm incident_updates
[Nhánh khác – điều kiện: Chưa khắc phục]
  8. Khách thuê → Ứng dụng di động: Chọn “Phản hồi”, nhập nội dung
  9. Ứng dụng di động → Máy chủ API: POST /api/incidents/:id/feedback {content}
  10. Máy chủ API → Cơ sở dữ liệu: Cập nhật incidents.status = IN_PROGRESS; thêm incident_updates
[Hết khung]
11. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Chủ trọ
12. Máy chủ API ⇢ Ứng dụng di động: 200
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự xác nhận kết quả xử lý sự cố

===== MỤC 3.2.2.14 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case gia hạn và điều chỉnh hợp đồng
GẠCH ĐẦU DÒNG: Gia hạn hợp đồng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự gia hạn hợp đồng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Đề nghị gia hạn”, nhập ngày kết thúc mong muốn (Khách thuê gửi đề nghị theo cách tương tự)
2. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/changes {kind: EXTEND, content}
3. Máy chủ API → Cơ sở dữ liệu: Lưu contract_changes (PROPOSED); tạo notifications cho bên còn lại
4. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
[Khung alt – điều kiện: Không thống nhất]
  5. Chủ trọ → Ứng dụng di động: Chọn “Đóng đề nghị”
  6. Ứng dụng di động → Máy chủ API: PUT /api/contract-changes/:id {status: CLOSED}
  7. Máy chủ API → Cơ sở dữ liệu: Cập nhật contract_changes
[Nhánh khác – điều kiện: Thống nhất]
  8. Chủ trọ → Ứng dụng di động: Nhập ngày kết thúc mới, ngày hiệu lực, chứng từ
  9. Ứng dụng di động → Máy chủ API: PUT /api/contract-changes/:id {changes, effectiveDate}
  10. Máy chủ API → Máy chủ API: Kiểm tra ngày mới muộn hơn hiện tại, không xung đột reservations
  [Khung alt – điều kiện: Không hợp lệ]
    11. Máy chủ API ⇢ Ứng dụng di động: 400
  [Nhánh khác – điều kiện: Hợp lệ]
    12. Máy chủ API → Cơ sở dữ liệu: Cập nhật contract_changes = AWAITING_CONFIRM
    13. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến người đứng tên
    14. Khách thuê → Ứng dụng di động: Người đứng tên chọn “Xác nhận” hoặc “Từ chối”
    15. Ứng dụng di động → Máy chủ API: POST /api/contract-changes/:id/confirm hoặc /reject
    [Khung alt – điều kiện: Xác nhận]
      16. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
      17. Máy chủ API → Cơ sở dữ liệu: Cập nhật contract_changes (CONFIRMED), contracts.end_date; ghi audit_logs
      18. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
      19. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến các thành viên
    [Nhánh khác – điều kiện: Từ chối]
      20. Máy chủ API → Cơ sở dữ liệu: Cập nhật contract_changes = REJECTED
    [Hết khung]
    21. Máy chủ API ⇢ Ứng dụng di động: 200
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự gia hạn hợp đồng
GẠCH ĐẦU DÒNG: Điều chỉnh hợp đồng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự điều chỉnh hợp đồng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Điều chỉnh hợp đồng”, nhập nội dung, ngày hiệu lực, chứng từ
2. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/changes {kind: ADJUST, content, changes, effectiveDate}
3. Máy chủ API → Máy chủ API: Kiểm tra đúng một người đứng tên, người đại diện hoặc người chịu trách nhiệm thanh toán theo chế độ
[Khung alt – điều kiện: Không hợp lệ]
  4. Máy chủ API ⇢ Ứng dụng di động: 400
  5. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Cơ sở dữ liệu: Lưu contract_changes (AWAITING_CONFIRM)
  7. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến người đứng tên
  8. Khách thuê → Ứng dụng di động: Người đứng tên chọn “Xác nhận” hoặc “Từ chối”
  9. Ứng dụng di động → Máy chủ API: POST /api/contract-changes/:id/confirm hoặc /reject
  [Khung alt – điều kiện: Xác nhận]
    10. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
    11. Máy chủ API → Cơ sở dữ liệu: Cập nhật contracts, contract_members (thêm thành viên, left_at), contract_changes (CONFIRMED); ghi audit_logs
    12. Máy chủ API → Máy chủ API: Tạo hoặc liên kết tài khoản cho thành viên mới
    13. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
    14. Máy chủ API → Máy chủ API: Phiếu đã phát hành giữ nguyên các phần phải trả
  [Nhánh khác – điều kiện: Từ chối]
    15. Máy chủ API → Cơ sở dữ liệu: Cập nhật contract_changes = REJECTED
  [Hết khung]
  16. Máy chủ API ⇢ Ứng dụng di động: 200
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự điều chỉnh hợp đồng

===== MỤC 3.2.2.15 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case trả phòng, thanh lý và quyết toán
GẠCH ĐẦU DÒNG: Yêu cầu trả phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự yêu cầu trả phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Khách thuê | Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Khách thuê → Ứng dụng di động: Chọn “Yêu cầu trả phòng”, nhập ngày dự kiến và lý do
2. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/move-out-request {moveOutDate, reason}
3. Máy chủ API → Máy chủ API: Kiểm tra ngày dự kiến không sớm hơn ngày gửi
[Khung alt – điều kiện: Không hợp lệ]
  4. Máy chủ API ⇢ Ứng dụng di động: 400
  5. Ứng dụng di động ⇢ Khách thuê: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Cơ sở dữ liệu: Cập nhật contracts.move_out_date; tạo notifications cho Chủ trọ
  7. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Chủ trọ
  8. Máy chủ API ⇢ Ứng dụng di động: 200
  9. Chủ trọ → Ứng dụng di động: Nhập ngày chấm dứt được chấp thuận
  10. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/termination {terminationDate}
  11. Máy chủ API → Cơ sở dữ liệu: Cập nhật contracts (termination_date, status = PENDING_LIQUIDATION)
  12. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến các thành viên
  13. Máy chủ API ⇢ Ứng dụng di động: 200
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự yêu cầu trả phòng
GẠCH ĐẦU DÒNG: Thanh lý hợp đồng và quyết toán tiền cọc
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự thanh lý hợp đồng và quyết toán tiền cọc]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Lập quyết toán”
2. Ứng dụng di động → Máy chủ API: GET /api/contracts/:id/settlement-preview
3. Máy chủ API → Cơ sở dữ liệu: Kiểm tra handovers MOVE_OUT ở trạng thái CONFIRMED hoặc COMPLETED_UNCONFIRMED và chỉ số cuối kỳ đã chốt
[Khung alt – điều kiện: Biên bản trả phòng chưa hoàn tất]
  4. Máy chủ API ⇢ Ứng dụng di động: 409
  5. Ứng dụng di động ⇢ Chủ trọ: Yêu cầu hoàn tất biên bản trả phòng
[Nhánh khác – điều kiện: Đã hoàn tất]
  6. Máy chủ API → Cơ sở dữ liệu: Lấy invoices, invoice_obligations còn thiếu, invoice_adjustments (SETTLEMENT), credit_balance, contracts.deposit_held
  7. Máy chủ API ⇢ Ứng dụng di động: Số liệu tổng hợp (kèm cảnh báo nếu biên bản Khách chưa xác nhận)
  8. Chủ trọ → Ứng dụng di động: Nhập tiền thuê đến ngày chấm dứt, phần hoàn, khoản khấu trừ kèm lý do, đánh dấu khoản có bản chất doanh thu
  9. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/settlement {items}
  10. Máy chủ API → Máy chủ API: Kiểm tra mỗi khoản khấu trừ có lý do; tính result_amount = cọc + khoản được hoàn − công nợ − khấu trừ − khoản phải thu khác
  [Khung alt – điều kiện: Thiếu lý do]
    11. Máy chủ API ⇢ Ứng dụng di động: 400
  [Nhánh khác – điều kiện: Hợp lệ]
    12. Máy chủ API → Cơ sở dữ liệu: Lưu settlements (SENT), settlement_items
    13. Máy chủ API → Dịch vụ thông báo đẩy: Gửi bảng quyết toán đến thiết bị Khách thuê
    14. Máy chủ API ⇢ Ứng dụng di động: 201
    15. Chủ trọ → Chủ trọ: Hai bên trao đổi, thống nhất ngoài ứng dụng
    [Khung alt – điều kiện: Chưa thống nhất]
      16. Chủ trọ → Ứng dụng di động: Điều chỉnh bảng quyết toán
      17. Ứng dụng di động → Máy chủ API: PUT /api/settlements/:id {items}
    [Nhánh khác – điều kiện: Đã thống nhất]
      18. Chủ trọ → Ứng dụng di động: Chọn “Hoàn tất quyết toán”
      19. Ứng dụng di động → Máy chủ API: POST /api/settlements/:id/complete
      20. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
      21. Máy chủ API → Cơ sở dữ liệu: Tạo payments (DEPOSIT_OFFSET, SETTLEMENT) cho phần cọc cấn trừ công nợ; cập nhật invoice_obligations; settlements.deposit_used_for_debt
      22. Máy chủ API → Cơ sở dữ liệu: Tạo finance_entries (INCOME, SETTLEMENT) chỉ cho khoản khấu trừ is_revenue; cập nhật invoice_adjustments = SETTLED
      23. Máy chủ API → Cơ sở dữ liệu: Cập nhật settlements (COMPLETED), contracts (LIQUIDATED, deposit_held = 0), rooms.status theo phiếu giữ phòng còn lại
      24. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
      25. Máy chủ API ⇢ Ứng dụng di động: 200
    [Hết khung]
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự thanh lý hợp đồng và quyết toán tiền cọc

===== MỤC 3.2.2.16 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý thu chi và thống kê
GẠCH ĐẦU DÒNG: Ghi nhận khoản thu chi khác
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự ghi nhận khoản thu chi khác]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Vào “Thu chi”, chọn “Thêm khoản”, nhập loại, nội dung, số tiền, ngày, chứng từ
2. Ứng dụng di động → Máy chủ API: POST /api/finance-entries {type, description, amount, occurredOn}
3. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu
[Khung alt – điều kiện: Không hợp lệ]
  4. Máy chủ API ⇢ Ứng dụng di động: 400
  5. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Cơ sở dữ liệu: Lưu finance_entries (MANUAL), attachments
  7. Máy chủ API ⇢ Ứng dụng di động: 201
  8. Ứng dụng di động ⇢ Chủ trọ: Cập nhật danh sách theo thời gian
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự ghi nhận khoản thu chi khác
GẠCH ĐẦU DÒNG: Xem thống kê
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự xem thống kê]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Vào mục “Thống kê”, chọn tháng hoặc khoảng thời gian
2. Ứng dụng di động → Máy chủ API: GET /api/statistics?from=&to=
3. Máy chủ API → Cơ sở dữ liệu: Tổng hợp payments, finance_entries, invoice_obligations, reservations, contracts, rooms theo house_id
4. Máy chủ API → Máy chủ API: Thực thu = payments trừ hình thức DEPOSIT_OFFSET; doanh thu không cộng tiền cọc đang giữ và khoản cấn trừ cọc; cọc giữ lại khi hủy phiếu và khoản khấu trừ có bản chất doanh thu tính là doanh thu
5. Máy chủ API → Máy chủ API: Tính khoản chi, chênh lệch, công nợ, tiền cọc đang giữ, số phòng theo trạng thái
6. Máy chủ API ⇢ Ứng dụng di động: 200 Các chỉ số (giá trị 0 nếu không có dữ liệu)
7. Ứng dụng di động ⇢ Chủ trọ: Hiển thị thống kê
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự xem thống kê

===== MỤC 3.2.2.17 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý thông báo
GẠCH ĐẦU DÒNG: Gửi thông báo chung
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự gửi thông báo chung]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Tạo thông báo”, nhập tiêu đề, nội dung, chọn đối tượng nhận
2. Ứng dụng di động → Máy chủ API: POST /api/announcements {title, content, target, roomIds}
3. Máy chủ API → Cơ sở dữ liệu: Xác định người nhận: thành viên có tài khoản của hợp đồng còn hiệu lực
[Khung alt – điều kiện: Thiếu dữ liệu hoặc không có người nhận]
  4. Máy chủ API ⇢ Ứng dụng di động: 400
  5. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Cơ sở dữ liệu: Lưu announcements và notifications cho từng người nhận (push_status = PENDING)
  7. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị của người nhận
  8. Máy chủ API → Cơ sở dữ liệu: Cập nhật push_status = SENT hoặc FAILED
  9. Máy chủ API ⇢ Ứng dụng di động: 201
  10. Ứng dụng di động ⇢ Chủ trọ: Thông báo gửi thành công
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự gửi thông báo chung
GẠCH ĐẦU DÒNG: Xem thông báo
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự xem thông báo]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Vào mục “Thông báo” hoặc chạm vào thông báo trên thiết bị
2. Ứng dụng di động → Máy chủ API: GET /api/notifications
3. Máy chủ API → Cơ sở dữ liệu: Lấy notifications theo user_id, mới nhất trước
4. Máy chủ API ⇢ Ứng dụng di động: Danh sách và dấu chưa đọc
5. Người dùng → Ứng dụng di động: Chọn một thông báo
6. Ứng dụng di động → Máy chủ API: PATCH /api/notifications/:id/read
7. Máy chủ API → Cơ sở dữ liệu: Cập nhật notifications.read_at
8. Máy chủ API ⇢ Ứng dụng di động: 200
[Khung opt – điều kiện: Thông báo gắn với đối tượng]
  9. Ứng dụng di động → Máy chủ API: GET tài nguyên theo ref_type, ref_id
  10. Máy chủ API → Máy chủ API: Kiểm tra quyền của tài khoản
  [Khung alt – điều kiện: Còn quyền]
    11. Máy chủ API ⇢ Ứng dụng di động: 200 Dữ liệu
    12. Ứng dụng di động ⇢ Người dùng: Chuyển đến màn hình tương ứng
  [Nhánh khác – điều kiện: Không còn quyền]
    13. Máy chủ API ⇢ Ứng dụng di động: 403
    14. Ứng dụng di động ⇢ Người dùng: Chỉ hiển thị nội dung thông báo
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự xem thông báo

KIỂM TRA SAU KHI LÀM (báo lại kết quả từng dòng):
1. Không còn nội dung "quản lý hồ sơ và điểm uy tín" trong mục 3.2.2.
2. Mục 3.2.2 có một đoạn văn và đúng 17 mục con 3.2.2.1 đến 3.2.2.17.
3. Tổng số khối mô tả sơ đồ và chú thích hình trong mục 3.2.2 đều là 51.
4. Sau khi cập nhật toàn bộ trường (Ctrl+A rồi F9), chú thích sơ đồ tuần tự đầu tiên là Hình 3-20 và cuối cùng là Hình 3-70. Cập nhật Mục lục và Mục lục các hình vẽ.
