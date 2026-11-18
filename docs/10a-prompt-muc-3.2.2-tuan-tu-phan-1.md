PROMPT 10a – MỤC 3.2.2 SƠ ĐỒ TUẦN TỰ (dán toàn bộ nội dung dưới đây cho AI Word; chỉ dùng sau khi đã chạy xong Prompt 09)

VAI TRÒ: Bạn là người triển khai nội dung vào tài liệu LVTN.docx. Toàn bộ nội dung dưới đây đã được phân tích và chốt. Bạn chèn đúng nguyên văn từng chữ. Không tự viết thêm, không diễn đạt lại, không rút gọn, không suy luận, không sửa phần khác của tài liệu.

PHẠM VI: Chỉ làm việc trong mục "3.2.2 Sơ đồ tuần tự" (từ tiêu đề 3.2.2 đến trước tiêu đề "3.2.3 Sơ đồ hoạt động").

VIỆC 1 – XÓA phần còn sót của đề tài khác: tiêu đề "3.2.2.1 Sơ đồ tuần tự của use case quản lý hồ sơ và điểm uy tín", gạch đầu dòng "Cập nhật thông tin tài khoản" ngay dưới nó và chú thích "Sơ đồ tuần tự cập nhật thông tin tài khoản" (kể cả hình nếu có). Giữ tiêu đề "3.2.2 Sơ đồ tuần tự".

VIỆC 2 – CHÈN ngay dưới tiêu đề "3.2.2 Sơ đồ tuần tự" một đoạn văn và 17 mục con theo đúng thứ tự dưới đây.

ĐỊNH DẠNG:
- Tiêu đề mục con: dùng đúng kiểu và cách đánh số tự động của tiêu đề cấp 4 (như "2.3.1.5 Quy trình đổi mật khẩu"); số mục sẽ là 3.2.2.1 đến 3.2.2.17.
- Dòng bắt đầu bằng "GẠCH ĐẦU DÒNG:" là một gạch đầu dòng, dùng đúng kiểu gạch đầu dòng đang có ở mục 3.2.2 (dòng "Cập nhật thông tin tài khoản" sắp bị xóa); chỉ ghi phần chữ sau dấu hai chấm.
- Khối mô tả sơ đồ: chèn nguyên văn từ dòng "[[MÔ TẢ SƠ ĐỒ: ...]]" đến dòng "[[HẾT MÔ TẢ]]", mỗi dòng là một đoạn riêng, phông Consolas cỡ 10, căn trái, giữ nguyên khoảng trắng đầu dòng. Đây là chỗ giữ chỗ cho hình.
- Chú thích hình: đặt ngay dưới khối mô tả sơ đồ, tạo bằng cơ chế chú thích có trường đánh số tự động, đúng kiểu chú thích hình đang có. Không gõ tay số hình.
- Thứ tự: Tiêu đề mục con → (Gạch đầu dòng → Khối mô tả → Chú thích) lặp lại cho từng chức năng.

ĐOẠN VĂN (đặt ngay dưới tiêu đề 3.2.2):
Sơ đồ tuần tự mô tả trình tự trao đổi thông điệp giữa tác nhân, ứng dụng di động, máy chủ API, cơ sở dữ liệu và dịch vụ bên ngoài khi thực hiện từng chức năng mở rộng ở mục 3.2.1. Ứng dụng gọi máy chủ qua REST API sử dụng HTTPS; máy chủ xác thực mã truy cập, kiểm tra quyền theo nhà trọ hoặc hợp đồng, kiểm tra quy tắc nghiệp vụ rồi đọc, ghi dữ liệu thông qua Prisma ORM. Các thao tác ghi nhận tài chính gồm nhiều bước được thực hiện trong một giao dịch cơ sở dữ liệu để bảo đảm thành công trọn vẹn hoặc không lưu phần nào.

===== MỤC 3.2.2.1 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý tài khoản và xác thực
GẠCH ĐẦU DÒNG: Đăng ký tài khoản Chủ trọ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự đăng ký tài khoản Chủ trọ]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ SMS OTP
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Nhập số điện thoại, mật khẩu, xác nhận mật khẩu, chọn “Đăng ký”
2. Ứng dụng di động → Máy chủ API: POST /api/auth/register {phone, password}
3. Máy chủ API → Máy chủ API: Kiểm tra định dạng dữ liệu
4. Máy chủ API → Cơ sở dữ liệu: Tìm users theo phone
5. Máy chủ API ⇢ Cơ sở dữ liệu: Kết quả tìm kiếm
[Khung alt – điều kiện: Dữ liệu không hợp lệ hoặc số điện thoại đã tồn tại]
  6. Máy chủ API ⇢ Ứng dụng di động: 400/409 kèm thông báo lỗi
  7. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi hoặc hướng dẫn đăng nhập
[Nhánh khác – điều kiện: Hợp lệ]
  8. Máy chủ API → Cơ sở dữ liệu: Lưu otp_codes (REGISTER, code_hash, expires_at)
  9. Máy chủ API → Dịch vụ SMS OTP: Gửi mã OTP qua SMS
  10. Máy chủ API ⇢ Ứng dụng di động: 200 Đã gửi mã
  11. Chủ trọ → Ứng dụng di động: Nhập mã OTP
  12. Ứng dụng di động → Máy chủ API: POST /api/auth/register/verify {phone, password, otp}
  13. Máy chủ API → Cơ sở dữ liệu: Đối chiếu otp_codes
  [Khung alt – điều kiện: Mã sai hoặc hết hiệu lực]
    14. Máy chủ API ⇢ Ứng dụng di động: 400 Mã không hợp lệ
    15. Ứng dụng di động ⇢ Chủ trọ: Cho nhập lại hoặc gửi mã mới
  [Nhánh khác – điều kiện: Mã đúng]
    16. Máy chủ API → Cơ sở dữ liệu: Tạo users (is_landlord = true, phone_verified_at), đánh dấu used_at
    17. Máy chủ API → Cơ sở dữ liệu: Tạo sessions
    18. Máy chủ API ⇢ Ứng dụng di động: 201 Token đăng nhập
    19. Ứng dụng di động ⇢ Chủ trọ: Chuyển đến màn hình thiết lập nhà trọ
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự đăng ký tài khoản Chủ trọ
GẠCH ĐẦU DÒNG: Đăng nhập tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự đăng nhập tài khoản]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ SMS OTP
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Chọn vai trò, nhập số điện thoại, mật khẩu, chọn “Đăng nhập”
2. Ứng dụng di động → Máy chủ API: POST /api/auth/login {phone, password, role}
3. Máy chủ API → Cơ sở dữ liệu: Tìm users theo phone
4. Máy chủ API ⇢ Cơ sở dữ liệu: Tài khoản
5. Máy chủ API → Máy chủ API: So khớp mật khẩu đã băm, kiểm tra vai trò
[Khung alt – điều kiện: Sai thông tin hoặc không có vai trò đã chọn]
  6. Máy chủ API ⇢ Ứng dụng di động: 401 Thông tin đăng nhập không đúng
  7. Ứng dụng di động ⇢ Người dùng: Hiển thị lỗi
[Nhánh khác – điều kiện: Đúng]
  [Khung alt – điều kiện: Số điện thoại chưa xác minh]
    8. Máy chủ API → Cơ sở dữ liệu: Lưu otp_codes (VERIFY_PHONE)
    9. Máy chủ API → Dịch vụ SMS OTP: Gửi mã OTP qua SMS
    10. Máy chủ API ⇢ Ứng dụng di động: 200 Cần xác minh
    11. Người dùng → Ứng dụng di động: Nhập mã OTP
    12. Ứng dụng di động → Máy chủ API: POST /api/auth/verify-phone {otp}
    13. Máy chủ API → Cơ sở dữ liệu: Đối chiếu mã, cập nhật users.phone_verified_at
  [Hết khung]
  14. Máy chủ API → Cơ sở dữ liệu: Tạo sessions (active_role, push_token)
  15. Máy chủ API ⇢ Ứng dụng di động: 200 Token truy cập và token làm mới
  16. Ứng dụng di động ⇢ Người dùng: Chuyển đến giao diện theo vai trò
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự đăng nhập tài khoản
GẠCH ĐẦU DÒNG: Đăng xuất tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự đăng xuất tài khoản]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Vào mục “Tôi”, chọn “Đăng xuất”
2. Ứng dụng di động → Máy chủ API: POST /api/auth/logout {refreshToken}
3. Máy chủ API → Cơ sở dữ liệu: Cập nhật sessions.revoked_at, xóa push_token
4. Máy chủ API ⇢ Cơ sở dữ liệu: Thành công
5. Máy chủ API ⇢ Ứng dụng di động: 204
6. Ứng dụng di động → Ứng dụng di động: Xóa token đã lưu trên thiết bị
7. Ứng dụng di động ⇢ Người dùng: Chuyển về màn hình chào
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự đăng xuất tài khoản
GẠCH ĐẦU DÒNG: Quên mật khẩu
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự quên mật khẩu]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ SMS OTP / Dịch vụ thư điện tử
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Chọn “Quên mật khẩu”, nhập số điện thoại chính
2. Ứng dụng di động → Máy chủ API: POST /api/auth/forgot-password {phone}
3. Máy chủ API → Cơ sở dữ liệu: Tìm users và recovery_contacts đã xác minh
[Khung alt – điều kiện: Không tìm thấy tài khoản]
  4. Máy chủ API ⇢ Ứng dụng di động: 404
  5. Ứng dụng di động ⇢ Người dùng: Thông báo không tìm thấy tài khoản
[Nhánh khác – điều kiện: Tìm thấy]
  6. Máy chủ API ⇢ Ứng dụng di động: Danh sách phương thức khôi phục (đã che một phần)
  7. Người dùng → Ứng dụng di động: Chọn phương thức khôi phục
  8. Ứng dụng di động → Máy chủ API: POST /api/auth/forgot-password/send {contactId}
  9. Máy chủ API → Cơ sở dữ liệu: Lưu otp_codes (RESET_PASSWORD)
  10. Máy chủ API → Dịch vụ SMS OTP / Dịch vụ thư điện tử: Gửi mã OTP qua SMS hoặc thư điện tử
  11. Người dùng → Ứng dụng di động: Nhập mã OTP và mật khẩu mới
  12. Ứng dụng di động → Máy chủ API: POST /api/auth/reset-password {otp, newPassword}
  13. Máy chủ API → Cơ sở dữ liệu: Đối chiếu otp_codes
  [Khung alt – điều kiện: Mã sai, hết hiệu lực hoặc mật khẩu không hợp lệ]
    14. Máy chủ API ⇢ Ứng dụng di động: 400 Thông báo lỗi
    15. Ứng dụng di động ⇢ Người dùng: Cho nhập lại hoặc gửi mã mới
  [Nhánh khác – điều kiện: Hợp lệ]
    16. Máy chủ API → Cơ sở dữ liệu: Cập nhật users.password_hash, thu hồi các sessions cũ
    17. Máy chủ API ⇢ Ứng dụng di động: 200
    18. Ứng dụng di động ⇢ Người dùng: Chuyển về màn hình đăng nhập
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự quên mật khẩu
GẠCH ĐẦU DÒNG: Đổi mật khẩu
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự đổi mật khẩu]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Nhập mật khẩu hiện tại, mật khẩu mới, xác nhận
2. Ứng dụng di động → Máy chủ API: PUT /api/me/password {currentPassword, newPassword}
3. Máy chủ API → Máy chủ API: Xác thực token
4. Máy chủ API → Cơ sở dữ liệu: Lấy users.password_hash
5. Máy chủ API → Máy chủ API: So khớp mật khẩu hiện tại, kiểm tra mật khẩu mới
[Khung alt – điều kiện: Không hợp lệ]
  6. Máy chủ API ⇢ Ứng dụng di động: 400 Thông báo lỗi
  7. Ứng dụng di động ⇢ Người dùng: Hiển thị lỗi, yêu cầu nhập lại
[Nhánh khác – điều kiện: Hợp lệ]
  8. Máy chủ API → Cơ sở dữ liệu: Cập nhật users.password_hash
  9. Máy chủ API ⇢ Ứng dụng di động: 200
  10. Ứng dụng di động ⇢ Người dùng: Thông báo đổi mật khẩu thành công
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự đổi mật khẩu
GẠCH ĐẦU DÒNG: Cập nhật thông tin tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự cập nhật thông tin tài khoản]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Vào “Thông tin tài khoản”
2. Ứng dụng di động → Máy chủ API: GET /api/me
3. Máy chủ API → Cơ sở dữ liệu: Lấy users và recovery_contacts
4. Máy chủ API ⇢ Ứng dụng di động: Thông tin hiện tại
5. Người dùng → Ứng dụng di động: Sửa họ tên, chọn “Lưu”
6. Ứng dụng di động → Máy chủ API: PUT /api/me {fullName}
7. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu
[Khung alt – điều kiện: Không hợp lệ]
  8. Máy chủ API ⇢ Ứng dụng di động: 400 Thông báo lỗi
  9. Ứng dụng di động ⇢ Người dùng: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  10. Máy chủ API → Cơ sở dữ liệu: Cập nhật users.full_name
  11. Máy chủ API ⇢ Ứng dụng di động: 200
  12. Ứng dụng di động ⇢ Người dùng: Thông báo cập nhật thành công
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự cập nhật thông tin tài khoản
GẠCH ĐẦU DÒNG: Cập nhật thông tin khôi phục tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự cập nhật thông tin khôi phục tài khoản]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Người dùng | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ SMS OTP / Dịch vụ thư điện tử
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Người dùng → Ứng dụng di động: Chọn thêm hoặc thay đổi thông tin khôi phục, nhập mật khẩu hiện tại và thông tin mới
2. Ứng dụng di động → Máy chủ API: POST /api/me/recovery-contacts {password, type, value}
3. Máy chủ API → Máy chủ API: So khớp mật khẩu, kiểm tra định dạng
4. Máy chủ API → Cơ sở dữ liệu: Đếm recovery_contacts theo loại
[Khung alt – điều kiện: Mật khẩu sai, sai định dạng hoặc vượt giới hạn]
  5. Máy chủ API ⇢ Ứng dụng di động: 400 Thông báo lỗi
  6. Ứng dụng di động ⇢ Người dùng: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  7. Máy chủ API → Cơ sở dữ liệu: Lưu recovery_contacts (verified_at rỗng) và otp_codes (VERIFY_RECOVERY)
  8. Máy chủ API → Dịch vụ SMS OTP / Dịch vụ thư điện tử: Gửi mã OTP đến thông tin mới
  9. Người dùng → Ứng dụng di động: Nhập mã OTP
  10. Ứng dụng di động → Máy chủ API: POST /api/me/recovery-contacts/:id/verify {otp}
  [Khung alt – điều kiện: Mã sai hoặc hết hiệu lực]
    11. Máy chủ API ⇢ Ứng dụng di động: 400
    12. Ứng dụng di động ⇢ Người dùng: Cho nhập lại hoặc gửi mã mới
  [Nhánh khác – điều kiện: Mã đúng]
    13. Máy chủ API → Cơ sở dữ liệu: Cập nhật recovery_contacts.verified_at
    14. Máy chủ API ⇢ Ứng dụng di động: 200
    15. Ứng dụng di động ⇢ Người dùng: Thông báo cập nhật thành công
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự cập nhật thông tin khôi phục tài khoản
GẠCH ĐẦU DÒNG: Thiết lập tài khoản ngân hàng nhận tiền
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự thiết lập tài khoản ngân hàng nhận tiền]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Vào “Tài khoản nhận tiền”, nhập mật khẩu hiện tại
2. Chủ trọ → Ứng dụng di động: Chọn ngân hàng, nhập số tài khoản, tên chủ tài khoản
3. Ứng dụng di động → Ứng dụng di động: Hiển thị lại thông tin để đối chiếu
4. Chủ trọ → Ứng dụng di động: Chọn “Xác nhận”
5. Ứng dụng di động → Máy chủ API: PUT /api/house/bank-account {password, bankBin, accountNo, accountName}
6. Máy chủ API → Máy chủ API: So khớp mật khẩu, kiểm tra trường bắt buộc và định dạng
[Khung alt – điều kiện: Không hợp lệ]
  7. Máy chủ API ⇢ Ứng dụng di động: 400 Thông báo lỗi
  8. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi để điều chỉnh
[Nhánh khác – điều kiện: Hợp lệ]
  9. Máy chủ API → Cơ sở dữ liệu: Cập nhật boarding_houses (bank_bin, bank_account_no, bank_account_name)
  10. Máy chủ API → Cơ sở dữ liệu: Ghi audit_logs
  11. Máy chủ API ⇢ Ứng dụng di động: 200
  12. Ứng dụng di động ⇢ Chủ trọ: Thông báo lưu thành công
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự thiết lập tài khoản ngân hàng nhận tiền
GẠCH ĐẦU DÒNG: Kết nối dịch vụ thông báo biến động số dư
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự kết nối dịch vụ thông báo biến động số dư]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo biến động số dư
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Kết nối thông báo biến động số dư”, nhập mật khẩu hiện tại
2. Ứng dụng di động → Máy chủ API: POST /api/house/webhook {password}
3. Máy chủ API → Cơ sở dữ liệu: Lấy boarding_houses
[Khung alt – điều kiện: Chưa có tài khoản nhận tiền hoặc mật khẩu sai]
  4. Máy chủ API ⇢ Ứng dụng di động: 400 Thông báo lỗi
  5. Ứng dụng di động ⇢ Chủ trọ: Yêu cầu thiết lập tài khoản nhận tiền hoặc nhập lại mật khẩu
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Máy chủ API: Sinh webhook_token và khóa xác thực
  7. Máy chủ API → Cơ sở dữ liệu: Lưu webhook_token, webhook_key_hash
  8. Máy chủ API ⇢ Ứng dụng di động: Địa chỉ tiếp nhận và khóa xác thực (hiển thị một lần)
  9. Chủ trọ → Dịch vụ thông báo biến động số dư: Khai báo địa chỉ và khóa tại dịch vụ bên ngoài
  10. Chủ trọ → Ứng dụng di động: Chọn “Hoàn tất”
  11. Ứng dụng di động → Máy chủ API: POST /api/house/webhook/complete
  12. Máy chủ API → Cơ sở dữ liệu: Cập nhật webhook_connected_at
  13. Máy chủ API ⇢ Ứng dụng di động: 200
  14. Ứng dụng di động ⇢ Chủ trọ: Hiển thị trạng thái đã kết nối
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự kết nối dịch vụ thông báo biến động số dư

===== MỤC 3.2.2.2 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý nhà trọ, nhóm phòng và phòng
GẠCH ĐẦU DÒNG: Thiết lập thông tin nhà trọ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự thiết lập thông tin nhà trọ]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Thông tin nhà trọ”
2. Ứng dụng di động → Máy chủ API: GET /api/house
3. Máy chủ API → Cơ sở dữ liệu: Tìm boarding_houses theo owner_id
4. Máy chủ API ⇢ Ứng dụng di động: Thông tin nhà trọ hoặc rỗng
5. Chủ trọ → Ứng dụng di động: Nhập tên, địa chỉ, ngày lập phiếu, số ngày cho phép thanh toán, chọn “Lưu”
6. Ứng dụng di động → Máy chủ API: POST /api/house (khi chưa có) hoặc PUT /api/house
7. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu (ngày lập phiếu 1–28, số ngày nguyên dương)
[Khung alt – điều kiện: Không hợp lệ]
  8. Máy chủ API ⇢ Ứng dụng di động: 400 Thông báo lỗi
  9. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  10. Máy chủ API → Cơ sở dữ liệu: Tạo hoặc cập nhật boarding_houses
  11. Máy chủ API ⇢ Ứng dụng di động: 200
  12. Ứng dụng di động ⇢ Chủ trọ: Thông báo lưu thành công
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự thiết lập thông tin nhà trọ
GẠCH ĐẦU DÒNG: Quản lý nhóm phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự quản lý nhóm phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Vào “Nhóm phòng”
2. Ứng dụng di động → Máy chủ API: GET /api/room-groups
3. Máy chủ API → Cơ sở dữ liệu: Lấy room_groups theo house_id
4. Máy chủ API ⇢ Ứng dụng di động: Danh sách nhóm
[Khung alt – điều kiện: Thêm hoặc đổi tên]
  5. Chủ trọ → Ứng dụng di động: Nhập tên nhóm, chọn “Lưu”
  6. Ứng dụng di động → Máy chủ API: POST /api/room-groups hoặc PUT /api/room-groups/:id {name}
  7. Máy chủ API → Cơ sở dữ liệu: Kiểm tra trùng tên trong nhà trọ
  [Khung alt – điều kiện: Tên trống hoặc trùng]
    8. Máy chủ API ⇢ Ứng dụng di động: 400/409
    9. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
  [Nhánh khác – điều kiện: Hợp lệ]
    10. Máy chủ API → Cơ sở dữ liệu: Lưu room_groups
    11. Máy chủ API ⇢ Ứng dụng di động: 200
    12. Ứng dụng di động ⇢ Chủ trọ: Cập nhật danh sách
  [Hết khung]
[Nhánh khác – điều kiện: Xóa]
  13. Chủ trọ → Ứng dụng di động: Chọn “Xóa” và xác nhận
  14. Ứng dụng di động → Máy chủ API: DELETE /api/room-groups/:id
  15. Máy chủ API → Cơ sở dữ liệu: Đếm rooms theo group_id
  [Khung alt – điều kiện: Nhóm còn phòng]
    16. Máy chủ API ⇢ Ứng dụng di động: 409 Nhóm còn phòng
    17. Ứng dụng di động ⇢ Chủ trọ: Yêu cầu chuyển phòng sang nhóm khác
  [Nhánh khác – điều kiện: Không còn phòng]
    18. Máy chủ API → Cơ sở dữ liệu: Xóa room_groups
    19. Máy chủ API ⇢ Ứng dụng di động: 204
    20. Ứng dụng di động ⇢ Chủ trọ: Cập nhật danh sách
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự quản lý nhóm phòng
GẠCH ĐẦU DÒNG: Thêm phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự thêm phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Thêm phòng”, nhập tên, nhóm, giá thuê, ghi chú, số lượng, chọn “Lưu”
2. Ứng dụng di động → Máy chủ API: POST /api/rooms {name, groupId, monthlyRent, note, quantity}
3. Máy chủ API → Máy chủ API: Tạo danh sách tên phòng (đánh số từ 1 khi số lượng lớn hơn 1)
4. Máy chủ API → Cơ sở dữ liệu: Tìm rooms trùng tên trong nhà trọ
[Khung alt – điều kiện: Dữ liệu không hợp lệ hoặc trùng tên]
  5. Máy chủ API ⇢ Ứng dụng di động: 400 Danh sách lỗi và tên bị trùng
  6. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi, chưa lưu phòng nào
[Nhánh khác – điều kiện: Hợp lệ]
  7. Máy chủ API → Cơ sở dữ liệu: Tạo các rooms (status = VACANT) trong một giao dịch dữ liệu
  8. Máy chủ API ⇢ Ứng dụng di động: 201 Danh sách phòng đã tạo
  9. Ứng dụng di động ⇢ Chủ trọ: Cập nhật danh sách phòng
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự thêm phòng
GẠCH ĐẦU DÒNG: Cập nhật phòng và tạm ngừng sử dụng phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự cập nhật phòng và tạm ngừng sử dụng phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
[Khung alt – điều kiện: Chỉnh sửa]
  1. Chủ trọ → Ứng dụng di động: Sửa tên, nhóm, giá thuê, ghi chú, chọn “Lưu”
  2. Ứng dụng di động → Máy chủ API: PUT /api/rooms/:id
  3. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu
  4. Máy chủ API → Cơ sở dữ liệu: Cập nhật rooms (không sửa contracts.monthly_rent)
  5. Máy chủ API ⇢ Ứng dụng di động: 200 hoặc 400
  6. Ứng dụng di động ⇢ Chủ trọ: Thông báo kết quả
[Nhánh khác – điều kiện: Tạm ngừng sử dụng]
  7. Chủ trọ → Ứng dụng di động: Chọn “Tạm ngừng sử dụng”
  8. Ứng dụng di động → Máy chủ API: POST /api/rooms/:id/suspend
  9. Máy chủ API → Cơ sở dữ liệu: Lấy rooms.status
  [Khung alt – điều kiện: Phòng không ở trạng thái Trống]
    10. Máy chủ API ⇢ Ứng dụng di động: 409 Kèm lý do
    11. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lý do từ chối
  [Nhánh khác – điều kiện: Phòng Trống]
    12. Máy chủ API → Cơ sở dữ liệu: Cập nhật rooms.status = SUSPENDED
    13. Máy chủ API ⇢ Ứng dụng di động: 200
    14. Ứng dụng di động ⇢ Chủ trọ: Cập nhật trạng thái phòng
  [Hết khung]
[Nhánh khác – điều kiện: Mở lại]
  15. Chủ trọ → Ứng dụng di động: Chọn “Mở lại”
  16. Ứng dụng di động → Máy chủ API: POST /api/rooms/:id/reopen
  17. Máy chủ API → Cơ sở dữ liệu: Cập nhật rooms.status = VACANT
  18. Máy chủ API ⇢ Ứng dụng di động: 200
  19. Ứng dụng di động ⇢ Chủ trọ: Cập nhật trạng thái phòng
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự cập nhật phòng và tạm ngừng sử dụng phòng
GẠCH ĐẦU DÒNG: Tra cứu phòng theo trạng thái
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự tra cứu phòng theo trạng thái]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Vào mục “Phòng”, chọn bộ lọc trạng thái, nhóm hoặc nhập tên
2. Ứng dụng di động → Máy chủ API: GET /api/rooms?status=&groupId=&q=
3. Máy chủ API → Cơ sở dữ liệu: Truy vấn rooms theo house_id và điều kiện lọc
4. Máy chủ API ⇢ Cơ sở dữ liệu: Danh sách phòng
5. Máy chủ API ⇢ Ứng dụng di động: 200 Danh sách
[Khung alt – điều kiện: Không có kết quả]
  6. Ứng dụng di động ⇢ Chủ trọ: Hiển thị “Không tìm thấy kết quả”
[Nhánh khác – điều kiện: Có kết quả]
  7. Ứng dụng di động ⇢ Chủ trọ: Hiển thị danh sách theo nhóm
  8. Chủ trọ → Ứng dụng di động: Chọn một phòng
  9. Ứng dụng di động → Máy chủ API: GET /api/rooms/:id
  10. Máy chủ API → Cơ sở dữ liệu: Lấy rooms, reservations chưa xử lý, contracts đang gắn
  11. Máy chủ API ⇢ Ứng dụng di động: Chi tiết phòng
  12. Ứng dụng di động ⇢ Chủ trọ: Hiển thị chi tiết và thao tác phù hợp
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự tra cứu phòng theo trạng thái

===== MỤC 3.2.2.3 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý dịch vụ và đơn giá
GẠCH ĐẦU DÒNG: Khai báo dịch vụ, đơn giá và phương pháp tính
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự khai báo dịch vụ, đơn giá và phương pháp tính]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Thêm dịch vụ”, nhập loại, tên, phương pháp tính, đơn giá, đơn vị, ngày hiệu lực
2. Ứng dụng di động → Máy chủ API: POST /api/services {...}
3. Máy chủ API → Máy chủ API: Kiểm tra phương pháp tính phù hợp loại khoản phí, đơn giá không âm
4. Máy chủ API → Cơ sở dữ liệu: Kiểm tra trùng tên trong nhà trọ
[Khung alt – điều kiện: Không hợp lệ]
  5. Máy chủ API ⇢ Ứng dụng di động: 400/409 Thông báo lỗi
  6. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  7. Máy chủ API → Cơ sở dữ liệu: Tạo services và service_prices đầu tiên trong một giao dịch dữ liệu
  8. Máy chủ API ⇢ Ứng dụng di động: 201
  9. Ứng dụng di động ⇢ Chủ trọ: Cập nhật danh sách dịch vụ
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự khai báo dịch vụ, đơn giá và phương pháp tính
GẠCH ĐẦU DÒNG: Cập nhật mức phí và trạng thái áp dụng dịch vụ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự cập nhật mức phí và trạng thái áp dụng dịch vụ]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
[Khung alt – điều kiện: Cập nhật mức phí]
  1. Chủ trọ → Ứng dụng di động: Nhập đơn giá mới, ngày hiệu lực
  2. Ứng dụng di động → Máy chủ API: POST /api/services/:id/prices {unitPrice, effectiveFrom}
  3. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu
  4. Máy chủ API → Cơ sở dữ liệu: Thêm service_prices mới (không ghi đè bản ghi cũ)
[Nhánh khác – điều kiện: Thay đổi trạng thái áp dụng]
  5. Chủ trọ → Ứng dụng di động: Chọn hợp đồng, áp dụng hoặc ngừng, số suất, ngày hiệu lực
  6. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/services {serviceId, isApplied, quantity, effectiveFrom}
  7. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu
  8. Máy chủ API → Cơ sở dữ liệu: Thêm contract_services mới
[Hết khung]
9. Máy chủ API ⇢ Ứng dụng di động: 201 hoặc 400
10. Ứng dụng di động ⇢ Chủ trọ: Thông báo kết quả
[Khung opt – điều kiện: Xem lịch sử]
  11. Chủ trọ → Ứng dụng di động: Chọn “Lịch sử thay đổi”
  12. Ứng dụng di động → Máy chủ API: GET /api/services/:id/history
  13. Máy chủ API → Cơ sở dữ liệu: Lấy service_prices và contract_services theo thời gian
  14. Máy chủ API ⇢ Ứng dụng di động: Lịch sử
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự cập nhật mức phí và trạng thái áp dụng dịch vụ

===== MỤC 3.2.2.4 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case giữ phòng và quản lý tiền cọc
GẠCH ĐẦU DÒNG: Lập phiếu giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự lập phiếu giữ phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn phòng, chọn “Giữ phòng”, nhập thông tin người giữ, ngày nhận dự kiến, thời hạn, tiền cọc, thỏa thuận
2. Ứng dụng di động → Máy chủ API: POST /api/reservations {...}
3. Máy chủ API → Cơ sở dữ liệu: Lấy rooms (giá thuê làm agreed_rent), contracts chưa thanh lý, reservations chưa xử lý của phòng
4. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu bắt buộc, 0 < tiền cọc ≤ agreed_rent, thời hạn giữ không sớm hơn ngày lập
5. Máy chủ API → Máy chủ API: Kiểm tra xung đột theo ngày nhận dự kiến (kể cả phiếu đã quá hạn chưa xử lý)
[Khung alt – điều kiện: Không hợp lệ hoặc có xung đột]
  6. Máy chủ API ⇢ Ứng dụng di động: 400/409 Kèm nguyên nhân
  7. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  8. Máy chủ API → Cơ sở dữ liệu: Tạo reservations (status = ACTIVE, agreed_rent); cập nhật rooms.status = RESERVED nếu phòng Trống
  9. Máy chủ API ⇢ Ứng dụng di động: 201 Phiếu giữ phòng
  10. Ứng dụng di động ⇢ Chủ trọ: Hiển thị phiếu, cho phép chia sẻ
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự lập phiếu giữ phòng
GẠCH ĐẦU DÒNG: Xác nhận tiền cọc giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự xác nhận tiền cọc giữ phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
[Khung opt – điều kiện: Người giữ phòng chuyển khoản]
  1. Chủ trọ → Ứng dụng di động: Chọn “Hiển thị VietQR”
  2. Ứng dụng di động → Máy chủ API: GET /api/reservations/:id/deposit-qr
  3. Máy chủ API → Cơ sở dữ liệu: Lấy boarding_houses (tài khoản nhận) và reservations
  [Khung alt – điều kiện: Chưa có tài khoản nhận tiền]
    4. Máy chủ API ⇢ Ứng dụng di động: 409
    5. Ứng dụng di động ⇢ Chủ trọ: Yêu cầu thiết lập tài khoản nhận tiền
  [Nhánh khác – điều kiện: Đã có]
    6. Máy chủ API ⇢ Ứng dụng di động: Dữ liệu VietQR (tài khoản, số tiền, nội dung)
    7. Ứng dụng di động ⇢ Chủ trọ: Hiển thị mã VietQR
  [Hết khung]
[Hết khung]
8. Chủ trọ → Chủ trọ: Kiểm tra số tiền thực nhận
[Khung alt – điều kiện: Chưa nhận được tiền]
  9. Ứng dụng di động ⇢ Chủ trọ: Phiếu giữ nguyên tình trạng chưa nhận cọc
[Nhánh khác – điều kiện: Đã nhận]
  10. Chủ trọ → Ứng dụng di động: Chọn “Xác nhận đã nhận cọc”, nhập số tiền, hình thức
  11. Ứng dụng di động → Máy chủ API: POST /api/reservations/:id/confirm-deposit {amount, method}
  12. Máy chủ API → Cơ sở dữ liệu: Cập nhật reservations (deposit_received, deposit_method, deposit_confirmed_at)
  13. Máy chủ API ⇢ Ứng dụng di động: 200
  14. Ứng dụng di động ⇢ Chủ trọ: Hiển thị tiền cọc đang giữ
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự xác nhận tiền cọc giữ phòng
GẠCH ĐẦU DÒNG: Gia hạn phiếu giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự gia hạn phiếu giữ phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở phiếu, chọn “Gia hạn”, nhập thời hạn mới và ngày nhận dự kiến mới
2. Ứng dụng di động → Máy chủ API: POST /api/reservations/:id/extend {holdUntil, expectedMoveIn}
3. Máy chủ API → Cơ sở dữ liệu: Lấy reservations, contracts và reservations khác của phòng
4. Máy chủ API → Máy chủ API: Kiểm tra thời hạn mới và xung đột
[Khung alt – điều kiện: Không hợp lệ]
  5. Máy chủ API ⇢ Ứng dụng di động: 400/409
  6. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  7. Máy chủ API → Cơ sở dữ liệu: Cập nhật reservations (hold_until, status = ACTIVE); ghi audit_logs (trước, sau)
  8. Máy chủ API ⇢ Ứng dụng di động: 200
  9. Ứng dụng di động ⇢ Chủ trọ: Hiển thị phiếu đã gia hạn
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự gia hạn phiếu giữ phòng
GẠCH ĐẦU DÒNG: Hủy phiếu giữ phòng và xử lý tiền cọc
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự hủy phiếu giữ phòng và xử lý tiền cọc]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở phiếu, chọn “Hủy phiếu”
2. Chủ trọ → Ứng dụng di động: Chọn phương án, nhập số tiền hoàn, lý do, xác nhận
3. Ứng dụng di động → Máy chủ API: POST /api/reservations/:id/cancel {refundAmount, reason}
4. Máy chủ API → Máy chủ API: Kiểm tra 0 ≤ số tiền hoàn ≤ tiền cọc thực nhận, lý do không trống
[Khung alt – điều kiện: Không hợp lệ]
  5. Máy chủ API ⇢ Ứng dụng di động: 400
  6. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  7. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  8. Máy chủ API → Cơ sở dữ liệu: Cập nhật reservations (CANCELLED, refund_amount, cancel_reason)
  9. Máy chủ API → Cơ sở dữ liệu: Tạo finance_entries (INCOME, RESERVATION) cho phần cọc giữ lại nếu lớn hơn 0
  10. Máy chủ API → Cơ sở dữ liệu: Cập nhật rooms.status = VACANT nếu không còn phiếu hoặc hợp đồng khác
  11. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
  12. Máy chủ API ⇢ Ứng dụng di động: 200
  13. Ứng dụng di động ⇢ Chủ trọ: Hiển thị phiếu đã hủy
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự hủy phiếu giữ phòng và xử lý tiền cọc

===== MỤC 3.2.2.5 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý hợp đồng và thành viên
GẠCH ĐẦU DÒNG: Lập hợp đồng từ phiếu giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự lập hợp đồng từ phiếu giữ phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở phiếu giữ phòng, chọn “Lập hợp đồng”
2. Chủ trọ → Ứng dụng di động: Nhập thời hạn, giá thuê, dịch vụ, tiền cọc, thành viên, người đứng tên, chế độ thanh toán, chứng từ
3. Ứng dụng di động → Máy chủ API: POST /api/reservations/:id/contract {...}
4. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu, đúng một người đứng tên
5. Máy chủ API → Cơ sở dữ liệu: Lấy contracts và reservations khác của phòng
[Khung alt – điều kiện: Không hợp lệ hoặc xung đột]
  6. Máy chủ API ⇢ Ứng dụng di động: 400/409
  7. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  8. Máy chủ API → Máy chủ API: Tính tiền thuê kỳ đầu; reservation_offset = min(cọc thực nhận, tiền thuê kỳ đầu); offset_refund_due = phần cọc vượt
  9. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  10. Máy chủ API → Cơ sở dữ liệu: Tạo contracts (reservation_offset, offset_refund_due), contract_members, contract_services
  11. Máy chủ API → Cơ sở dữ liệu: Cập nhật reservations.status = CONVERTED, rooms.status = OCCUPIED
  12. Máy chủ API → Máy chủ API: Tạo hoặc liên kết tài khoản Khách thuê cho thành viên (extend Tạo và liên kết tài khoản Khách thuê)
  13. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
  14. Máy chủ API ⇢ Ứng dụng di động: 201 Hợp đồng, khoản cọc cần hoàn (nếu có) và thông tin đăng nhập của tài khoản mới
  15. Ứng dụng di động ⇢ Chủ trọ: Hiển thị hợp đồng, cho phép chia sẻ thông tin đăng nhập
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự lập hợp đồng từ phiếu giữ phòng
GẠCH ĐẦU DÒNG: Nhập hợp đồng đang còn hiệu lực
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự nhập hợp đồng đang còn hiệu lực]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn phòng Trống, chọn “Nhập hợp đồng đang thuê”
2. Chủ trọ → Ứng dụng di động: Nhập thông tin hợp đồng, tiền cọc đang giữ, công nợ đầu kỳ, chỉ số ban đầu
3. Ứng dụng di động → Máy chủ API: POST /api/contracts/import {...}
4. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu, số không âm, đúng một người đứng tên
5. Máy chủ API → Cơ sở dữ liệu: Kiểm tra xung đột với contracts và reservations của phòng
[Khung alt – điều kiện: Không hợp lệ]
  6. Máy chủ API ⇢ Ứng dụng di động: 400/409
  7. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  8. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  9. Máy chủ API → Cơ sở dữ liệu: Tạo contracts (source = IMPORTED, opening_debt, deposit_held là số dư ban đầu, không tạo payments), contract_members, contract_services
  10. Máy chủ API → Cơ sở dữ liệu: Tạo meter_readings ban đầu, cập nhật rooms.status = OCCUPIED
  11. Máy chủ API → Máy chủ API: Tạo hoặc liên kết tài khoản Khách thuê
  12. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
  13. Máy chủ API ⇢ Ứng dụng di động: 201
  14. Ứng dụng di động ⇢ Chủ trọ: Hiển thị hợp đồng
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự nhập hợp đồng đang còn hiệu lực
GẠCH ĐẦU DÒNG: Tạo và liên kết tài khoản Khách thuê
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự tạo và liên kết tài khoản Khách thuê]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Máy chủ API → Máy chủ API: Xét lần lượt từng thành viên của hợp đồng
[Khung alt – điều kiện: Không có số điện thoại]
  2. Máy chủ API → Cơ sở dữ liệu: Lưu contract_members (user_id rỗng)
[Nhánh khác – điều kiện: Có số điện thoại]
  3. Máy chủ API → Cơ sở dữ liệu: Tìm users theo phone
  [Khung alt – điều kiện: Chưa có tài khoản]
    4. Máy chủ API → Máy chủ API: Sinh mật khẩu ban đầu
    5. Máy chủ API → Cơ sở dữ liệu: Tạo users (is_tenant = true, phone_verified_at rỗng), gán contract_members.user_id
    6. Máy chủ API → Máy chủ API: Ghi thông tin đăng nhập vào phản hồi
  [Nhánh khác – điều kiện: Đã có tài khoản]
    7. Máy chủ API → Cơ sở dữ liệu: Cập nhật users.is_tenant = true nếu chưa có, gán contract_members.user_id
  [Hết khung]
[Hết khung]
8. Máy chủ API ⇢ Ứng dụng di động: Danh sách tài khoản mới và tài khoản đã liên kết
9. Ứng dụng di động ⇢ Chủ trọ: Hiển thị, chia sẻ thông tin đăng nhập qua chức năng chia sẻ của thiết bị
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự tạo và liên kết tài khoản Khách thuê

===== MỤC 3.2.2.6 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case bàn giao phòng
GẠCH ĐẦU DÒNG: Bàn giao phòng khi nhận phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự bàn giao phòng khi nhận phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn “Lập biên bản bàn giao”, nhập hiện trạng, tài sản, chìa khóa, chỉ số, hình ảnh
2. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/handovers {type: MOVE_IN, ...}
3. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu, chỉ số bắt buộc với khoản theo công tơ và không âm
[Khung alt – điều kiện: Không hợp lệ]
  4. Máy chủ API ⇢ Ứng dụng di động: 400
  5. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Cơ sở dữ liệu: Lưu handovers (status = PENDING_CONFIRM), attachments
  7. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Khách thuê
  8. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
  9. Máy chủ API ⇢ Ứng dụng di động: 201
  10. Khách thuê → Ứng dụng di động: Mở biên bản
  [Khung alt – điều kiện: Đồng ý]
    11. Khách thuê → Ứng dụng di động: Chọn “Xác nhận”
    12. Ứng dụng di động → Máy chủ API: POST /api/handovers/:id/confirm
    13. Máy chủ API → Cơ sở dữ liệu: Cập nhật handovers (CONFIRMED, confirmed_by, confirmed_at); chỉ số biên bản là chỉ số ban đầu
    14. Máy chủ API ⇢ Ứng dụng di động: 200
  [Nhánh khác – điều kiện: Chưa đồng ý]
    15. Khách thuê → Ứng dụng di động: Nhập phản hồi
    16. Ứng dụng di động → Máy chủ API: POST /api/handovers/:id/feedback {content}
    17. Máy chủ API → Cơ sở dữ liệu: Cập nhật handovers (DISPUTED, tenant_feedback); tạo notifications cho Chủ trọ
    18. Máy chủ API ⇢ Ứng dụng di động: 200
  [Hết khung]
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự bàn giao phòng khi nhận phòng
GẠCH ĐẦU DÒNG: Bàn giao khi trả phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự bàn giao khi trả phòng]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Khách thuê | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở hợp đồng chờ thanh lý, chọn “Lập biên bản trả phòng”
2. Ứng dụng di động → Máy chủ API: GET /api/contracts/:id/handovers
3. Máy chủ API → Cơ sở dữ liệu: Lấy biên bản nhận phòng
4. Máy chủ API ⇢ Ứng dụng di động: Biên bản nhận phòng để đối chiếu
5. Chủ trọ → Ứng dụng di động: Nhập hiện trạng, tài sản, chìa khóa, hư hỏng, chỉ số cuối, hình ảnh
6. Ứng dụng di động → Máy chủ API: POST /api/contracts/:id/handovers {type: MOVE_OUT, ...}
7. Máy chủ API → Cơ sở dữ liệu: Lấy meter_readings đã chốt gần nhất
[Khung alt – điều kiện: Chỉ số cuối nhỏ hơn chỉ số đã chốt]
  8. Máy chủ API ⇢ Ứng dụng di động: 400
  9. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  10. Máy chủ API → Cơ sở dữ liệu: Lưu handovers (PENDING_CONFIRM), attachments; tạo notifications cho Khách thuê
  11. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
  12. Máy chủ API ⇢ Ứng dụng di động: 201
  [Khung alt – điều kiện: Khách thuê đồng ý]
    13. Khách thuê → Ứng dụng di động: Chọn “Xác nhận”
    14. Ứng dụng di động → Máy chủ API: POST /api/handovers/:id/confirm
    15. Máy chủ API → Cơ sở dữ liệu: Cập nhật handovers = CONFIRMED; tạo meter_readings chốt cuối kỳ
  [Nhánh khác – điều kiện: Khách thuê phản hồi]
    16. Khách thuê → Ứng dụng di động: Nhập phản hồi
    17. Ứng dụng di động → Máy chủ API: POST /api/handovers/:id/feedback
    18. Máy chủ API → Cơ sở dữ liệu: Cập nhật handovers = DISPUTED; Chủ trọ chỉnh sửa và gửi lại
  [Nhánh khác – điều kiện: Khách thuê không phản hồi]
    19. Chủ trọ → Ứng dụng di động: Chọn “Hoàn tất ghi nhận – Khách chưa xác nhận”, nhập ghi chú, bằng chứng
    20. Ứng dụng di động → Máy chủ API: POST /api/handovers/:id/complete-unconfirmed {note}
    21. Máy chủ API → Cơ sở dữ liệu: Cập nhật handovers (COMPLETED_UNCONFIRMED, completion_note, completed_by, completed_at); tạo meter_readings chốt cuối kỳ
  [Hết khung]
  22. Máy chủ API ⇢ Ứng dụng di động: 200
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự bàn giao khi trả phòng

===== MỤC 3.2.2.7 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý chỉ số điện nước
GẠCH ĐẦU DÒNG: Ghi nhận và chốt chỉ số điện nước
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự ghi nhận và chốt chỉ số điện nước]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn kỳ và phòng
2. Ứng dụng di động → Máy chủ API: GET /api/rooms/:id/meter-readings/latest
3. Máy chủ API → Cơ sở dữ liệu: Lấy meters đang dùng và meter_readings gần nhất
4. Máy chủ API ⇢ Ứng dụng di động: Chỉ số lần trước
5. Chủ trọ → Ứng dụng di động: Nhập chỉ số mới, đính kèm ảnh, chọn “Chốt chỉ số”
6. Ứng dụng di động → Máy chủ API: POST /api/meter-readings {meterId, period, reading, confirmAbnormal}
7. Máy chủ API → Máy chủ API: So sánh với chỉ số cũ và mức tiêu thụ các kỳ trước
[Khung alt – điều kiện: Chỉ số mới nhỏ hơn chỉ số cũ]
  8. Máy chủ API ⇢ Ứng dụng di động: 400 Yêu cầu kiểm tra lại
  9. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Tiêu thụ bất thường và chưa xác nhận]
  10. Máy chủ API ⇢ Ứng dụng di động: 409 Cảnh báo bất thường
  11. Ứng dụng di động ⇢ Chủ trọ: Hiển thị cảnh báo, cho nhập lại hoặc xác nhận tiếp tục
[Nhánh khác – điều kiện: Hợp lệ]
  12. Máy chủ API → Cơ sở dữ liệu: Lưu meter_readings (locked_by, locked_at, is_abnormal), attachments
  13. Máy chủ API ⇢ Ứng dụng di động: 201
  14. Ứng dụng di động ⇢ Chủ trọ: Hiển thị chỉ số đã chốt
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự ghi nhận và chốt chỉ số điện nước
GẠCH ĐẦU DÒNG: Ghi nhận thay công tơ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự ghi nhận thay công tơ]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Chọn phòng, chọn “Thay công tơ”, nhập loại, ngày thay, chỉ số cuối cũ, chỉ số đầu mới, hình ảnh
2. Ứng dụng di động → Máy chủ API: POST /api/meters/:id/replace {removedOn, finalReading, newStartReading}
3. Máy chủ API → Cơ sở dữ liệu: Lấy meter_readings đã chốt gần nhất của công tơ cũ
[Khung alt – điều kiện: Không hợp lệ]
  4. Máy chủ API ⇢ Ứng dụng di động: 400
  5. Ứng dụng di động ⇢ Chủ trọ: Hiển thị lỗi
[Nhánh khác – điều kiện: Hợp lệ]
  6. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  7. Máy chủ API → Cơ sở dữ liệu: Cập nhật meters cũ (final_reading, removed_on); tạo meters mới; lưu attachments
  8. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
  9. Máy chủ API ⇢ Ứng dụng di động: 201
  10. Ứng dụng di động ⇢ Chủ trọ: Thông báo ghi nhận thành công
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự ghi nhận thay công tơ
GẠCH ĐẦU DÒNG: Phản hồi và điều chỉnh chỉ số đã chốt
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự phản hồi và điều chỉnh chỉ số đã chốt]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Khách thuê | Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Khách thuê → Ứng dụng di động: Chọn “Gửi phản hồi” trên chỉ số, nhập nội dung
2. Ứng dụng di động → Máy chủ API: POST /api/meter-readings/:id/feedbacks {content}
3. Máy chủ API → Cơ sở dữ liệu: Lưu reading_feedbacks (OPEN); tạo notifications cho Chủ trọ
4. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Chủ trọ
5. Máy chủ API ⇢ Ứng dụng di động: 201
[Khung alt – điều kiện: Chỉ số đúng]
  6. Chủ trọ → Ứng dụng di động: Nhập trả lời, đóng phản hồi
  7. Ứng dụng di động → Máy chủ API: PUT /api/reading-feedbacks/:id {reply, status: CLOSED}
  8. Máy chủ API → Cơ sở dữ liệu: Cập nhật reading_feedbacks
[Nhánh khác – điều kiện: Chỉ số sai]
  9. Chủ trọ → Ứng dụng di động: Chọn “Điều chỉnh chỉ số”, nhập giá trị đúng và lý do
  10. Ứng dụng di động → Máy chủ API: PUT /api/meter-readings/:id {reading, reason}
  11. Máy chủ API → Máy chủ API: Kiểm tra giá trị hợp lệ, lý do không trống
  12. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
  13. Máy chủ API → Cơ sở dữ liệu: Cập nhật meter_readings.reading; ghi audit_logs (trước, sau, lý do); đóng reading_feedbacks
  14. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
  15. Máy chủ API → Máy chủ API: Phiếu đã phát hành dùng chỉ số này không tự thay đổi; Chủ trọ xử lý theo extend Điều chỉnh phiếu báo phí đã phát hành
[Hết khung]
16. Máy chủ API → Cơ sở dữ liệu: Tạo notifications kết quả cho Khách thuê
17. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
18. Máy chủ API ⇢ Ứng dụng di động: 200
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự phản hồi và điều chỉnh chỉ số đã chốt

===== MỤC 3.2.2.8 =====
TIÊU ĐỀ: Sơ đồ tuần tự của use case quản lý phiếu báo phí
GẠCH ĐẦU DÒNG: Lập phiếu báo phí nháp
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự lập phiếu báo phí nháp]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Máy chủ API → Máy chủ API: Tác vụ định kỳ đến ngày lập phiếu, hoặc Chủ trọ gọi POST /api/invoices/generate {contractId}
2. Máy chủ API → Cơ sở dữ liệu: Lấy contracts còn hiệu lực, contract_services, service_prices, meter_readings, extra_charges và invoice_adjustments (NEXT_PERIOD, PENDING) chưa đưa vào phiếu
3. Máy chủ API → Máy chủ API: Tính tiền phòng (tháng đủ 100%; kỳ lẻ = số ngày × giá thuê / 30, làm tròn một lần đến 1.000 đồng)
[Khung opt – điều kiện: Tháng đầu của hợp đồng lập từ phiếu giữ phòng]
  4. Máy chủ API → Máy chủ API: Thêm khoản cấn trừ bằng contracts.reservation_offset (không vượt tiền thuê kỳ đầu, không tạo tiền thuê âm)
[Hết khung]
[Khung alt – điều kiện: Đã có chỉ số chốt của kỳ]
  5. Máy chủ API → Máy chủ API: Tính điện nước theo công tơ = (chỉ số mới − chỉ số cũ) × đơn giá
[Nhánh khác – điều kiện: Chưa có]
  6. Máy chủ API → Máy chủ API: Bỏ khoản theo công tơ, đánh dấu missing_reading
[Hết khung]
7. Máy chủ API → Máy chủ API: Tính dịch vụ khác, cộng khoản phát sinh và khoản điều chỉnh chuyển sang kỳ này
8. Máy chủ API → Máy chủ API: Phân bổ nghĩa vụ thanh toán (extend Phân bổ nghĩa vụ thanh toán)
9. Máy chủ API → Cơ sở dữ liệu: Lưu invoices (DRAFT), invoice_lines, invoice_obligations; cập nhật invoice_adjustments = APPLIED trong một giao dịch dữ liệu
10. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho Chủ trọ
11. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị Chủ trọ
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự lập phiếu báo phí nháp
GẠCH ĐẦU DÒNG: Phân bổ nghĩa vụ thanh toán
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự phân bổ nghĩa vụ thanh toán]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Máy chủ API → Cơ sở dữ liệu: Lấy contracts.payment_mode và contract_members còn hiệu lực
[Khung alt – điều kiện: Chế độ đại diện]
  2. Máy chủ API → Máy chủ API: Tạo một phần phải trả bằng tổng phiếu cho người đại diện
[Nhánh khác – điều kiện: Chế độ chia đều]
  3. Máy chủ API → Máy chủ API: Phần nguyên = tổng phiếu chia số thành viên chịu trách nhiệm, theo đơn vị đồng
  4. Máy chủ API → Máy chủ API: Cộng phần dư, mỗi người một đồng theo thứ tự sort_order
[Hết khung]
5. Máy chủ API → Máy chủ API: Bù trừ credit_balance của từng thành viên vào phần của chính thành viên đó
6. Máy chủ API → Máy chủ API: Sinh payment_code riêng cho từng phần
7. Máy chủ API → Cơ sở dữ liệu: Lưu invoice_obligations; cập nhật contract_members.credit_balance
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự phân bổ nghĩa vụ thanh toán
GẠCH ĐẦU DÒNG: Kiểm tra và phát hành phiếu báo phí
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự kiểm tra và phát hành phiếu báo phí]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở phiếu nháp
2. Ứng dụng di động → Máy chủ API: GET /api/invoices/:id
3. Máy chủ API → Cơ sở dữ liệu: Lấy invoices, invoice_lines, invoice_obligations
4. Máy chủ API ⇢ Ứng dụng di động: Chi tiết phiếu
[Khung opt – điều kiện: Điều chỉnh khoản dịch vụ]
  5. Chủ trọ → Ứng dụng di động: Nhập số tiền khác hoặc 0 đồng, lý do (tùy chọn)
  6. Ứng dụng di động → Máy chủ API: PUT /api/invoices/:id/lines/:lineId {amount, reason}
  7. Máy chủ API → Cơ sở dữ liệu: Cập nhật invoice_lines.amount (giữ default_amount); tính lại tổng và phân bổ lại
  8. Máy chủ API ⇢ Ứng dụng di động: Phiếu đã tính lại
[Hết khung]
9. Chủ trọ → Ứng dụng di động: Chọn “Phát hành”
10. Ứng dụng di động → Máy chủ API: POST /api/invoices/:id/issue
11. Máy chủ API → Máy chủ API: Kiểm tra khoản theo công tơ đã có chỉ số chốt
[Khung alt – điều kiện: Thiếu chỉ số]
  12. Máy chủ API ⇢ Ứng dụng di động: 409 Kèm khoản còn thiếu
  13. Ứng dụng di động ⇢ Chủ trọ: Hiển thị khoản thiếu, phiếu giữ trạng thái nháp
[Nhánh khác – điều kiện: Đủ]
  14. Máy chủ API → Cơ sở dữ liệu: Cập nhật invoices (ISSUED, issued_at, due_date = ngày phát hành + payment_due_days)
  15. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho người có nghĩa vụ
  16. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
  17. Máy chủ API ⇢ Ứng dụng di động: 200
  18. Ứng dụng di động ⇢ Chủ trọ: Hiển thị phiếu đã phát hành
[Hết khung]
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự kiểm tra và phát hành phiếu báo phí
GẠCH ĐẦU DÒNG: Điều chỉnh phiếu báo phí đã phát hành
[[MÔ TẢ SƠ ĐỒ: Sơ đồ tuần tự điều chỉnh phiếu báo phí đã phát hành]]
Loại: Sơ đồ tuần tự UML; mỗi đối tượng có đường sống dọc và thanh kích hoạt; tác nhân người vẽ hình người que.
Đối tượng (từ trái sang phải): Chủ trọ | Ứng dụng di động | Máy chủ API | Cơ sở dữ liệu | Dịch vụ thông báo đẩy
Quy ước: “→” là thông điệp gọi (nét liền, đầu mũi tên đặc); “⇢” là thông điệp trả về (nét đứt); thông điệp từ một đối tượng đến chính nó vẽ dạng vòng tự gọi. Các dòng [Khung ...] mở khung kết hợp alt hoặc opt, [Nhánh khác ...] là đường phân cách nhánh trong khung alt, [Hết khung] đóng khung gần nhất. Ghi số thứ tự trước mỗi thông điệp.
Thông điệp:
1. Chủ trọ → Ứng dụng di động: Mở phiếu đã phát hành
2. Ứng dụng di động → Máy chủ API: GET /api/invoices/:id
3. Máy chủ API → Cơ sở dữ liệu: Lấy invoices và payments đã xác nhận của phiếu
4. Máy chủ API ⇢ Ứng dụng di động: Chi tiết phiếu và thao tác được phép
[Khung alt – điều kiện: Chưa có thanh toán được xác nhận]
  5. Chủ trọ → Ứng dụng di động: Chọn “Chỉnh sửa”, cập nhật khoản cần điều chỉnh, nhập lý do
  6. Ứng dụng di động → Máy chủ API: PUT /api/invoices/:id {lines, reason}
  7. Máy chủ API → Máy chủ API: Kiểm tra dữ liệu, tính lại tổng và phần phải trả theo chế độ của phiếu
  [Khung alt – điều kiện: Không hợp lệ hoặc đã có thanh toán vừa được xác nhận]
    8. Máy chủ API ⇢ Ứng dụng di động: 400/409
  [Nhánh khác – điều kiện: Hợp lệ]
    9. Máy chủ API → Cơ sở dữ liệu: Bắt đầu giao dịch dữ liệu
    10. Máy chủ API → Cơ sở dữ liệu: Cập nhật invoice_lines, total_amount, invoice_obligations (giữ mã phiếu, due_date); invoices.is_adjusted = true; ghi audit_logs (trước, sau, lý do)
    11. Máy chủ API → Cơ sở dữ liệu: Cập nhật payment_requests PENDING của phiếu = CANCELLED
    12. Máy chủ API → Cơ sở dữ liệu: Kết thúc giao dịch dữ liệu
    13. Máy chủ API ⇢ Ứng dụng di động: 200
  [Hết khung]
[Nhánh khác – điều kiện: Đã có thanh toán được xác nhận]
  14. Chủ trọ → Ứng dụng di động: Chọn “Ghi nhận điều chỉnh”, chọn tăng hoặc giảm, nhập số tiền, lý do, cách xử lý
  15. Ứng dụng di động → Máy chủ API: POST /api/invoices/:id/adjustments {direction, amount, reason, handling}
  16. Máy chủ API → Máy chủ API: Kiểm tra số tiền lớn hơn 0, lý do không trống, cách xử lý phù hợp loại điều chỉnh
  17. Máy chủ API → Cơ sở dữ liệu: Tạo invoice_adjustments (PENDING) liên kết phiếu gốc; không sửa invoices, invoice_lines, payments của phiếu gốc
  18. Máy chủ API ⇢ Ứng dụng di động: 201
[Hết khung]
19. Máy chủ API → Cơ sở dữ liệu: Tạo notifications cho người có nghĩa vụ thanh toán
20. Máy chủ API → Dịch vụ thông báo đẩy: Gửi thông báo đến thiết bị
21. Ứng dụng di động ⇢ Chủ trọ: Hiển thị kết quả
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ tuần tự điều chỉnh phiếu báo phí đã phát hành

KIỂM TRA SAU KHI LÀM (báo lại kết quả từng dòng):
1. Không còn nội dung "quản lý hồ sơ và điểm uy tín" trong mục 3.2.2.
2. Mục 3.2.2 có một đoạn văn và các mục con 3.2.2.1 đến 3.2.2.8, mỗi chức năng có một gạch đầu dòng, một khối mô tả và một chú thích hình.
