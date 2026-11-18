PROMPT 08b – MỤC 3.1.3 MÔ HÌNH DỮ LIỆU MỨC VẬT LÝ (dán toàn bộ nội dung dưới đây cho AI Word; chỉ dùng sau khi đã chạy xong Prompt 08a)

VAI TRÒ: Bạn là người triển khai nội dung vào tài liệu LVTN.docx. Toàn bộ nội dung dưới đây đã được phân tích và chốt. Bạn chèn đúng nguyên văn từng chữ. Không tự viết thêm, không diễn đạt lại, không rút gọn, không suy luận, không sửa phần khác của tài liệu.

PHẠM VI: Chỉ làm việc trong mục "3.1 MÔ HÌNH DỮ LIỆU" (từ tiêu đề 3.1 đến trước tiêu đề "3.2 MÔ HÌNH XỬ LÝ"). Không sửa Chương 1, Chương 2 và từ mục 3.2 trở đi.

ĐỊNH DẠNG CHUNG:
- Đoạn văn và gạch đầu dòng: dùng đúng định dạng đoạn văn và gạch đầu dòng đang có trong mục 3.1.1 (dòng "Lược đồ cơ sở dữ liệu:" và gạch đầu dòng "Bảng users: ...").
- Khối mô tả sơ đồ: chèn nguyên văn từ dòng "[[MÔ TẢ SƠ ĐỒ: ...]]" đến dòng "[[HẾT MÔ TẢ]]", mỗi dòng là một đoạn riêng, phông Consolas cỡ 10, căn trái, không thụt đầu dòng. Đặt khối này ngay trên chú thích hình tương ứng; đây là chỗ giữ chỗ cho hình.
- Tiêu đề bảng vật lý: dùng đúng kiểu (style) của tiêu đề "Bảng users" đang có trong mục 3.1.3.
- Bảng vật lý: dùng đúng mẫu bảng "Bảng users" đang có (7 cột "Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải"; dòng đầu tiên gộp 7 ô, ghi "Mô tả: ..." với chữ "Mô tả" in đậm; dòng thứ hai là tiêu đề cột in đậm). Dấu "x" đặt giữa ô.
- Dòng "Ràng buộc bổ sung: ..." (nếu có) là một đoạn văn thường đặt ngay dưới bảng.

===== VIỆC 4: MỤC 3.1.3 MÔ HÌNH DỮ LIỆU MỨC VẬT LÝ =====
CHÈN ngay dưới tiêu đề "3.1.3 Mô hình dữ liệu mức vật lý" một đoạn văn, sau đó lần lượt 36 bảng theo đúng thứ tự dưới đây. Mỗi bảng gồm: tiêu đề "Bảng <tên>", bảng 7 cột, rồi dòng ràng buộc bổ sung nếu có. Mỗi dòng dữ liệu dưới đây gồm 7 ô ngăn cách bằng dấu "|".
ĐOẠN VĂN:
Mô hình dữ liệu mức vật lý mô tả chi tiết các bảng được cài đặt trên MySQL thông qua Prisma ORM. Trong các bảng dưới đây, cột K đánh dấu khóa chính, U đánh dấu giá trị duy nhất, M đánh dấu thuộc tính bắt buộc và F đánh dấu khóa ngoại. Kiểu ENUM liệt kê các giá trị hợp lệ của thuộc tính trạng thái hoặc phân loại; kiểu JSON lưu dữ liệu có cấu trúc không cần truy vấn riêng.
--- Bảng users ---
TIÊU ĐỀ: Bảng users
Mô tả: Bảng users lưu tài khoản đăng nhập của Chủ trọ và Khách thuê. Một tài khoản có thể có một hoặc cả hai vai trò.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
phone | VARCHAR(15) |  | x | x |  | Số điện thoại chính, dùng để đăng nhập
password_hash | VARCHAR(255) |  |  | x |  | Mật khẩu đã được băm một chiều
full_name | VARCHAR(100) |  |  |  |  | Họ tên người dùng
is_landlord | BOOLEAN |  |  | x |  | Có vai trò Chủ trọ hay không, mặc định không
is_tenant | BOOLEAN |  |  | x |  | Có vai trò Khách thuê hay không, mặc định không
phone_verified_at | DATETIME |  |  |  |  | Thời điểm xác minh số điện thoại bằng OTP; rỗng nghĩa là chưa xác minh
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng recovery_contacts ---
TIÊU ĐỀ: Bảng recovery_contacts
Mô tả: Bảng recovery_contacts lưu địa chỉ thư điện tử và số điện thoại phụ dùng để khôi phục mật khẩu. Mỗi tài khoản có tối đa hai địa chỉ thư điện tử và một số điện thoại phụ.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
user_id | INT |  |  | x | x | Tài khoản sở hữu
type | ENUM('EMAIL','PHONE') |  |  | x |  | Loại thông tin khôi phục: thư điện tử hoặc số điện thoại phụ
value | VARCHAR(255) |  |  | x |  | Địa chỉ thư điện tử hoặc số điện thoại
verified_at | DATETIME |  |  |  |  | Thời điểm xác minh bằng OTP; thông tin chưa xác minh không được dùng để khôi phục
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
Ràng buộc bổ sung: Duy nhất theo cặp (user_id, value).
--- Bảng otp_codes ---
TIÊU ĐỀ: Bảng otp_codes
Mô tả: Bảng otp_codes lưu các mã OTP đã gửi cho đăng ký, xác minh số điện thoại, khôi phục mật khẩu và xác minh thông tin khôi phục.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
user_id | INT |  |  |  | x | Tài khoản liên quan; rỗng khi đăng ký chưa có tài khoản
target | VARCHAR(255) |  |  | x |  | Số điện thoại hoặc địa chỉ thư điện tử nhận mã
purpose | ENUM('REGISTER','VERIFY_PHONE','RESET_PASSWORD','VERIFY_RECOVERY') |  |  | x |  | Mục đích sử dụng mã
code_hash | VARCHAR(255) |  |  | x |  | Mã OTP đã được băm, không lưu mã gốc
expires_at | DATETIME |  |  | x |  | Thời điểm hết hiệu lực, mặc định 5 phút sau khi tạo
attempt_count | INT |  |  | x |  | Số lần nhập sai, mã bị vô hiệu sau 5 lần sai
used_at | DATETIME |  |  |  |  | Thời điểm mã đã được sử dụng thành công
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng sessions ---
TIÊU ĐỀ: Bảng sessions
Mô tả: Bảng sessions lưu các phiên đăng nhập trên từng thiết bị, phục vụ làm mới phiên, đăng xuất và gửi thông báo đến thiết bị.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
user_id | INT |  |  | x | x | Tài khoản đăng nhập
refresh_token_hash | VARCHAR(255) |  | x | x |  | Mã làm mới phiên đã được băm
active_role | ENUM('LANDLORD','TENANT') |  |  | x |  | Vai trò người dùng đã chọn khi đăng nhập
push_token | VARCHAR(255) |  |  |  |  | Mã nhận thông báo đẩy của thiết bị
expires_at | DATETIME |  |  | x |  | Thời điểm phiên hết hạn
revoked_at | DATETIME |  |  |  |  | Thời điểm phiên bị kết thúc khi đăng xuất
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng boarding_houses ---
TIÊU ĐỀ: Bảng boarding_houses
Mô tả: Bảng boarding_houses lưu thông tin nhà trọ, tài khoản ngân hàng nhận tiền và thông tin kết nối dịch vụ thông báo biến động số dư. Mỗi Chủ trọ có đúng một nhà trọ.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
owner_id | INT |  | x | x | x | Tài khoản Chủ trọ sở hữu nhà trọ; duy nhất vì mỗi Chủ trọ chỉ quản lý một nhà trọ
name | VARCHAR(150) |  |  | x |  | Tên nhà trọ
address | VARCHAR(255) |  |  | x |  | Địa chỉ nhà trọ
billing_day | TINYINT |  |  | x |  | Ngày dự kiến lập phiếu báo phí hằng tháng, từ 1 đến 28
payment_due_days | TINYINT |  |  | x |  | Số ngày cho phép thanh toán, mặc định 5
bank_bin | VARCHAR(10) |  |  |  |  | Mã ngân hàng nhận tiền theo chuẩn VietQR
bank_account_no | VARCHAR(30) |  |  |  |  | Số tài khoản nhận tiền
bank_account_name | VARCHAR(100) |  |  |  |  | Tên chủ tài khoản nhận tiền
webhook_token | VARCHAR(64) |  | x |  |  | Chuỗi định danh riêng của nhà trọ trong địa chỉ tiếp nhận thông báo giao dịch
webhook_key_hash | VARCHAR(255) |  |  |  |  | Khóa xác thực thông báo giao dịch đã được băm; rỗng nghĩa là chưa kết nối
webhook_connected_at | DATETIME |  |  |  |  | Thời điểm kết nối dịch vụ thông báo biến động số dư
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng room_groups ---
TIÊU ĐỀ: Bảng room_groups
Mô tả: Bảng room_groups lưu các nhóm phòng của nhà trọ, mỗi nhóm tương ứng một dãy, khu hoặc tầng.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ chứa nhóm phòng
name | VARCHAR(100) |  |  | x |  | Tên nhóm phòng
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
Ràng buộc bổ sung: Duy nhất theo cặp (house_id, name).
--- Bảng rooms ---
TIÊU ĐỀ: Bảng rooms
Mô tả: Bảng rooms lưu thông tin và trạng thái của từng phòng trong nhà trọ.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ chứa phòng
group_id | INT |  |  |  | x | Nhóm phòng; rỗng nếu chưa xếp nhóm
name | VARCHAR(50) |  |  | x |  | Tên phòng
monthly_rent | INT |  |  | x |  | Giá thuê tháng niêm yết của phòng, đơn vị đồng
status | ENUM('VACANT','RESERVED','OCCUPIED','SUSPENDED') |  |  | x |  | Trạng thái: Trống, Đã giữ chỗ, Đang thuê, Tạm ngừng sử dụng
note | VARCHAR(255) |  |  |  |  | Ghi chú
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
Ràng buộc bổ sung: Duy nhất theo cặp (house_id, name).
--- Bảng services ---
TIÊU ĐỀ: Bảng services
Mô tả: Bảng services lưu các khoản điện, nước và dịch vụ khác do Chủ trọ khai báo cùng phương pháp tính.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ khai báo dịch vụ
name | VARCHAR(100) |  |  | x |  | Tên dịch vụ
fee_type | ENUM('ELECTRIC','WATER','OTHER') |  |  | x |  | Loại khoản phí: điện, nước hoặc dịch vụ khác
calc_method | ENUM('METER','PER_PERSON','PER_ROOM','PER_QUANTITY','FIXED') |  |  | x |  | Phương pháp tính: theo công tơ, theo người, theo phòng, theo số lượng, cố định
unit | VARCHAR(30) |  |  | x |  | Đơn vị tính, ví dụ kWh, m³, người, tháng
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
Ràng buộc bổ sung: Duy nhất theo cặp (house_id, name).
--- Bảng service_prices ---
TIÊU ĐỀ: Bảng service_prices
Mô tả: Bảng service_prices lưu lịch sử đơn giá của dịch vụ theo ngày hiệu lực. Mỗi lần đổi giá tạo một bản ghi mới, không ghi đè bản ghi cũ.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
service_id | INT |  |  | x | x | Dịch vụ áp dụng đơn giá
unit_price | INT |  |  | x |  | Đơn giá, đơn vị đồng, không âm
effective_from | DATE |  |  | x |  | Ngày bắt đầu hiệu lực
created_by | INT |  |  | x | x | Người thực hiện thay đổi
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng reservations ---
TIÊU ĐỀ: Bảng reservations
Mô tả: Bảng reservations lưu phiếu giữ phòng, tiền cọc giữ phòng đã thỏa thuận, đã thực nhận và kết quả xử lý tiền cọc khi hủy.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ
room_id | INT |  |  | x | x | Phòng được giữ
holder_name | VARCHAR(100) |  |  | x |  | Họ tên người giữ phòng
holder_phone | VARCHAR(15) |  |  | x |  | Số điện thoại người giữ phòng
agreed_rent | INT |  |  | x |  | Giá thuê tháng đã thỏa thuận, làm căn cứ giới hạn tiền cọc; mặc định lấy giá thuê niêm yết của phòng
expected_move_in | DATE |  |  | x |  | Ngày nhận phòng dự kiến
hold_until | DATE |  |  | x |  | Thời hạn giữ phòng
deposit_amount | INT |  |  | x |  | Số tiền cọc giữ phòng đã thỏa thuận, lớn hơn 0 và không vượt giá thuê một tháng đã thỏa thuận
deposit_terms | TEXT |  |  |  |  | Thỏa thuận xử lý tiền cọc
deposit_received | INT |  |  |  |  | Số tiền cọc thực nhận; rỗng nghĩa là chưa nhận
deposit_method | ENUM('CASH','TRANSFER') |  |  |  |  | Hình thức nhận cọc
deposit_confirmed_at | DATETIME |  |  |  |  | Thời điểm Chủ trọ xác nhận đã nhận cọc
status | ENUM('ACTIVE','EXPIRED','CANCELLED','CONVERTED') |  |  | x |  | Trạng thái: còn hiệu lực, quá hạn, đã hủy, đã lập hợp đồng
refund_amount | INT |  |  |  |  | Số tiền cọc hoàn lại khi hủy phiếu theo xác nhận của Chủ trọ
cancel_reason | VARCHAR(255) |  |  |  |  | Lý do hủy phiếu
created_by | INT |  |  | x | x | Người lập phiếu
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng contracts ---
TIÊU ĐỀ: Bảng contracts
Mô tả: Bảng contracts lưu hợp đồng thuê, gồm điều khoản hiện hành, chế độ thanh toán, tiền cọc bảo đảm và dữ liệu ban đầu của hợp đồng nhập vào hệ thống.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ
room_id | INT |  |  | x | x | Phòng thuê
reservation_id | INT |  | x |  | x | Phiếu giữ phòng làm căn cứ lập hợp đồng; rỗng với hợp đồng nhập
source | ENUM('FROM_RESERVATION','IMPORTED') |  |  | x |  | Nguồn tạo: lập từ phiếu giữ phòng hoặc nhập hợp đồng đang còn hiệu lực
start_date | DATE |  |  | x |  | Ngày bắt đầu thuê
end_date | DATE |  |  | x |  | Ngày kết thúc hợp đồng hiện hành
monthly_rent | INT |  |  | x |  | Giá thuê tháng đã thỏa thuận hiện hành, đơn vị đồng
payment_mode | ENUM('REPRESENTATIVE','SPLIT') |  |  | x |  | Chế độ thanh toán: đại diện hoặc chia đều
deposit_agreed | INT |  |  | x |  | Tiền cọc bảo đảm theo thỏa thuận
deposit_held | INT |  |  | x |  | Tiền cọc bảo đảm đang giữ (đã thực nhận)
reservation_offset | INT |  |  | x |  | Số tiền cọc giữ phòng cấn trừ một lần vào tiền thuê tháng đầu, tối đa bằng tiền thuê kỳ đầu; 0 với hợp đồng nhập
offset_refund_due | INT |  |  | x |  | Phần cọc giữ phòng vượt tiền thuê kỳ đầu, Chủ trọ cần hoàn cho người đặt cọc; mặc định 0
offset_refunded_at | DATETIME |  |  |  |  | Thời điểm Chủ trọ ghi nhận đã hoàn phần cọc vượt
offset_invoice_id | INT |  | x |  | x | Phiếu báo phí đã thực hiện cấn trừ; rỗng nghĩa là chưa cấn trừ
opening_debt | INT |  |  | x |  | Công nợ đầu kỳ khi nhập hợp đồng đang thuê, là số dư ban đầu và không tạo khoản thu mới; mặc định 0
terms_note | TEXT |  |  |  |  | Điều khoản khác
status | ENUM('ACTIVE','PENDING_LIQUIDATION','LIQUIDATED') |  |  | x |  | Trạng thái: còn hiệu lực, chờ thanh lý, đã thanh lý
move_out_date | DATE |  |  |  |  | Ngày dự kiến trả phòng do Khách thuê đề nghị
termination_date | DATE |  |  |  |  | Ngày chấm dứt được hai bên chấp thuận
created_by | INT |  |  | x | x | Người lập hợp đồng
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng contract_members ---
TIÊU ĐỀ: Bảng contract_members
Mô tả: Bảng contract_members lưu thành viên của hợp đồng, vai trò đứng tên, trách nhiệm thanh toán và khoản trả dư của từng thành viên.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
contract_id | INT |  |  | x | x | Hợp đồng
user_id | INT |  |  |  | x | Tài khoản Khách thuê liên kết; rỗng với người cư trú không có số điện thoại
full_name | VARCHAR(100) |  |  | x |  | Họ tên thành viên
phone | VARCHAR(15) |  |  |  |  | Số điện thoại
is_holder | BOOLEAN |  |  | x |  | Là người đứng tên hợp đồng; mỗi hợp đồng có đúng một người
is_representative | BOOLEAN |  |  | x |  | Là người đại diện thanh toán ở chế độ đại diện
is_payer | BOOLEAN |  |  | x |  | Chịu trách nhiệm thanh toán ở chế độ chia đều
sort_order | INT |  |  | x |  | Thứ tự trong danh sách, dùng để cộng phần dư khi chia đều
credit_balance | INT |  |  | x |  | Khoản trả dư chưa xử lý, mặc định 0
joined_at | DATE |  |  | x |  | Ngày bắt đầu là thành viên
left_at | DATE |  |  |  |  | Ngày rời hợp đồng
--- Bảng contract_services ---
TIÊU ĐỀ: Bảng contract_services
Mô tả: Bảng contract_services lưu lịch sử áp dụng hoặc ngừng áp dụng dịch vụ cho từng hợp đồng cùng số suất tính phí. Mỗi thay đổi tạo một bản ghi mới kèm ngày hiệu lực.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
contract_id | INT |  |  | x | x | Hợp đồng
service_id | INT |  |  | x | x | Dịch vụ
is_applied | BOOLEAN |  |  | x |  | Áp dụng (đúng) hoặc ngừng áp dụng (sai) từ ngày hiệu lực
quantity | INT |  |  | x |  | Số suất tính phí hoặc số lượng theo thỏa thuận; bằng 1 với khoản theo phòng hoặc cố định
effective_from | DATE |  |  | x |  | Ngày bắt đầu hiệu lực
created_by | INT |  |  | x | x | Người thực hiện
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng contract_changes ---
TIÊU ĐỀ: Bảng contract_changes
Mô tả: Bảng contract_changes lưu đề nghị gia hạn, điều chỉnh hợp đồng và kết quả xác nhận của người đứng tên. Các bản ghi đã xác nhận tạo thành lịch sử phiên bản điều khoản.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
contract_id | INT |  |  | x | x | Hợp đồng
kind | ENUM('EXTEND','ADJUST') |  |  | x |  | Loại thay đổi: gia hạn hoặc điều chỉnh
proposed_by | INT |  |  | x | x | Người gửi đề nghị
content | TEXT |  |  | x |  | Nội dung đề nghị hoặc nội dung hai bên đã thống nhất
changes | JSON |  |  |  |  | Giá trị mới đã thống nhất như ngày kết thúc, giá thuê, thành viên, chế độ thanh toán
effective_date | DATE |  |  |  |  | Ngày hiệu lực của thay đổi
status | ENUM('PROPOSED','AWAITING_CONFIRM','CONFIRMED','REJECTED','CLOSED') |  |  | x |  | Trạng thái: đã đề nghị, chờ người đứng tên xác nhận, đã xác nhận, bị từ chối, đã đóng
confirmed_by | INT |  |  |  | x | Người đứng tên đã xác nhận
confirmed_at | DATETIME |  |  |  |  | Thời điểm xác nhận
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng handovers ---
TIÊU ĐỀ: Bảng handovers
Mô tả: Bảng handovers lưu biên bản bàn giao khi nhận phòng và khi trả phòng.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
contract_id | INT |  |  | x | x | Hợp đồng
type | ENUM('MOVE_IN','MOVE_OUT') |  |  | x |  | Loại biên bản: nhận phòng hoặc trả phòng
condition_note | TEXT |  |  | x |  | Hiện trạng phòng
assets | JSON |  |  | x |  | Danh sách tài sản gồm tên, số lượng, tình trạng
key_count | INT |  |  | x |  | Số lượng chìa khóa giao hoặc nhận lại
electric_reading | INT |  |  |  |  | Chỉ số điện tại thời điểm bàn giao
water_reading | INT |  |  |  |  | Chỉ số nước tại thời điểm bàn giao
damage_note | TEXT |  |  |  |  | Hư hỏng, thiếu hụt ghi nhận khi trả phòng
status | ENUM('PENDING_CONFIRM','DISPUTED','CONFIRMED','COMPLETED_UNCONFIRMED') |  |  | x |  | Trạng thái: chờ khách xác nhận, khách phản hồi, khách đã xác nhận, Chủ trọ hoàn tất ghi nhận khi khách chưa xác nhận
tenant_feedback | TEXT |  |  |  |  | Nội dung phản hồi của Khách thuê
confirmed_by | INT |  |  |  | x | Khách thuê đã xác nhận
confirmed_at | DATETIME |  |  |  |  | Thời điểm xác nhận
completion_note | TEXT |  |  |  |  | Ghi chú của Chủ trọ khi hoàn tất ghi nhận mà khách chưa xác nhận
completed_by | INT |  |  |  | x | Chủ trọ hoàn tất ghi nhận
completed_at | DATETIME |  |  |  |  | Thời điểm hoàn tất ghi nhận
created_by | INT |  |  | x | x | Người lập biên bản
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
Ràng buộc bổ sung: Duy nhất theo cặp (contract_id, type).
--- Bảng meters ---
TIÊU ĐỀ: Bảng meters
Mô tả: Bảng meters lưu công tơ điện, nước của từng phòng. Khi thay công tơ, bản ghi cũ được ghi chỉ số cuối và một bản ghi mới được tạo.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
room_id | INT |  |  | x | x | Phòng lắp công tơ
type | ENUM('ELECTRIC','WATER') |  |  | x |  | Loại công tơ
start_reading | INT |  |  | x |  | Chỉ số đầu khi lắp
installed_on | DATE |  |  | x |  | Ngày lắp
final_reading | INT |  |  |  |  | Chỉ số cuối khi tháo
removed_on | DATE |  |  |  |  | Ngày tháo; rỗng nghĩa là công tơ đang dùng
created_by | INT |  |  | x | x | Người ghi nhận
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng meter_readings ---
TIÊU ĐỀ: Bảng meter_readings
Mô tả: Bảng meter_readings lưu chỉ số công tơ đã chốt theo kỳ. Chỉ số đã chốt không bị sửa hoặc xóa trực tiếp; mọi điều chỉnh được ghi vào nhật ký thay đổi.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
meter_id | INT |  |  | x | x | Công tơ
period | CHAR(7) |  |  | x |  | Kỳ ghi chỉ số theo dạng YYYY-MM
reading | INT |  |  | x |  | Chỉ số đã chốt
is_abnormal | BOOLEAN |  |  | x |  | Có cảnh báo tiêu thụ bất thường khi chốt
locked_by | INT |  |  | x | x | Người chốt chỉ số
locked_at | DATETIME |  |  | x |  | Thời điểm chốt
updated_at | DATETIME |  |  | x |  | Thời điểm điều chỉnh gần nhất
Ràng buộc bổ sung: Duy nhất theo cặp (meter_id, period).
--- Bảng reading_feedbacks ---
TIÊU ĐỀ: Bảng reading_feedbacks
Mô tả: Bảng reading_feedbacks lưu phản hồi của Khách thuê về chỉ số đã chốt và kết quả xử lý của Chủ trọ.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
reading_id | INT |  |  | x | x | Chỉ số được phản hồi
tenant_id | INT |  |  | x | x | Khách thuê gửi phản hồi
content | TEXT |  |  | x |  | Nội dung phản hồi
status | ENUM('OPEN','CLOSED') |  |  | x |  | Trạng thái: đang mở hoặc đã đóng
reply | TEXT |  |  |  |  | Trả lời của Chủ trọ
handled_by | INT |  |  |  | x | Người xử lý
handled_at | DATETIME |  |  |  |  | Thời điểm xử lý
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng invoices ---
TIÊU ĐỀ: Bảng invoices
Mô tả: Bảng invoices lưu phiếu báo phí của hợp đồng theo kỳ. Phiếu đã phát hành chưa có thanh toán được xác nhận được chỉnh sửa trên cùng phiếu và lưu lịch sử; phiếu đã có thanh toán không được chỉnh sửa hoặc hủy.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ
contract_id | INT |  |  | x | x | Hợp đồng
period | CHAR(7) |  |  | x |  | Kỳ báo phí theo dạng YYYY-MM
period_start | DATE |  |  | x |  | Ngày bắt đầu kỳ tính phí
period_end | DATE |  |  | x |  | Ngày kết thúc kỳ tính phí
status | ENUM('DRAFT','ISSUED') |  |  | x |  | Trạng thái: nháp hoặc đã phát hành
missing_reading | BOOLEAN |  |  | x |  | Phiếu còn thiếu chỉ số chốt cho khoản theo công tơ
total_amount | INT |  |  | x |  | Tổng số tiền của phiếu
issued_at | DATETIME |  |  |  |  | Ngày phát hành thực tế
due_date | DATE |  |  |  |  | Hạn thanh toán bằng ngày phát hành cộng số ngày cho phép thanh toán
is_adjusted | BOOLEAN |  |  | x |  | Phiếu đã được chỉnh sửa sau khi phát hành, hiển thị dấu “Đã điều chỉnh”; mặc định không
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng invoice_lines ---
TIÊU ĐỀ: Bảng invoice_lines
Mô tả: Bảng invoice_lines lưu từng khoản cấu thành phiếu báo phí, gồm số tiền theo cấu hình và số tiền sau điều chỉnh.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
invoice_id | INT |  |  | x | x | Phiếu báo phí
line_type | ENUM('RENT','ELECTRIC','WATER','SERVICE','EXTRA','RESERVATION_OFFSET','OPENING_DEBT','ADJUSTMENT') |  |  | x |  | Loại khoản: tiền phòng, điện, nước, dịch vụ, phát sinh, cấn trừ cọc giữ phòng, công nợ đầu kỳ, khoản điều chỉnh chuyển từ phiếu trước
service_id | INT |  |  |  | x | Dịch vụ tương ứng nếu có
description | VARCHAR(255) |  |  | x |  | Diễn giải khoản mục
quantity | INT |  |  | x |  | Số lượng tính phí như số ngày, số kWh, số m³, số suất
unit_price | INT |  |  | x |  | Đơn giá áp dụng
old_reading | INT |  |  |  |  | Chỉ số cũ với khoản theo công tơ
new_reading | INT |  |  |  |  | Chỉ số mới với khoản theo công tơ
default_amount | INT |  |  | x |  | Số tiền tính theo cấu hình
amount | INT |  |  | x |  | Số tiền phải thu sau điều chỉnh; âm với khoản cấn trừ hoặc khoản giảm
adjust_reason | VARCHAR(255) |  |  |  |  | Lý do điều chỉnh; tùy chọn với phiếu nháp
adjustment_id | INT |  |  |  | x | Khoản điều chỉnh riêng của phiếu trước được đưa vào phiếu này
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng invoice_obligations ---
TIÊU ĐỀ: Bảng invoice_obligations
Mô tả: Bảng invoice_obligations lưu nghĩa vụ thanh toán được phân bổ từ phiếu báo phí cho người đại diện hoặc từng thành viên chịu trách nhiệm thanh toán.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
invoice_id | INT |  |  | x | x | Phiếu báo phí
member_id | INT |  |  | x | x | Thành viên có nghĩa vụ
payment_code | VARCHAR(20) |  | x | x |  | Mã thanh toán riêng của phần phải trả
share_amount | INT |  |  | x |  | Số tiền được phân bổ
credit_applied | INT |  |  | x |  | Khoản trả dư được bù trừ vào phần này
amount_due | INT |  |  | x |  | Số tiền phải trả bằng số được phân bổ trừ khoản bù trừ
amount_paid | INT |  |  | x |  | Số tiền đã thanh toán được xác nhận
sort_order | INT |  |  | x |  | Thứ tự trong danh sách
status | ENUM('UNPAID','PARTIAL','PAID') |  |  | x |  | Trạng thái: chưa trả, trả một phần, đã trả đủ
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng invoice_adjustments ---
TIÊU ĐỀ: Bảng invoice_adjustments
Mô tả: Bảng invoice_adjustments lưu khoản điều chỉnh tăng hoặc giảm ghi nhận riêng cho phiếu đã có thanh toán được xác nhận, liên kết với phiếu gốc mà không sửa nội dung phiếu gốc.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
invoice_id | INT |  |  | x | x | Phiếu báo phí gốc
direction | ENUM('INCREASE','DECREASE') |  |  | x |  | Loại điều chỉnh: tăng hoặc giảm
amount | INT |  |  | x |  | Số tiền điều chỉnh, lớn hơn 0
reason | VARCHAR(255) |  |  | x |  | Lý do điều chỉnh
handling | ENUM('NEXT_PERIOD','REFUND','SETTLEMENT') |  |  | x |  | Cách xử lý: đưa vào kỳ sau, hoàn tiền (chỉ với điều chỉnh giảm), xử lý khi quyết toán (chỉ với điều chỉnh tăng)
status | ENUM('PENDING','APPLIED','REFUNDED','SETTLED') |  |  | x |  | Trạng thái: chờ xử lý, đã đưa vào phiếu kỳ sau, đã hoàn tiền, đã xử lý khi quyết toán
handled_at | DATETIME |  |  |  |  | Thời điểm xử lý xong
created_by | INT |  |  | x | x | Chủ trọ ghi nhận
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng payment_requests ---
TIÊU ĐỀ: Bảng payment_requests
Mô tả: Bảng payment_requests lưu yêu cầu thanh toán VietQR do Khách thuê tạo và thông tin báo chuyển khoản kèm kết quả xác nhận thủ công.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
invoice_id | INT |  |  | x | x | Phiếu báo phí
obligation_id | INT |  |  |  | x | Phần phải trả được thanh toán; rỗng khi dùng mã tổng của phòng
requested_by | INT |  |  | x | x | Khách thuê tạo yêu cầu
amount | INT |  |  | x |  | Số tiền yêu cầu, lớn hơn 0 và không vượt số dư còn phải trả
reference_code | VARCHAR(20) |  | x | x |  | Mã tham chiếu ghi trong nội dung chuyển khoản
status | ENUM('PENDING','PAID','EXPIRED','CANCELLED') |  |  | x |  | Trạng thái: chờ thanh toán, đã thanh toán, hết hạn, đã vô hiệu do phiếu được chỉnh sửa
expires_at | DATETIME |  |  | x |  | Thời điểm hết hạn, 15 phút sau khi tạo
report_status | ENUM('NONE','REPORTED','CONFIRMED','REJECTED') |  |  | x |  | Trạng thái báo chuyển khoản
reported_at | DATETIME |  |  |  |  | Thời điểm Khách thuê báo đã chuyển
reject_reason | VARCHAR(255) |  |  |  |  | Lý do Chủ trọ từ chối báo chuyển khoản
reviewed_by | INT |  |  |  | x | Chủ trọ xử lý báo chuyển khoản
reviewed_at | DATETIME |  |  |  |  | Thời điểm xử lý
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng bank_transactions ---
TIÊU ĐỀ: Bảng bank_transactions
Mô tả: Bảng bank_transactions lưu giao dịch tiền vào do dịch vụ thông báo biến động số dư gửi đến và kết quả đối chiếu.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ nhận thông báo
provider_txn_id | VARCHAR(64) |  |  | x |  | Mã định danh giao dịch do dịch vụ cung cấp
account_no | VARCHAR(30) |  |  | x |  | Số tài khoản nhận
amount | INT |  |  | x |  | Số tiền giao dịch
content | VARCHAR(255) |  |  | x |  | Nội dung chuyển khoản
transaction_date | DATETIME |  |  | x |  | Thời điểm ngân hàng ghi nhận giao dịch
raw_payload | JSON |  |  | x |  | Dữ liệu gốc nhận được
result | ENUM('AUTO_CONFIRMED','NEED_RECONCILE','RECONCILED','UNRELATED') |  |  | x |  | Kết quả: tự động xác nhận, cần đối chiếu, đã đối chiếu, không liên quan
reason | VARCHAR(255) |  |  |  |  | Nguyên nhân không tự xác nhận (kể cả nghi trùng với khoản đã xác nhận thủ công) hoặc lý do không liên quan
payment_request_id | INT |  |  |  | x | Yêu cầu thanh toán khớp nếu có
handled_by | INT |  |  |  | x | Chủ trọ đối chiếu thủ công
handled_at | DATETIME |  |  |  |  | Thời điểm đối chiếu
received_at | DATETIME |  |  | x |  | Thời điểm máy chủ nhận thông báo
Ràng buộc bổ sung: Duy nhất theo cặp (house_id, provider_txn_id) để không ghi nhận một giao dịch hai lần.
--- Bảng payments ---
TIÊU ĐỀ: Bảng payments
Mô tả: Bảng payments lưu khoản thanh toán đã được xác nhận cho phiếu báo phí, từ tiền mặt, xác nhận thủ công, tự động xác nhận, đối chiếu thủ công hoặc cấn trừ từ tiền cọc khi quyết toán.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ
invoice_id | INT |  |  | x | x | Phiếu báo phí được thanh toán
payer_member_id | INT |  |  |  | x | Thành viên đã trả tiền
method | ENUM('CASH','TRANSFER','DEPOSIT_OFFSET') |  |  | x |  | Hình thức: tiền mặt, chuyển khoản hoặc cấn trừ từ tiền cọc; cấn trừ từ tiền cọc không tính vào tiền thực thu
source | ENUM('CASH','TRANSFER_REPORT','AUTO_BANK','RECONCILE','SETTLEMENT') |  |  | x |  | Nguồn xác nhận
amount | INT |  |  | x |  | Số tiền được ghi nhận
payment_request_id | INT |  | x |  | x | Yêu cầu thanh toán tương ứng; duy nhất để một yêu cầu chỉ được xác nhận một lần
bank_transaction_id | INT |  | x |  | x | Giao dịch ngân hàng tương ứng; duy nhất để một giao dịch chỉ tạo một khoản thu
note | VARCHAR(255) |  |  |  |  | Ghi chú
confirmed_by | INT |  |  |  | x | Chủ trọ xác nhận; rỗng khi hệ thống tự động xác nhận
confirmed_at | DATETIME |  |  | x |  | Thời điểm xác nhận
--- Bảng payment_allocations ---
TIÊU ĐỀ: Bảng payment_allocations
Mô tả: Bảng payment_allocations lưu việc phân bổ một khoản thu vào một hoặc nhiều phần phải trả.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
payment_id | INT |  |  | x | x | Khoản thu
obligation_id | INT |  |  | x | x | Phần phải trả được thanh toán
amount | INT |  |  | x |  | Số tiền phân bổ
--- Bảng incidents ---
TIÊU ĐỀ: Bảng incidents
Mô tả: Bảng incidents lưu yêu cầu sự cố, kết quả xử lý, chi phí và bên chịu chi phí.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ
room_id | INT |  |  | x | x | Phòng xảy ra sự cố
contract_id | INT |  |  |  | x | Hợp đồng liên quan; rỗng khi Chủ trọ tạo cho phòng trống
reported_by | INT |  |  | x | x | Người tạo yêu cầu
description | TEXT |  |  | x |  | Nội dung mô tả
severity | ENUM('LOW','MEDIUM','HIGH') |  |  | x |  | Mức độ ảnh hưởng: thấp, trung bình, cao
status | ENUM('NEW','IN_PROGRESS','AWAITING_CONFIRM','DONE') |  |  | x |  | Trạng thái: mới, đang xử lý, chờ khách xác nhận, hoàn tất
cause | TEXT |  |  |  |  | Nguyên nhân
result | TEXT |  |  |  |  | Kết quả xử lý
cost_amount | INT |  |  |  |  | Chi phí phát sinh
cost_bearer | ENUM('LANDLORD','TENANT') |  |  |  |  | Bên chịu chi phí
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
closed_at | DATETIME |  |  |  |  | Thời điểm hoàn tất
--- Bảng incident_updates ---
TIÊU ĐỀ: Bảng incident_updates
Mô tả: Bảng incident_updates lưu từng lần cập nhật tiến độ, kết quả và phản hồi của một yêu cầu sự cố.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
incident_id | INT |  |  | x | x | Sự cố
author_id | INT |  |  | x | x | Người cập nhật
content | TEXT |  |  | x |  | Nội dung cập nhật hoặc phản hồi
status_after | ENUM('NEW','IN_PROGRESS','AWAITING_CONFIRM','DONE') |  |  | x |  | Trạng thái sau lần cập nhật
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng extra_charges ---
TIÊU ĐỀ: Bảng extra_charges
Mô tả: Bảng extra_charges lưu khoản phát sinh do Khách thuê chịu, chẳng hạn chi phí sửa chữa, để đưa vào phiếu báo phí.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
contract_id | INT |  |  | x | x | Hợp đồng chịu khoản phát sinh
incident_id | INT |  |  |  | x | Sự cố làm phát sinh khoản này nếu có
description | VARCHAR(255) |  |  | x |  | Nội dung khoản phát sinh
amount | INT |  |  | x |  | Số tiền
invoice_id | INT |  |  |  | x | Phiếu báo phí đã đưa khoản này vào; rỗng nghĩa là chưa đưa vào phiếu
created_by | INT |  |  | x | x | Người ghi nhận
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng finance_entries ---
TIÊU ĐỀ: Bảng finance_entries
Mô tả: Bảng finance_entries lưu khoản thu chi khác do Chủ trọ nhập và các khoản thu chi hệ thống tự ghi nhận từ nghiệp vụ như chi phí sửa chữa, tiền cọc giữ lại hoặc khấu trừ khi quyết toán.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ
type | ENUM('INCOME','EXPENSE') |  |  | x |  | Loại: thu hoặc chi
source | ENUM('MANUAL','INCIDENT','RESERVATION','SETTLEMENT') |  |  | x |  | Nguồn: nhập tay, sự cố, phiếu giữ phòng, quyết toán
source_id | INT |  |  |  |  | Mã bản ghi nghiệp vụ nguồn
description | VARCHAR(255) |  |  | x |  | Nội dung
amount | INT |  |  | x |  | Số tiền, lớn hơn 0
occurred_on | DATE |  |  | x |  | Ngày phát sinh
created_by | INT |  |  |  | x | Người nhập; rỗng khi hệ thống tự ghi nhận
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng settlements ---
TIÊU ĐỀ: Bảng settlements
Mô tả: Bảng settlements lưu bảng quyết toán khi thanh lý hợp đồng.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
contract_id | INT |  | x | x | x | Hợp đồng được quyết toán
deposit_held | INT |  |  | x |  | Tiền cọc bảo đảm đang giữ
outstanding_debt | INT |  |  | x |  | Công nợ còn thiếu
deposit_used_for_debt | INT |  |  | x |  | Phần tiền cọc dùng cấn trừ công nợ đã có; không ghi nhận thành doanh thu mới
result_amount | INT |  |  | x |  | Kết quả: dương là số tiền hoàn cho khách, âm là số tiền khách phải trả thêm
status | ENUM('DRAFT','SENT','COMPLETED') |  |  | x |  | Trạng thái: đang lập, đã gửi khách xem, đã hoàn tất
completed_by | INT |  |  |  | x | Chủ trọ hoàn tất quyết toán
completed_at | DATETIME |  |  |  |  | Thời điểm hoàn tất
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
updated_at | DATETIME |  |  | x |  | Thời điểm cập nhật gần nhất
--- Bảng settlement_items ---
TIÊU ĐỀ: Bảng settlement_items
Mô tả: Bảng settlement_items lưu các khoản cấu thành bảng quyết toán.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
settlement_id | INT |  |  | x | x | Bảng quyết toán
kind | ENUM('RENT_DUE','PREPAID_REFUND','DEDUCTION','OTHER_CHARGE','ADJUSTMENT') |  |  | x |  | Loại: tiền thuê phải trả đến ngày chấm dứt, tiền thuê trả trước được hoàn, khấu trừ hoặc bồi thường, khoản phải thu khác, khoản điều chỉnh chờ quyết toán
adjustment_id | INT |  |  |  | x | Khoản điều chỉnh được xử lý trong quyết toán nếu có
is_revenue | BOOLEAN |  |  | x |  | Khoản khấu trừ có bản chất doanh thu, được ghi nhận doanh thu khi hoàn tất; mặc định không
description | VARCHAR(255) |  |  | x |  | Nội dung
amount | INT |  |  | x |  | Số tiền
reason | VARCHAR(255) |  |  |  |  | Căn cứ; bắt buộc với khoản khấu trừ
--- Bảng announcements ---
TIÊU ĐỀ: Bảng announcements
Mô tả: Bảng announcements lưu thông báo chung do Chủ trọ gửi cho khách thuê.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ
title | VARCHAR(150) |  |  | x |  | Tiêu đề
content | TEXT |  |  | x |  | Nội dung
target | ENUM('ALL','ROOMS') |  |  | x |  | Đối tượng nhận: toàn bộ khách thuê hoặc theo phòng
room_ids | JSON |  |  |  |  | Danh sách phòng nhận khi gửi theo phòng
created_by | INT |  |  | x | x | Người gửi
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng notifications ---
TIÊU ĐỀ: Bảng notifications
Mô tả: Bảng notifications lưu thông báo trong ứng dụng của từng tài khoản và trạng thái chuyển đến thiết bị.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
user_id | INT |  |  | x | x | Tài khoản nhận
house_id | INT |  |  |  | x | Nhà trọ liên quan
type | VARCHAR(50) |  |  | x |  | Loại thông báo như phiếu báo phí, nhắc thanh toán, kết quả thanh toán, sự cố, hợp đồng, thông báo chung
title | VARCHAR(150) |  |  | x |  | Tiêu đề
body | TEXT |  |  | x |  | Nội dung
ref_type | VARCHAR(30) |  |  |  |  | Loại đối tượng liên quan như invoice, incident, contract
ref_id | INT |  |  |  |  | Mã đối tượng liên quan
read_at | DATETIME |  |  |  |  | Thời điểm đã đọc
push_status | ENUM('PENDING','SENT','FAILED') |  |  | x |  | Kết quả chuyển thông báo đến thiết bị
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng attachments ---
TIÊU ĐỀ: Bảng attachments
Mô tả: Bảng attachments lưu đường dẫn hình ảnh và chứng từ. Tệp được lưu trong thư mục trên máy chủ, cơ sở dữ liệu chỉ lưu đường dẫn.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  | x | x | Nhà trọ sở hữu tệp, dùng để kiểm tra quyền truy cập
owner_type | ENUM('METER_READING','METER','HANDOVER','CONTRACT','CONTRACT_CHANGE','INCIDENT','PAYMENT_REQUEST','FINANCE_ENTRY') |  |  | x |  | Loại đối tượng sở hữu tệp
owner_id | INT |  |  | x |  | Mã đối tượng sở hữu tệp
file_path | VARCHAR(255) |  |  | x |  | Đường dẫn tệp trên máy chủ
uploaded_by | INT |  |  | x | x | Người tải lên
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi
--- Bảng audit_logs ---
TIÊU ĐỀ: Bảng audit_logs
Mô tả: Bảng audit_logs lưu lịch sử điều chỉnh dữ liệu quan trọng như chỉ số đã chốt, phiếu đã phát hành, giao dịch đã xác nhận, hợp đồng và phiếu giữ phòng. Người dùng không thể sửa hoặc xóa bảng này.
Thuộc tính | Kiểu dữ liệu | K | U | M | F | Diễn giải
id | INT | x | x | x |  | Mã định danh, tự tăng
house_id | INT |  |  |  | x | Nhà trọ liên quan
actor_id | INT |  |  |  | x | Người thực hiện; rỗng khi hệ thống tự thực hiện
entity_type | VARCHAR(50) |  |  | x |  | Loại đối tượng bị thay đổi
entity_id | INT |  |  | x |  | Mã đối tượng bị thay đổi
action | VARCHAR(50) |  |  | x |  | Hành động như điều chỉnh, hủy, gia hạn, xác nhận
before_data | JSON |  |  |  |  | Giá trị trước khi thay đổi
after_data | JSON |  |  |  |  | Giá trị sau khi thay đổi
reason | VARCHAR(255) |  |  |  |  | Lý do thay đổi
created_at | DATETIME |  |  | x |  | Thời điểm tạo bản ghi

KIỂM TRA SAU KHI LÀM (báo lại kết quả từng dòng):
1. Mục 3.1.3 có một đoạn văn và đúng 36 bảng, từ "Bảng users" đến "Bảng audit_logs", mỗi bảng có 7 cột và dòng đầu "Mô tả: ...".
2. Sau khi cập nhật toàn bộ trường (Ctrl+A rồi F9), hai chú thích của mục 3.1 là Hình 3-1 và Hình 3-2. Cập nhật Mục lục và Mục lục các hình vẽ.
