PROMPT 09 – MỤC 3.2.1 USE CASE CHI TIẾT (dán toàn bộ nội dung dưới đây cho AI Word; chỉ dùng sau khi đã chạy xong Prompt 08b)

VAI TRÒ: Bạn là người triển khai nội dung vào tài liệu LVTN.docx. Toàn bộ nội dung dưới đây đã được phân tích và chốt. Bạn chèn đúng nguyên văn từng chữ. Không tự viết thêm, không diễn đạt lại, không rút gọn, không suy luận, không sửa phần khác của tài liệu.

PHẠM VI: Chỉ làm việc trong mục "3.2.1 Use case chi tiết" (từ tiêu đề 3.2.1 đến trước tiêu đề "3.2.2 Sơ đồ tuần tự").

VIỆC 1 – XÓA phần còn sót của đề tài khác: tiêu đề "3.2.1.1 Quản lý hồ sơ và điểm uy tín", chú thích "Usecase quản lý hồ sơ và điểm uy tín" (kể cả hình nếu có) và toàn bộ bảng đặc tả ngay dưới (bảng có dòng "Thiết lập vị trí GPS phục vụ tìm kiếm thực phẩm..."). Giữ tiêu đề "3.2.1 Use case chi tiết".

VIỆC 2 – CHÈN ngay dưới tiêu đề "3.2.1 Use case chi tiết" một đoạn văn và 17 mục con theo đúng thứ tự dưới đây.

ĐỊNH DẠNG:
- Tiêu đề mục con: dùng đúng kiểu (style) và cách đánh số tự động của tiêu đề cấp 4 đang dùng ở mục 2.3.1 (ví dụ "2.3.1.5 Quy trình đổi mật khẩu"); số mục sẽ là 3.2.1.1 đến 3.2.1.17.
- Khối mô tả sơ đồ: chèn nguyên văn từ dòng "[[MÔ TẢ SƠ ĐỒ: ...]]" đến dòng "[[HẾT MÔ TẢ]]", mỗi dòng là một đoạn riêng, phông Consolas cỡ 10, căn trái, không thụt đầu dòng. Đây là chỗ giữ chỗ cho hình.
- Chú thích hình: đặt ngay dưới khối mô tả sơ đồ, tạo bằng cơ chế chú thích có trường đánh số tự động, đúng kiểu chú thích hình đang có trong tài liệu. Không gõ tay số hình.
- Bảng đặc tả: bảng 2 cột, viền đơn, cùng phông chữ với đoạn văn. Mỗi dòng "[Nhãn] Nội dung" dưới đây là một hàng của bảng: ô trái ghi Nhãn, ô phải ghi Nội dung. Hàng đầu tiên ("Tên use case") in đậm cả hai ô. Ký hiệu " ¶ " nghĩa là xuống dòng trong cùng một ô (không ghi ký hiệu ¶ vào tài liệu). Một use case có thể có nhiều hàng "Extend use case"; với mỗi hàng này, dòng đầu tiên trong ô phải là tên extend use case và in đậm.
- Thứ tự trong mỗi mục con: Tiêu đề → Khối mô tả sơ đồ → Chú thích hình → Bảng đặc tả.

ĐOẠN VĂN (đặt ngay dưới tiêu đề 3.2.1):
Mục này đặc tả chi tiết 17 use case đã xác định ở sơ đồ use case tổng quát (mục 2.3.4). Mỗi use case gồm các chức năng mở rộng (extend use case); mỗi chức năng mở rộng tương ứng với một quy trình đã phân tích ở mục 2.3.1 và là căn cứ cho sơ đồ tuần tự ở mục 3.2.2, sơ đồ hoạt động ở mục 3.2.3.

===== MỤC 3.2.1.1 =====
TIÊU ĐỀ: Quản lý tài khoản và xác thực
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý tài khoản và xác thực]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Khách thuê
Use case chính (hình elip ở giữa khung): Quản lý tài khoản và xác thực
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Đăng ký tài khoản Chủ trọ; Đăng nhập tài khoản; Đăng xuất tài khoản; Quên mật khẩu; Đổi mật khẩu; Cập nhật thông tin tài khoản; Cập nhật thông tin khôi phục tài khoản; Thiết lập tài khoản ngân hàng nhận tiền; Kết nối dịch vụ thông báo biến động số dư
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý tài khoản và xác thực
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý tài khoản và xác thực
[Tác nhân] Chủ trọ, Khách thuê
[Mô tả] Người dùng đăng ký (Chủ trọ), đăng nhập, đăng xuất, khôi phục và đổi mật khẩu, cập nhật thông tin tài khoản và thông tin khôi phục. Chủ trọ còn thiết lập tài khoản ngân hàng nhận tiền và kết nối dịch vụ thông báo biến động số dư.
[Điều kiện tiên quyết] Thiết bị có kết nối mạng. Với các chức năng sau đăng nhập, người dùng đã đăng nhập thành công.
[Điều kiện hậu quyết] Thành công: Tài khoản, phiên đăng nhập hoặc thông tin được cập nhật vào cơ sở dữ liệu. ¶ Thất bại: Dữ liệu hoặc mã OTP không hợp lệ, hệ thống hiển thị thông báo lỗi và giữ nguyên dữ liệu.
[Luồng sự kiện chính] 1. Người dùng mở ứng dụng, chọn vai trò Chủ trọ hoặc Khách thuê trên màn hình chào. ¶ 2. Người dùng chọn đăng ký, đăng nhập hoặc quên mật khẩu; sau khi đăng nhập, người dùng vào mục “Tôi”. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Đăng ký tài khoản Chủ trọ ¶ Extend use case: Đăng nhập tài khoản ¶ Extend use case: Đăng xuất tài khoản ¶ Extend use case: Quên mật khẩu ¶ Extend use case: Đổi mật khẩu ¶ Extend use case: Cập nhật thông tin tài khoản ¶ Extend use case: Cập nhật thông tin khôi phục tài khoản ¶ Extend use case: Thiết lập tài khoản ngân hàng nhận tiền ¶ Extend use case: Kết nối dịch vụ thông báo biến động số dư
[Luồng sự kiện phụ] Người dùng chọn “Hủy” hoặc rời màn hình trước khi xác nhận: hệ thống không lưu thay đổi. Mã OTP hết hiệu lực: người dùng yêu cầu gửi mã mới.
[Extend use case] Đăng ký tài khoản Chủ trọ ¶ 1. Người dùng nhập số điện thoại, mật khẩu, xác nhận mật khẩu và chọn “Đăng ký”. ¶ 2. Hệ thống kiểm tra dữ liệu và kiểm tra số điện thoại đã tồn tại chưa. ¶ 3. Hệ thống gửi mã OTP qua SMS; người dùng nhập mã. ¶ 4. Hệ thống tạo tài khoản vai trò Chủ trọ và chuyển đến thiết lập nhà trọ. ¶ Rẽ nhánh 1: 2.1 Dữ liệu không hợp lệ → Hiển thị lỗi, yêu cầu nhập lại. ¶ Rẽ nhánh 2: 2.2 Số điện thoại đã tồn tại → Thông báo và hướng dẫn đăng nhập. ¶ Rẽ nhánh 3: 3.1 Mã OTP sai hoặc hết hiệu lực → Cho nhập lại hoặc gửi mã mới.
[Extend use case] Đăng nhập tài khoản ¶ 1. Người dùng nhập số điện thoại, mật khẩu và chọn “Đăng nhập”. ¶ 2. Hệ thống kiểm tra thông tin xác thực. ¶ 3. Hệ thống kiểm tra trạng thái xác minh số điện thoại. ¶ 4. Hệ thống tạo phiên đăng nhập và chuyển đến giao diện theo vai trò đã chọn. ¶ Rẽ nhánh 1: 2.1 Sai thông tin → Hiển thị lỗi, yêu cầu nhập lại. ¶ Rẽ nhánh 2: 3.1 Chưa xác minh → Gửi OTP qua SMS, người dùng nhập mã để xác minh. ¶ Rẽ nhánh 3: 4.1 Tài khoản không có vai trò đã chọn → Thông báo và yêu cầu chọn lại vai trò.
[Extend use case] Đăng xuất tài khoản ¶ 1. Người dùng vào mục “Tôi”, chọn “Đăng xuất”. ¶ 2. Hệ thống kết thúc phiên đăng nhập, xóa mã nhận thông báo của thiết bị và thông tin xác thực đã lưu. ¶ 3. Ứng dụng chuyển về màn hình chào.
[Extend use case] Quên mật khẩu ¶ 1. Người dùng chọn “Quên mật khẩu” và nhập số điện thoại chính. ¶ 2. Hệ thống hiển thị các phương thức khôi phục đã xác minh; người dùng chọn một phương thức. ¶ 3. Hệ thống gửi OTP qua SMS hoặc thư điện tử; người dùng nhập mã. ¶ 4. Người dùng nhập mật khẩu mới; hệ thống cập nhật và chuyển về màn hình đăng nhập. ¶ Rẽ nhánh 1: 1.1 Số điện thoại không tồn tại → Thông báo không tìm thấy tài khoản. ¶ Rẽ nhánh 2: 3.1 Mã sai hoặc hết hiệu lực → Cho nhập lại hoặc gửi mã mới. ¶ Rẽ nhánh 3: 4.1 Mật khẩu mới không hợp lệ → Hiển thị lỗi.
[Extend use case] Đổi mật khẩu ¶ 1. Người dùng vào “Thông tin tài khoản”, chọn “Đổi mật khẩu”. ¶ 2. Người dùng nhập mật khẩu hiện tại, mật khẩu mới và xác nhận mật khẩu mới. ¶ 3. Hệ thống kiểm tra và cập nhật mật khẩu. ¶ Rẽ nhánh 1: 3.1 Mật khẩu hiện tại sai, mật khẩu mới không hợp lệ hoặc không khớp → Hiển thị lỗi, yêu cầu nhập lại.
[Extend use case] Cập nhật thông tin tài khoản ¶ 1. Người dùng vào “Thông tin tài khoản”; hệ thống hiển thị thông tin hiện tại. ¶ 2. Người dùng sửa họ tên và chọn “Lưu”. ¶ 3. Hệ thống kiểm tra và lưu thông tin. ¶ Rẽ nhánh 1: 3.1 Họ tên bỏ trống hoặc không hợp lệ → Hiển thị lỗi. ¶ Số điện thoại chính không được sửa trong chức năng này.
[Extend use case] Cập nhật thông tin khôi phục tài khoản ¶ 1. Người dùng chọn “Thông tin khôi phục”, chọn thêm hoặc thay đổi thư điện tử hoặc số điện thoại phụ. ¶ 2. Người dùng nhập mật khẩu hiện tại để xác thực lại. ¶ 3. Người dùng nhập thông tin mới; hệ thống kiểm tra định dạng và giới hạn số lượng. ¶ 4. Hệ thống gửi OTP đến thông tin mới; người dùng nhập mã; hệ thống lưu ở trạng thái đã xác minh. ¶ Rẽ nhánh 1: 2.1 Mật khẩu sai → Yêu cầu nhập lại. ¶ Rẽ nhánh 2: 3.1 Sai định dạng hoặc vượt giới hạn hai thư điện tử, một số điện thoại phụ → Hiển thị lỗi. ¶ Rẽ nhánh 3: 4.1 OTP sai hoặc hết hiệu lực → Cho nhập lại hoặc gửi mã mới.
[Extend use case] Thiết lập tài khoản ngân hàng nhận tiền ¶ 1. Chủ trọ vào “Tài khoản nhận tiền” và nhập mật khẩu hiện tại. ¶ 2. Chủ trọ chọn ngân hàng, nhập số tài khoản và tên chủ tài khoản. ¶ 3. Hệ thống kiểm tra dữ liệu và hiển thị lại để đối chiếu. ¶ 4. Chủ trọ xác nhận; hệ thống lưu tài khoản nhận tiền. ¶ Rẽ nhánh 1: 1.1 Mật khẩu sai → Yêu cầu nhập lại. ¶ Rẽ nhánh 2: 3.1 Dữ liệu không hợp lệ → Hiển thị lỗi. ¶ Rẽ nhánh 3: 4.1 Chủ trọ chọn “Sửa lại” → Quay lại bước 2.
[Extend use case] Kết nối dịch vụ thông báo biến động số dư ¶ 1. Chủ trọ chọn “Kết nối thông báo biến động số dư”. ¶ 2. Hệ thống kiểm tra đã có tài khoản nhận tiền; Chủ trọ nhập mật khẩu hiện tại. ¶ 3. Hệ thống tạo và hiển thị địa chỉ tiếp nhận và khóa xác thực riêng của nhà trọ. ¶ 4. Chủ trọ khai báo thông tin này tại dịch vụ bên ngoài rồi chọn “Hoàn tất”; hệ thống lưu cấu hình kết nối và bắt đầu tiếp nhận thông báo giao dịch; chỉ thông báo đã được xác thực hợp lệ mới được đối chiếu tự động. ¶ Rẽ nhánh 1: 2.1 Chưa có tài khoản nhận tiền → Yêu cầu thiết lập trước. ¶ Rẽ nhánh 2: 2.2 Mật khẩu sai → Yêu cầu nhập lại. ¶ Rẽ nhánh 3: 4.1 Chủ trọ chọn “Ngắt kết nối” và xác thực lại → Hệ thống vô hiệu hóa khóa xác thực; các khoản chuyển khoản sau đó được xác nhận thủ công.

===== MỤC 3.2.1.2 =====
TIÊU ĐỀ: Quản lý nhà trọ, nhóm phòng và phòng
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý nhà trọ, nhóm phòng và phòng]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ
Use case chính (hình elip ở giữa khung): Quản lý nhà trọ, nhóm phòng và phòng
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Thiết lập thông tin nhà trọ; Quản lý nhóm phòng; Thêm phòng; Cập nhật phòng và tạm ngừng sử dụng phòng; Tra cứu phòng theo trạng thái
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý nhà trọ, nhóm phòng và phòng
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý nhà trọ, nhóm phòng và phòng
[Tác nhân] Chủ trọ
[Mô tả] Chủ trọ thiết lập thông tin một nhà trọ, tổ chức phòng theo nhóm, thêm, cập nhật, tạm ngừng và tra cứu phòng theo trạng thái.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập. Với chức năng về phòng, nhà trọ đã được thiết lập.
[Điều kiện hậu quyết] Thành công: Thông tin nhà trọ, nhóm phòng hoặc phòng được lưu; trạng thái phòng phản ánh đúng nghiệp vụ. ¶ Thất bại: Dữ liệu không hợp lệ hoặc thao tác không được phép, hệ thống hiển thị lỗi và giữ nguyên dữ liệu.
[Luồng sự kiện chính] 1. Chủ trọ vào mục “Phòng” hoặc “Thông tin nhà trọ”. ¶ 2. Hệ thống hiển thị dữ liệu thuộc nhà trọ của Chủ trọ. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Thiết lập thông tin nhà trọ ¶ Extend use case: Quản lý nhóm phòng ¶ Extend use case: Thêm phòng ¶ Extend use case: Cập nhật phòng và tạm ngừng sử dụng phòng ¶ Extend use case: Tra cứu phòng theo trạng thái
[Luồng sự kiện phụ] Chủ trọ chọn “Hủy” trước khi lưu: hệ thống không lưu thay đổi.
[Extend use case] Thiết lập thông tin nhà trọ ¶ 1. Hệ thống kiểm tra tài khoản đã có nhà trọ chưa. ¶ 2. Chủ trọ nhập tên, địa chỉ, ngày dự kiến lập phiếu và số ngày cho phép thanh toán (mặc định 5). ¶ 3. Hệ thống kiểm tra và lưu. ¶ Rẽ nhánh 1: 1.1 Đã có nhà trọ → Mở thông tin hiện tại để cập nhật, không tạo nhà trọ thứ hai. ¶ Rẽ nhánh 2: 3.1 Bỏ trống tên, địa chỉ; ngày lập phiếu ngoài khoảng 1–28; số ngày không phải số nguyên dương → Hiển thị lỗi.
[Extend use case] Quản lý nhóm phòng ¶ 1. Chủ trọ vào “Nhóm phòng”; hệ thống hiển thị danh sách nhóm. ¶ 2. Chủ trọ chọn thêm, đổi tên hoặc xóa nhóm. ¶ 3. Hệ thống kiểm tra và lưu. ¶ Rẽ nhánh 1: 3.1 Tên bỏ trống hoặc trùng → Hiển thị lỗi. ¶ Rẽ nhánh 2: 3.2 Xóa nhóm còn phòng → Từ chối, yêu cầu chuyển phòng sang nhóm khác trước. ¶ Rẽ nhánh 3: 3.3 Xóa nhóm không còn phòng → Yêu cầu xác nhận rồi xóa.
[Extend use case] Thêm phòng ¶ 1. Chủ trọ chọn “Thêm phòng”. ¶ 2. Chủ trọ nhập tên phòng, nhóm phòng, giá thuê tháng, ghi chú và số lượng phòng, chọn “Lưu”. ¶ 3. Hệ thống tạo danh sách phòng theo số lượng; khi số lượng lớn hơn một, tên phòng là tên gốc và được đánh số từ 1. ¶ 4. Hệ thống kiểm tra và tạo các phòng với trạng thái Trống. ¶ Rẽ nhánh 1: 4.1 Tên trống, trùng phòng đã có, số lượng nhỏ hơn 1 hoặc giá âm → Chỉ rõ lỗi, chưa lưu phòng nào.
[Extend use case] Cập nhật phòng và tạm ngừng sử dụng phòng ¶ 1. Chủ trọ chọn một phòng, chọn “Chỉnh sửa”, “Tạm ngừng sử dụng” hoặc “Mở lại”. ¶ 2. Khi chỉnh sửa: hệ thống kiểm tra và lưu tên, nhóm, giá thuê, ghi chú; giá mới không đổi giá của hợp đồng đang hiệu lực. ¶ 3. Khi tạm ngừng: hệ thống kiểm tra phòng đang Trống rồi chuyển sang Tạm ngừng sử dụng. ¶ 4. Khi mở lại: hệ thống chuyển phòng về Trống. ¶ Rẽ nhánh 1: 2.1 Dữ liệu không hợp lệ → Hiển thị lỗi. ¶ Rẽ nhánh 2: 3.1 Phòng không ở trạng thái Trống → Từ chối và nêu lý do.
[Extend use case] Tra cứu phòng theo trạng thái ¶ 1. Hệ thống hiển thị danh sách phòng theo nhóm kèm trạng thái. ¶ 2. Chủ trọ lọc theo trạng thái, nhóm hoặc nhập tên phòng. ¶ 3. Chủ trọ chọn một phòng; hệ thống hiển thị chi tiết, phiếu giữ phòng hoặc hợp đồng đang gắn và thao tác phù hợp. ¶ Rẽ nhánh 1: 2.1 Không có phòng phù hợp → Hiển thị “Không tìm thấy kết quả”.

===== MỤC 3.2.1.3 =====
TIÊU ĐỀ: Quản lý dịch vụ và đơn giá
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý dịch vụ và đơn giá]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ
Use case chính (hình elip ở giữa khung): Quản lý dịch vụ và đơn giá
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Khai báo dịch vụ, đơn giá và phương pháp tính; Cập nhật mức phí và trạng thái áp dụng dịch vụ
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý dịch vụ và đơn giá
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý dịch vụ và đơn giá
[Tác nhân] Chủ trọ
[Mô tả] Chủ trọ khai báo điện, nước và dịch vụ khác cùng đơn giá, phương pháp tính; cập nhật mức phí và trạng thái áp dụng theo ngày hiệu lực, xem lịch sử thay đổi.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập và đã thiết lập nhà trọ.
[Điều kiện hậu quyết] Thành công: Dịch vụ hoặc bản ghi mức phí, trạng thái áp dụng mới được lưu kèm ngày hiệu lực; phiếu đã phát hành không thay đổi. ¶ Thất bại: Dữ liệu không hợp lệ, hệ thống hiển thị lỗi.
[Luồng sự kiện chính] 1. Chủ trọ vào mục “Dịch vụ”. ¶ 2. Hệ thống hiển thị danh sách dịch vụ và mức phí hiện hành. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Khai báo dịch vụ, đơn giá và phương pháp tính ¶ Extend use case: Cập nhật mức phí và trạng thái áp dụng dịch vụ
[Luồng sự kiện phụ] Chủ trọ chọn “Lịch sử thay đổi”: hệ thống hiển thị các mức phí và trạng thái đã áp dụng theo thời gian.
[Extend use case] Khai báo dịch vụ, đơn giá và phương pháp tính ¶ 1. Chủ trọ chọn “Thêm dịch vụ”. ¶ 2. Chủ trọ chọn loại khoản phí, nhập tên, chọn phương pháp tính, nhập đơn giá, đơn vị và ngày hiệu lực. ¶ 3. Hệ thống kiểm tra và lưu dịch vụ cùng mức phí đầu tiên. ¶ Rẽ nhánh 1: 3.1 Tên trống hoặc trùng, đơn giá âm, phương pháp tính không phù hợp loại khoản phí → Hiển thị lỗi.
[Extend use case] Cập nhật mức phí và trạng thái áp dụng dịch vụ ¶ 1. Chủ trọ chọn một dịch vụ, chọn “Cập nhật mức phí” hoặc “Thay đổi trạng thái áp dụng”. ¶ 2. Chủ trọ nhập đơn giá mới và ngày hiệu lực, hoặc chọn hợp đồng, chọn áp dụng hoặc ngừng áp dụng, số suất và ngày hiệu lực. ¶ 3. Hệ thống kiểm tra và lưu thành bản ghi mới, không ghi đè bản ghi cũ. ¶ Rẽ nhánh 1: 3.1 Đơn giá âm hoặc ngày hiệu lực không hợp lệ → Hiển thị lỗi.

===== MỤC 3.2.1.4 =====
TIÊU ĐỀ: Giữ phòng và quản lý tiền cọc
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase giữ phòng và quản lý tiền cọc]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ
Use case chính (hình elip ở giữa khung): Giữ phòng và quản lý tiền cọc
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Lập phiếu giữ phòng; Xác nhận tiền cọc giữ phòng; Gia hạn phiếu giữ phòng; Hủy phiếu giữ phòng và xử lý tiền cọc
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase giữ phòng và quản lý tiền cọc
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Giữ phòng và quản lý tiền cọc
[Tác nhân] Chủ trọ
[Mô tả] Chủ trọ lập, gia hạn, hủy phiếu giữ phòng sau khi kiểm tra xung đột thời gian; xác nhận tiền cọc đã thực nhận và ghi nhận kết quả xử lý tiền cọc khi hủy.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập; phòng không ở trạng thái Tạm ngừng sử dụng.
[Điều kiện hậu quyết] Thành công: Phiếu giữ phòng, tiền cọc thực nhận hoặc kết quả hủy được lưu; trạng thái phòng được cập nhật. ¶ Thất bại: Có xung đột thời gian hoặc dữ liệu không hợp lệ, hệ thống từ chối và nêu lý do.
[Luồng sự kiện chính] 1. Chủ trọ chọn một phòng hoặc một phiếu giữ phòng. ¶ 2. Hệ thống hiển thị thông tin phòng và phiếu giữ phòng hiện có. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Lập phiếu giữ phòng ¶ Extend use case: Xác nhận tiền cọc giữ phòng ¶ Extend use case: Gia hạn phiếu giữ phòng ¶ Extend use case: Hủy phiếu giữ phòng và xử lý tiền cọc
[Luồng sự kiện phụ] Khi hết thời hạn giữ mà chưa lập hợp đồng, hệ thống tự chuyển phiếu sang quá hạn và thông báo cho Chủ trọ; phiếu không tự hủy, không tự làm mất cọc và vẫn ngăn lập phiếu mới có thời gian xung đột.
[Extend use case] Lập phiếu giữ phòng ¶ 1. Chủ trọ chọn phòng, chọn “Giữ phòng”. ¶ 2. Chủ trọ nhập họ tên, số điện thoại người giữ, ngày nhận dự kiến, thời hạn giữ, tiền cọc và thỏa thuận xử lý cọc. ¶ 3. Hệ thống kiểm tra dữ liệu, tiền cọc lớn hơn 0 và không vượt giá thuê một tháng đã thỏa thuận, thời hạn giữ không sớm hơn ngày lập phiếu, và kiểm tra xung đột theo ngày nhận dự kiến. ¶ 4. Hệ thống tạo phiếu với tiền cọc chưa nhận; phòng Trống chuyển sang Đã giữ chỗ. ¶ Rẽ nhánh 1: 3.1 Dữ liệu không hợp lệ, tiền cọc bằng 0 hoặc vượt giá thuê một tháng → Hiển thị lỗi. ¶ Rẽ nhánh 2: 3.2 Phòng tạm ngừng, trùng thời gian hợp đồng chưa thanh lý hoặc đã có phiếu chưa xử lý, kể cả phiếu quá hạn → Từ chối, nêu nguyên nhân.
[Extend use case] Xác nhận tiền cọc giữ phòng ¶ 1. Chủ trọ mở phiếu có tiền cọc chưa nhận. ¶ 2. Nếu chuyển khoản, Chủ trọ chọn “Hiển thị VietQR”; hệ thống tạo mã chứa tài khoản nhận, số tiền, nội dung đối chiếu. ¶ 3. Chủ trọ kiểm tra tiền thực nhận, chọn “Xác nhận đã nhận cọc”, nhập số tiền và hình thức. ¶ 4. Hệ thống ghi nhận tiền cọc đang giữ, không tính vào doanh thu. ¶ Rẽ nhánh 1: 2.1 Chưa có tài khoản nhận tiền → Yêu cầu thiết lập trước. ¶ Rẽ nhánh 2: 3.1 Chưa nhận được tiền → Phiếu giữ nguyên tình trạng chưa nhận cọc.
[Extend use case] Gia hạn phiếu giữ phòng ¶ 1. Chủ trọ mở phiếu còn hiệu lực hoặc quá hạn, chọn “Gia hạn”. ¶ 2. Chủ trọ nhập thời hạn giữ mới và ngày nhận dự kiến mới nếu có. ¶ 3. Hệ thống kiểm tra thời hạn và xung đột. ¶ 4. Hệ thống cập nhật thời hạn, đưa phiếu về còn hiệu lực và lưu lịch sử gia hạn. ¶ Rẽ nhánh 1: 3.1 Thời hạn không muộn hơn hiện tại, sớm hơn ngày thực hiện hoặc có xung đột → Hiển thị lỗi.
[Extend use case] Hủy phiếu giữ phòng và xử lý tiền cọc ¶ 1. Sau khi liên hệ người giữ phòng, kể cả khi hai bên chưa thống nhất, Chủ trọ mở phiếu, chọn “Hủy phiếu”; hệ thống hiển thị tiền cọc đã thực nhận. ¶ 2. Chủ trọ chọn hoàn toàn bộ, hoàn một phần hoặc không hoàn, nhập số tiền hoàn và lý do. ¶ 3. Hệ thống kiểm tra và yêu cầu xác nhận. ¶ 4. Hệ thống ghi nhận khoản hoàn theo xác nhận của Chủ trọ, chuyển phần giữ lại thành doanh thu khác mà không tạo giao dịch thu tiền mới, hủy phiếu và trả phòng về Trống nếu không còn phiếu hoặc hợp đồng khác. ¶ Rẽ nhánh 1: 3.1 Số tiền hoàn ngoài khoảng từ 0 đến tiền cọc đã nhận hoặc thiếu lý do → Hiển thị lỗi.

===== MỤC 3.2.1.5 =====
TIÊU ĐỀ: Quản lý hợp đồng và thành viên
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý hợp đồng và thành viên]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ
Use case chính (hình elip ở giữa khung): Quản lý hợp đồng và thành viên
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Lập hợp đồng từ phiếu giữ phòng; Nhập hợp đồng đang còn hiệu lực; Tạo và liên kết tài khoản Khách thuê
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý hợp đồng và thành viên
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý hợp đồng và thành viên
[Tác nhân] Chủ trọ
[Mô tả] Chủ trọ lập hợp đồng từ phiếu giữ phòng hoặc nhập hợp đồng đang thuê, lưu thành viên, người đứng tên, chế độ thanh toán, tiền cọc bảo đảm; hệ thống tạo hoặc liên kết tài khoản Khách thuê.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập. Hai bên đã ký hợp đồng ngoài ứng dụng.
[Điều kiện hậu quyết] Thành công: Hợp đồng, thành viên và tiền cọc bảo đảm được lưu; phòng chuyển sang Đang thuê; thành viên có số điện thoại có tài khoản Khách thuê. ¶ Thất bại: Dữ liệu không hợp lệ hoặc xung đột thời gian, hệ thống hiển thị lỗi và không lưu.
[Luồng sự kiện chính] 1. Chủ trọ mở phiếu giữ phòng hoặc chọn một phòng Trống. ¶ 2. Hệ thống hiển thị biểu mẫu hợp đồng. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Lập hợp đồng từ phiếu giữ phòng ¶ Extend use case: Nhập hợp đồng đang còn hiệu lực ¶ Extend use case: Tạo và liên kết tài khoản Khách thuê
[Luồng sự kiện phụ] Chủ trọ chọn “Hủy” trước khi lưu: hệ thống không tạo hợp đồng, phiếu giữ phòng giữ nguyên.
[Extend use case] Lập hợp đồng từ phiếu giữ phòng ¶ 1. Chủ trọ mở phiếu giữ phòng, chọn “Lập hợp đồng”; hệ thống điền sẵn phòng và người giữ phòng. ¶ 2. Chủ trọ nhập thời hạn, giá thuê, dịch vụ và số suất, tiền cọc bảo đảm, thành viên, người đứng tên, chế độ thanh toán và chứng từ. ¶ 3. Hệ thống kiểm tra dữ liệu và xung đột thời gian. ¶ 4. Hệ thống lưu hợp đồng, chuyển phiếu sang đã lập hợp đồng, ghi nhận khoản cọc giữ phòng sẽ cấn trừ một lần vào tháng đầu, tối đa bằng tiền thuê kỳ đầu, ghi phần cọc vượt là khoản cần hoàn cho người đặt cọc, ghi riêng cọc bảo đảm, chuyển phòng sang Đang thuê. ¶ Rẽ nhánh 1: 3.1 Thiếu dữ liệu, ngày kết thúc không sau ngày bắt đầu, không đúng một người đứng tên hoặc xung đột → Hiển thị lỗi.
[Extend use case] Nhập hợp đồng đang còn hiệu lực ¶ 1. Chủ trọ chọn phòng Trống, chọn “Nhập hợp đồng đang thuê”. ¶ 2. Chủ trọ nhập thông tin hợp đồng và dữ liệu ban đầu: tiền cọc đang giữ, công nợ đầu kỳ, chỉ số điện nước ban đầu. ¶ 3. Hệ thống kiểm tra dữ liệu. ¶ 4. Hệ thống lưu hợp đồng và dữ liệu ban đầu dưới dạng số dư ban đầu, không tạo khoản thu tiền mặt hoặc chuyển khoản mới; chuyển phòng sang Đang thuê; không phát sinh khoản cấn trừ cọc giữ phòng. ¶ Rẽ nhánh 1: 3.1 Số tiền hoặc chỉ số âm, không đúng một người đứng tên hoặc xung đột → Hiển thị lỗi.
[Extend use case] Tạo và liên kết tài khoản Khách thuê ¶ 1. Khi lưu hợp đồng hoặc bổ sung thành viên, hệ thống xét từng thành viên. ¶ 2. Thành viên không có số điện thoại chỉ được ghi nhận là người cư trú. ¶ 3. Số điện thoại chưa có tài khoản: hệ thống tạo tài khoản Khách thuê, sinh mật khẩu ban đầu và hiển thị để Chủ trọ chia sẻ. ¶ 4. Số điện thoại đã có tài khoản: hệ thống liên kết, bổ sung vai trò Khách thuê nếu chưa có, không đổi mật khẩu. ¶ Rẽ nhánh 1: 3.1 Lần đăng nhập đầu, tài khoản mới phải xác minh số điện thoại bằng OTP.

===== MỤC 3.2.1.6 =====
TIÊU ĐỀ: Bàn giao phòng
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase bàn giao phòng]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Khách thuê
Use case chính (hình elip ở giữa khung): Bàn giao phòng
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Bàn giao phòng khi nhận phòng; Bàn giao khi trả phòng
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase bàn giao phòng
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Bàn giao phòng
[Tác nhân] Chủ trọ, Khách thuê
[Mô tả] Chủ trọ lập biên bản bàn giao khi nhận và khi trả phòng gồm hiện trạng, tài sản, chìa khóa, chỉ số, hình ảnh; Khách thuê xem và xác nhận hoặc phản hồi.
[Điều kiện tiên quyết] Hợp đồng đang còn hiệu lực (nhận phòng) hoặc đang chờ thanh lý (trả phòng). Người dùng đã đăng nhập.
[Điều kiện hậu quyết] Thành công: Biên bản được lưu và được Khách thuê xác nhận; với biên bản trả phòng mà Khách thuê không phản hồi, Chủ trọ hoàn tất ghi nhận với trạng thái Khách chưa xác nhận. Chỉ số trong biên bản được dùng làm chỉ số đầu hoặc chỉ số cuối. ¶ Thất bại: Dữ liệu không hợp lệ hoặc Khách thuê chưa đồng ý, biên bản được chỉnh sửa và gửi lại.
[Luồng sự kiện chính] 1. Chủ trọ mở hợp đồng, chọn lập biên bản. ¶ 2. Khách thuê nhận thông báo và mở biên bản. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Bàn giao phòng khi nhận phòng ¶ Extend use case: Bàn giao khi trả phòng
[Luồng sự kiện phụ] Khách thuê chưa đồng ý: gửi phản hồi, Chủ trọ chỉnh sửa và gửi lại biên bản. Việc Chủ trọ hoàn tất ghi nhận khi khách chưa xác nhận không có nghĩa khách đã đồng ý với tình trạng phòng hoặc khoản khấu trừ.
[Extend use case] Bàn giao phòng khi nhận phòng ¶ 1. Chủ trọ chọn “Lập biên bản bàn giao”, ghi hiện trạng, tài sản, số chìa khóa, chỉ số điện nước, hình ảnh. ¶ 2. Hệ thống kiểm tra và lưu biên bản, thông báo cho Khách thuê. ¶ 3. Khách thuê chọn “Xác nhận”; hệ thống dùng chỉ số trong biên bản làm chỉ số ban đầu. ¶ Rẽ nhánh 1: 2.1 Thiếu chỉ số cho khoản theo công tơ hoặc chỉ số âm → Hiển thị lỗi. ¶ Rẽ nhánh 2: 3.1 Khách thuê gửi phản hồi → Thông báo Chủ trọ chỉnh sửa và gửi lại.
[Extend use case] Bàn giao khi trả phòng ¶ 1. Chủ trọ mở hợp đồng chờ thanh lý, chọn “Lập biên bản trả phòng”; hệ thống hiển thị biên bản nhận phòng để đối chiếu. ¶ 2. Chủ trọ ghi hiện trạng, tài sản, chìa khóa nhận lại, hư hỏng, chỉ số cuối và hình ảnh. ¶ 3. Hệ thống kiểm tra, lưu biên bản ở trạng thái chờ xác nhận và thông báo Khách thuê. ¶ 4. Khách thuê chọn “Xác nhận”; hệ thống hoàn tất biên bản và chốt chỉ số cuối kỳ làm căn cứ quyết toán. ¶ Rẽ nhánh 1: 3.1 Chỉ số cuối nhỏ hơn chỉ số đã chốt gần nhất → Hiển thị lỗi. ¶ Rẽ nhánh 2: 4.1 Khách thuê phản hồi → Chủ trọ chỉnh sửa biên bản chưa hoàn tất và gửi lại. ¶ Rẽ nhánh 3: 4.2 Khách thuê không phản hồi → Chủ trọ liên hệ ngoài ứng dụng, chọn “Hoàn tất ghi nhận – Khách chưa xác nhận”, nhập ghi chú, bằng chứng; hệ thống lưu trạng thái chưa được xác nhận và chốt chỉ số cuối kỳ.

===== MỤC 3.2.1.7 =====
TIÊU ĐỀ: Quản lý chỉ số điện nước
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý chỉ số điện nước]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Khách thuê
Use case chính (hình elip ở giữa khung): Quản lý chỉ số điện nước
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Ghi nhận và chốt chỉ số điện nước; Ghi nhận thay công tơ; Phản hồi và điều chỉnh chỉ số đã chốt
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý chỉ số điện nước
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý chỉ số điện nước
[Tác nhân] Chủ trọ, Khách thuê
[Mô tả] Chủ trọ ghi nhận, chốt chỉ số theo kỳ, ghi nhận thay công tơ và điều chỉnh có lưu lịch sử; Khách thuê xem chỉ số, hình ảnh công tơ và gửi phản hồi.
[Điều kiện tiên quyết] Người dùng đã đăng nhập; phòng có công tơ đang dùng.
[Điều kiện hậu quyết] Thành công: Chỉ số được chốt kèm hình ảnh, người chốt, thời điểm; điều chỉnh được lưu lịch sử. ¶ Thất bại: Chỉ số không hợp lệ, hệ thống từ chối.
[Luồng sự kiện chính] 1. Chủ trọ vào mục “Chỉ số điện nước”, chọn kỳ và phòng; Khách thuê xem chỉ số của phòng mình. ¶ 2. Hệ thống hiển thị chỉ số đã chốt lần trước. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Ghi nhận và chốt chỉ số điện nước ¶ Extend use case: Ghi nhận thay công tơ ¶ Extend use case: Phản hồi và điều chỉnh chỉ số đã chốt
[Luồng sự kiện phụ] Chỉ số đã chốt không được sửa hoặc xóa trực tiếp; mọi thay đổi đi qua chức năng điều chỉnh.
[Extend use case] Ghi nhận và chốt chỉ số điện nước ¶ 1. Chủ trọ nhập chỉ số mới và đính kèm hình ảnh cho các khoản điện, nước đang tính theo công tơ; khoản nước theo người hoặc cố định không cần chỉ số. ¶ 2. Hệ thống so sánh với chỉ số lần trước. ¶ 3. Chủ trọ chọn “Chốt chỉ số”; hệ thống lưu chỉ số đã chốt cùng hình ảnh, người chốt, thời điểm. ¶ Rẽ nhánh 1: 2.1 Chỉ số mới nhỏ hơn chỉ số cũ → Từ chối, yêu cầu kiểm tra lại. ¶ Rẽ nhánh 2: 2.2 Mức tiêu thụ bất thường → Cảnh báo; Chủ trọ nhập lại hoặc xác nhận tiếp tục.
[Extend use case] Ghi nhận thay công tơ ¶ 1. Chủ trọ chọn phòng, chọn “Thay công tơ”. ¶ 2. Chủ trọ chọn loại công tơ, nhập ngày thay, chỉ số cuối công tơ cũ, chỉ số đầu công tơ mới và hình ảnh. ¶ 3. Hệ thống kiểm tra, đóng công tơ cũ và tạo công tơ mới. ¶ Rẽ nhánh 1: 3.1 Chỉ số cuối công tơ cũ nhỏ hơn chỉ số đã chốt gần nhất hoặc chỉ số đầu âm → Hiển thị lỗi.
[Extend use case] Phản hồi và điều chỉnh chỉ số đã chốt ¶ 1. Khách thuê chọn “Gửi phản hồi” trên chỉ số và nhập nội dung; hệ thống thông báo Chủ trọ. ¶ 2. Chủ trọ đối chiếu công tơ thực tế. ¶ 3. Chỉ số sai: Chủ trọ chọn “Điều chỉnh chỉ số”, nhập giá trị đúng và lý do; hệ thống lưu giá trị mới và lịch sử điều chỉnh, không xóa bản ghi cũ. ¶ 4. Hệ thống thông báo kết quả cho Khách thuê. ¶ Rẽ nhánh 1: 2.1 Chỉ số đúng → Chủ trọ trả lời và đóng phản hồi. ¶ Rẽ nhánh 2: 3.1 Chỉ số đã dùng trong phiếu đã phát hành → Phiếu không tự đổi; phiếu chưa có thanh toán được xác nhận thì Chủ trọ chỉnh sửa phiếu, phiếu đã có thanh toán thì Chủ trọ ghi nhận khoản điều chỉnh riêng.

===== MỤC 3.2.1.8 =====
TIÊU ĐỀ: Quản lý phiếu báo phí
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý phiếu báo phí]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ
Use case chính (hình elip ở giữa khung): Quản lý phiếu báo phí
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Lập phiếu báo phí nháp; Phân bổ nghĩa vụ thanh toán; Kiểm tra và phát hành phiếu báo phí; Điều chỉnh phiếu báo phí đã phát hành
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý phiếu báo phí
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý phiếu báo phí
[Tác nhân] Chủ trọ
[Mô tả] Hệ thống tính phí và lập phiếu nháp, phân bổ nghĩa vụ thanh toán; Chủ trọ kiểm tra và phát hành phiếu; điều chỉnh phiếu đã phát hành khi chưa có thanh toán được xác nhận và lưu lịch sử; khóa chỉnh sửa trực tiếp khi phiếu đã có thanh toán và ghi nhận khoản điều chỉnh tăng hoặc giảm riêng, liên kết với phiếu gốc.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập; hợp đồng còn hiệu lực.
[Điều kiện hậu quyết] Thành công: Phiếu được lập, phát hành với hạn thanh toán xác định; các phần phải trả có tổng bằng tổng phiếu; mọi điều chỉnh sau phát hành được lưu lịch sử. ¶ Thất bại: Thiếu chỉ số chốt hoặc thao tác không được phép, phiếu giữ nguyên.
[Luồng sự kiện chính] 1. Đến ngày dự kiến lập phiếu hoặc Chủ trọ chọn “Lập phiếu báo phí”. ¶ 2. Hệ thống lập phiếu nháp và thông báo Chủ trọ. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Lập phiếu báo phí nháp ¶ Extend use case: Phân bổ nghĩa vụ thanh toán ¶ Extend use case: Kiểm tra và phát hành phiếu báo phí ¶ Extend use case: Điều chỉnh phiếu báo phí đã phát hành
[Luồng sự kiện phụ] Phiếu nháp chưa phát hành không gửi đến Khách thuê và có thể được tính lại khi dữ liệu thay đổi. Phiếu đã có thanh toán được xác nhận không được chỉnh sửa hoặc hủy trực tiếp.
[Extend use case] Lập phiếu báo phí nháp ¶ 1. Hệ thống tính tiền phòng: tháng đủ bằng 100% giá thuê; kỳ lẻ bằng số ngày nhân giá thuê chia 30, làm tròn một lần đến 1.000 đồng. ¶ 2. Tháng đầu của hợp đồng lập từ phiếu giữ phòng: cấn trừ một lần cọc giữ phòng, không vượt tiền thuê kỳ đầu; phần cọc vượt được ghi là khoản cần hoàn, tách khỏi phiếu. ¶ 3. Hệ thống tính điện nước theo chỉ số đã chốt, các dịch vụ khác theo phương pháp, đơn giá, số suất; cộng khoản phát sinh và khoản điều chỉnh chuyển sang kỳ này. ¶ 4. Hệ thống phân bổ nghĩa vụ và lưu phiếu nháp. ¶ Rẽ nhánh 1: 3.1 Chưa có chỉ số chốt → Chưa tính khoản này, đánh dấu phiếu thiếu chỉ số.
[Extend use case] Phân bổ nghĩa vụ thanh toán ¶ 1. Hệ thống xác định chế độ thanh toán của hợp đồng. ¶ 2. Chế độ đại diện: tạo một phần phải trả bằng toàn bộ phiếu, gán cho người đại diện. ¶ 3. Chế độ chia đều: chia phần nguyên theo đồng cho các thành viên chịu trách nhiệm; phần dư cộng mỗi người một đồng theo thứ tự danh sách. ¶ 4. Hệ thống bù trừ khoản trả dư của từng thành viên và gán mã thanh toán riêng cho từng phần. ¶ Rẽ nhánh 1: 3.1 Tổng các phần luôn bằng tổng phiếu; hệ thống không làm tròn lại từng phần.
[Extend use case] Kiểm tra và phát hành phiếu báo phí ¶ 1. Chủ trọ mở phiếu nháp; hệ thống hiển thị chi tiết các khoản và các phần phải trả. ¶ 2. Chủ trọ giữ mức mặc định, nhập số tiền khác hoặc miễn phí từng khoản dịch vụ, lý do là tùy chọn; hệ thống lưu cả mức mặc định và số tiền sau điều chỉnh, tính lại tổng và phân bổ lại. ¶ 3. Chủ trọ chọn “Phát hành”; hệ thống kiểm tra chỉ số. ¶ 4. Hệ thống phát hành, lưu ngày phát hành, hạn thanh toán và thông báo đến người có nghĩa vụ. ¶ Rẽ nhánh 1: 3.1 Thiếu chỉ số chốt cho khoản theo công tơ → Từ chối phát hành, chỉ rõ khoản thiếu.
[Extend use case] Điều chỉnh phiếu báo phí đã phát hành ¶ 1. Chủ trọ mở phiếu đã phát hành; hệ thống xác định đã có khoản thanh toán được xác nhận chưa. ¶ 2. Chưa có: Chủ trọ chọn “Chỉnh sửa”, cập nhật khoản cần điều chỉnh, nhập lý do; hệ thống tính lại tổng và các phần phải trả, cập nhật trên cùng phiếu, giữ mã phiếu và hạn thanh toán, lưu lịch sử, đánh dấu “Đã điều chỉnh”, vô hiệu yêu cầu VietQR đang chờ theo số tiền cũ. ¶ 3. Đã có: hệ thống khóa chỉnh sửa và hủy; Chủ trọ chọn “Ghi nhận điều chỉnh”, nhập tăng hoặc giảm, số tiền, lý do; hệ thống tạo khoản điều chỉnh riêng liên kết với phiếu gốc. ¶ 4. Hệ thống thông báo đến người có nghĩa vụ thanh toán. ¶ Rẽ nhánh 1: 3.1 Điều chỉnh giảm → Chủ trọ chọn bù trừ kỳ sau hoặc ghi nhận hoàn tiền. ¶ Rẽ nhánh 2: 3.2 Điều chỉnh tăng → Ghi nhận khoản phải thu bổ sung vào kỳ sau hoặc khi quyết toán.

===== MỤC 3.2.1.9 =====
TIÊU ĐỀ: Tra cứu thông tin thuê
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase tra cứu thông tin thuê]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Khách thuê
Use case chính (hình elip ở giữa khung): Tra cứu thông tin thuê
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase tra cứu thông tin thuê
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Tra cứu thông tin thuê
[Tác nhân] Khách thuê
[Mô tả] Khách thuê xem thông tin phòng, hợp đồng, thành viên, phiếu báo phí, chỉ số, lịch sử thanh toán và công nợ trong phạm vi hợp đồng được cấp quyền.
[Điều kiện tiên quyết] Khách thuê đã đăng nhập.
[Điều kiện hậu quyết] Thành công: Thông tin thuộc phạm vi quyền được hiển thị. ¶ Thất bại: Yêu cầu ngoài phạm vi quyền bị từ chối.
[Luồng sự kiện chính] 1. Khách thuê mở giao diện Khách thuê. ¶ 2. Hệ thống xác định các hợp đồng mà tài khoản là thành viên. ¶ 3. Hệ thống hiển thị chức năng: ¶ Extend use case: Tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê
[Luồng sự kiện phụ] Tài khoản chưa gắn với hợp đồng nào: hệ thống thông báo chưa có dữ liệu thuê.
[Extend use case] Tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê ¶ 1. Khách thuê chọn nội dung cần xem: phòng và hợp đồng, phiếu báo phí, chỉ số hoặc lịch sử thanh toán. ¶ 2. Hệ thống kiểm tra quyền đối với dữ liệu được yêu cầu. ¶ 3. Hệ thống hiển thị dữ liệu; nghĩa vụ hiển thị theo chế độ thanh toán; phiếu từng chỉnh sửa có dấu “Đã điều chỉnh” và lịch sử; khoản điều chỉnh riêng được hiển thị kèm lý do và kết quả xử lý. ¶ Rẽ nhánh 1: 2.1 Dữ liệu ngoài phạm vi hợp đồng → Từ chối truy cập. ¶ Rẽ nhánh 2: 3.1 Thành viên đã rời hợp đồng → Chỉ xem lịch sử thuộc phạm vi quyền còn hiệu lực.

===== MỤC 3.2.1.10 =====
TIÊU ĐỀ: Thanh toán VietQR và báo chuyển khoản
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase thanh toán VietQR và báo chuyển khoản]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Khách thuê
Use case chính (hình elip ở giữa khung): Thanh toán VietQR và báo chuyển khoản
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Tạo yêu cầu thanh toán VietQR; Báo chuyển khoản
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase thanh toán VietQR và báo chuyển khoản
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Thanh toán VietQR và báo chuyển khoản
[Tác nhân] Khách thuê
[Mô tả] Khách thuê tạo yêu cầu thanh toán VietQR cho toàn bộ hoặc một phần số dư phải trả, báo đã chuyển khoản kèm chứng từ và theo dõi kết quả xác nhận.
[Điều kiện tiên quyết] Khách thuê đã đăng nhập; phiếu đã phát hành còn số dư phải trả; Chủ trọ đã thiết lập tài khoản nhận tiền.
[Điều kiện hậu quyết] Thành công: Yêu cầu thanh toán có mã tham chiếu riêng và hạn 15 phút được tạo; báo chuyển khoản được ghi nhận chờ xác nhận. ¶ Thất bại: Số tiền không hợp lệ hoặc chưa có tài khoản nhận tiền, hệ thống thông báo.
[Luồng sự kiện chính] 1. Khách thuê mở phiếu báo phí, chọn “Thanh toán”. ¶ 2. Hệ thống hiển thị nghĩa vụ có thể thanh toán theo chế độ của hợp đồng. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Tạo yêu cầu thanh toán VietQR ¶ Extend use case: Báo chuyển khoản
[Luồng sự kiện phụ] Việc tạo mã hoặc báo đã chuyển không làm giảm công nợ; chỉ khoản đã được xác nhận mới làm giảm công nợ.
[Extend use case] Tạo yêu cầu thanh toán VietQR ¶ 1. Khách thuê chọn nghĩa vụ cần thanh toán (phần của mình hoặc mã tổng của phòng). ¶ 2. Khách thuê chọn thanh toán toàn bộ hoặc nhập số tiền một phần. ¶ 3. Hệ thống kiểm tra số tiền và tài khoản nhận tiền của Chủ trọ. ¶ 4. Hệ thống tạo yêu cầu có mã tham chiếu riêng, hạn 15 phút và hiển thị mã VietQR. ¶ Rẽ nhánh 1: 3.1 Số tiền bằng 0 hoặc vượt số dư → Hiển thị lỗi. ¶ Rẽ nhánh 2: 3.2 Chủ trọ chưa có tài khoản nhận tiền → Thông báo chưa thể tạo mã. ¶ Rẽ nhánh 3: 4.1 Hết 15 phút chưa có giao dịch xác nhận → Yêu cầu hết hạn, Khách thuê tạo yêu cầu mới.
[Extend use case] Báo chuyển khoản ¶ 1. Sau khi chuyển khoản, Khách thuê chọn “Tôi đã chuyển” trên yêu cầu thanh toán. ¶ 2. Khách thuê đính kèm hình ảnh chứng từ. ¶ 3. Hệ thống ghi nhận báo chuyển khoản chờ xác nhận và thông báo Chủ trọ. ¶ Rẽ nhánh 1: 3.1 Yêu cầu đã được xác nhận tự động → Hệ thống thông báo đã thanh toán, không tạo báo chuyển khoản.

===== MỤC 3.2.1.11 =====
TIÊU ĐỀ: Xác nhận thanh toán và đối chiếu giao dịch
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase xác nhận thanh toán và đối chiếu giao dịch]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Dịch vụ thông báo biến động số dư
Use case chính (hình elip ở giữa khung): Xác nhận thanh toán và đối chiếu giao dịch
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Xác nhận báo chuyển khoản; Tự động xác nhận giao dịch ngân hàng; Đối chiếu thủ công giao dịch không khớp; Ghi nhận thanh toán tiền mặt
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase xác nhận thanh toán và đối chiếu giao dịch
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Xác nhận thanh toán và đối chiếu giao dịch
[Tác nhân] Chủ trọ, Dịch vụ thông báo biến động số dư
[Mô tả] Chủ trọ xác nhận hoặc từ chối báo chuyển khoản, ghi nhận tiền mặt và đối chiếu giao dịch không khớp; hệ thống tự động xác nhận giao dịch do dịch vụ thông báo biến động số dư gửi đến khi đủ điều kiện.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập. Với tự động xác nhận, Chủ trọ đã kết nối dịch vụ thông báo biến động số dư.
[Điều kiện hậu quyết] Thành công: Khoản thu được ghi nhận một lần, phân bổ vào nghĩa vụ và công nợ được cập nhật trong cùng một giao dịch dữ liệu. ¶ Thất bại: Thông tin không khớp hoặc giao dịch đã ghi nhận, công nợ giữ nguyên.
[Luồng sự kiện chính] 1. Chủ trọ nhận thông báo báo chuyển khoản, giao dịch cần đối chiếu hoặc trực tiếp nhận tiền mặt. ¶ 2. Hệ thống hiển thị thông tin cần xử lý. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Xác nhận báo chuyển khoản ¶ Extend use case: Tự động xác nhận giao dịch ngân hàng ¶ Extend use case: Đối chiếu thủ công giao dịch không khớp ¶ Extend use case: Ghi nhận thanh toán tiền mặt
[Luồng sự kiện phụ] Một giao dịch ngân hàng hoặc một yêu cầu thanh toán đã ghi nhận sẽ không được ghi nhận lần thứ hai.
[Extend use case] Xác nhận báo chuyển khoản ¶ 1. Chủ trọ mở báo chuyển khoản và kiểm tra tiền thực nhận trong tài khoản ngân hàng. ¶ 2. Chủ trọ chọn “Xác nhận”; hệ thống kiểm tra giao dịch chưa từng ghi nhận. ¶ 3. Hệ thống ghi nhận khoản thu, phân bổ, cập nhật công nợ trong cùng một giao dịch dữ liệu và thông báo Khách thuê. ¶ Rẽ nhánh 1: 1.1 Chưa nhận được tiền hoặc không khớp → Chủ trọ chọn “Từ chối”, nhập lý do; công nợ giữ nguyên. ¶ Rẽ nhánh 2: 2.1 Đã được xác nhận trước đó → Không ghi nhận lần hai.
[Extend use case] Tự động xác nhận giao dịch ngân hàng ¶ 1. Dịch vụ gửi thông báo giao dịch tiền vào đến máy chủ. ¶ 2. Hệ thống kiểm tra khóa xác thực và mã định danh giao dịch do dịch vụ cung cấp. ¶ 3. Hệ thống đối chiếu với các khoản chuyển khoản đã xác nhận thủ công theo tài khoản nhận, số tiền, thời điểm và mã tham chiếu. ¶ 4. Hệ thống kiểm tra tài khoản nhận, mã tham chiếu, thời điểm giao dịch, số tiền và số dư còn phải trả. ¶ 5. Hệ thống ghi nhận khoản thu, phân bổ, cập nhật công nợ và trạng thái yêu cầu trong cùng một giao dịch dữ liệu, thông báo hai bên. ¶ Rẽ nhánh 1: 2.1 Khóa không hợp lệ → Từ chối thông báo. ¶ Rẽ nhánh 2: 2.2 Giao dịch đã ghi nhận → Bỏ qua. ¶ Rẽ nhánh 3: 3.1 Có dấu hiệu trùng khoản đã xác nhận thủ công → Đưa vào danh sách cần đối chiếu, không tạo khoản thu. ¶ Rẽ nhánh 4: 4.1 Không đủ điều kiện → Đưa vào danh sách cần đối chiếu, thông báo Chủ trọ.
[Extend use case] Đối chiếu thủ công giao dịch không khớp ¶ 1. Chủ trọ mở “Giao dịch cần đối chiếu”, chọn một giao dịch; hệ thống hiển thị số tiền, thời điểm, nội dung và nguyên nhân. ¶ 2. Chủ trọ xác định giao dịch có phải khoản thanh toán tiền thuê. ¶ 3. Có: Chủ trọ chọn phòng, nghĩa vụ và “Xác nhận”; hệ thống kiểm tra chưa ghi nhận, ghi nhận khoản thu và phân bổ. ¶ 4. Hệ thống lưu kết quả, người thực hiện, lý do; giao dịch rời danh sách chờ nhưng vẫn giữ trong lịch sử; thông báo Khách thuê. ¶ Rẽ nhánh 1: 2.1 Không liên quan hoặc đã được ghi nhận trước đó → Chủ trọ chọn “Không liên quan”, nhập lý do, không ghi nhận khoản thu. ¶ Rẽ nhánh 2: 3.1 Số tiền lớn hơn số còn thiếu → Phần chênh lệch là khoản trả dư.
[Extend use case] Ghi nhận thanh toán tiền mặt ¶ 1. Chủ trọ nhận, kiểm đếm tiền, mở phiếu và chọn “Thu tiền mặt”. ¶ 2. Chủ trọ nhập số tiền, chọn người trả và nghĩa vụ được thanh toán. ¶ 3. Hệ thống kiểm tra, ghi nhận khoản thu, phân bổ và cập nhật công nợ; thông báo Khách thuê. ¶ Rẽ nhánh 1: 3.1 Số tiền không lớn hơn 0 hoặc nghĩa vụ không thuộc phiếu → Hiển thị lỗi. ¶ Rẽ nhánh 2: 3.2 Số tiền lớn hơn số còn thiếu → Phần chênh lệch là khoản trả dư của người trả.

===== MỤC 3.2.1.12 =====
TIÊU ĐỀ: Theo dõi công nợ và nhắc thanh toán
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase theo dõi công nợ và nhắc thanh toán]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ
Use case chính (hình elip ở giữa khung): Theo dõi công nợ và nhắc thanh toán
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Theo dõi công nợ và nhắc thanh toán
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase theo dõi công nợ và nhắc thanh toán
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Theo dõi công nợ và nhắc thanh toán
[Tác nhân] Chủ trọ
[Mô tả] Chủ trọ xem số phải trả, đã trả, còn thiếu và khoản quá hạn theo phòng và từng phần phải trả; gửi nhắc thanh toán đến đúng người còn nghĩa vụ; xử lý khoản trả dư.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập.
[Điều kiện hậu quyết] Thành công: Công nợ hiển thị đúng dữ liệu đã xác nhận; thông báo nhắc được gửi và lưu lịch sử. ¶ Thất bại: Không có khoản còn nợ, hệ thống hiển thị danh sách rỗng.
[Luồng sự kiện chính] 1. Chủ trọ vào mục “Công nợ”. ¶ 2. Hệ thống tổng hợp phiếu đã phát hành chưa thanh toán đủ theo phòng. ¶ 3. Hệ thống hiển thị chức năng: ¶ Extend use case: Theo dõi công nợ và nhắc thanh toán
[Luồng sự kiện phụ] Hệ thống không tự tính tiền phạt chậm trả và không tự chấm dứt hợp đồng do quá hạn.
[Extend use case] Theo dõi công nợ và nhắc thanh toán ¶ 1. Hệ thống hiển thị số phải trả, đã trả, còn thiếu, hạn thanh toán và trạng thái của từng phần phải trả. ¶ 2. Chủ trọ chọn một phiếu để xem lịch sử thanh toán. ¶ 3. Chủ trọ chọn “Nhắc thanh toán”; hệ thống gửi thông báo đến người còn nghĩa vụ và lưu lịch sử. ¶ 4. Với khoản trả dư, Chủ trọ chọn bù trừ kỳ sau hoặc ghi nhận hoàn tiền. ¶ Rẽ nhánh 1: 1.1 Qua ngày đến hạn mà chưa trả đủ → Đánh dấu quá hạn từ ngày tiếp theo. ¶ Rẽ nhánh 2: 4.1 Không chọn → Khoản trả dư tự bù trừ vào kỳ sau của đúng người đã trả.

===== MỤC 3.2.1.13 =====
TIÊU ĐỀ: Quản lý sự cố
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý sự cố]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Khách thuê
Use case chính (hình elip ở giữa khung): Quản lý sự cố
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Gửi yêu cầu sự cố; Xử lý sự cố và ghi nhận chi phí; Xác nhận kết quả xử lý sự cố
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý sự cố
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý sự cố
[Tác nhân] Chủ trọ, Khách thuê
[Mô tả] Khách thuê hoặc Chủ trọ tạo yêu cầu sự cố; Chủ trọ tiếp nhận, cập nhật tiến độ, kết quả, chi phí và bên chịu chi phí; Khách thuê xác nhận hoặc phản hồi kết quả.
[Điều kiện tiên quyết] Người dùng đã đăng nhập; Khách thuê có hợp đồng còn hiệu lực.
[Điều kiện hậu quyết] Thành công: Yêu cầu sự cố và mọi lần cập nhật được lưu; chi phí được ghi nhận đúng bên chịu. ¶ Thất bại: Thiếu dữ liệu bắt buộc, hệ thống hiển thị lỗi.
[Luồng sự kiện chính] 1. Người dùng vào mục “Sự cố”. ¶ 2. Hệ thống hiển thị danh sách yêu cầu theo quyền. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Gửi yêu cầu sự cố ¶ Extend use case: Xử lý sự cố và ghi nhận chi phí ¶ Extend use case: Xác nhận kết quả xử lý sự cố
[Luồng sự kiện phụ] Sự cố do Chủ trọ tự tạo được Chủ trọ tự chuyển sang Hoàn tất sau khi xử lý xong.
[Extend use case] Gửi yêu cầu sự cố ¶ 1. Người dùng chọn “Tạo yêu cầu”, nhập mô tả, chọn mức độ ảnh hưởng và đính kèm hình ảnh. ¶ 2. Hệ thống kiểm tra dữ liệu. ¶ 3. Hệ thống tạo yêu cầu gắn với phòng, trạng thái Mới và thông báo Chủ trọ. ¶ Rẽ nhánh 1: 2.1 Thiếu mô tả hoặc mức độ → Hiển thị lỗi.
[Extend use case] Xử lý sự cố và ghi nhận chi phí ¶ 1. Chủ trọ mở yêu cầu Mới, chọn “Tiếp nhận”; hệ thống chuyển sang Đang xử lý và thông báo Khách thuê. ¶ 2. Chủ trọ cập nhật nguyên nhân, tiến độ. ¶ 3. Chủ trọ nhập kết quả và chi phí nếu có; hệ thống lưu lịch sử xử lý. ¶ 4. Yêu cầu do Khách thuê tạo: hệ thống chuyển sang Chờ khách xác nhận và thông báo. ¶ Rẽ nhánh 1: 3.1 Chủ trọ chịu chi phí → Ghi nhận khoản chi của nhà trọ. ¶ Rẽ nhánh 2: 3.2 Khách thuê chịu chi phí → Ghi nhận khoản phát sinh vào phiếu báo phí của hợp đồng. ¶ Rẽ nhánh 3: 4.1 Yêu cầu do Chủ trọ tự tạo → Chủ trọ xác nhận hoàn tất, hệ thống chuyển sang Hoàn tất.
[Extend use case] Xác nhận kết quả xử lý sự cố ¶ 1. Khách thuê mở yêu cầu Chờ khách xác nhận; hệ thống hiển thị kết quả, chi phí và bên chịu. ¶ 2. Khách thuê kiểm tra thực tế và chọn “Xác nhận”. ¶ 3. Hệ thống chuyển sang Hoàn tất và thông báo Chủ trọ. ¶ Rẽ nhánh 1: 2.1 Chưa khắc phục → Khách thuê chọn “Phản hồi”, hệ thống chuyển lại Đang xử lý.

===== MỤC 3.2.1.14 =====
TIÊU ĐỀ: Gia hạn và điều chỉnh hợp đồng
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase gia hạn và điều chỉnh hợp đồng]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Khách thuê
Use case chính (hình elip ở giữa khung): Gia hạn và điều chỉnh hợp đồng
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Gia hạn hợp đồng; Điều chỉnh hợp đồng
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase gia hạn và điều chỉnh hợp đồng
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Gia hạn và điều chỉnh hợp đồng
[Tác nhân] Chủ trọ, Khách thuê
[Mô tả] Hai bên gửi đề nghị; Chủ trọ ghi nhận nội dung đã thống nhất và ngày hiệu lực; người đứng tên xác nhận trên ứng dụng; hệ thống lưu phiên bản và lịch sử thay đổi.
[Điều kiện tiên quyết] Hợp đồng đang còn hiệu lực; người dùng đã đăng nhập.
[Điều kiện hậu quyết] Thành công: Phiên bản điều khoản mới và lịch sử thay đổi được lưu; phiếu đã phát hành không bị phân bổ lại. ¶ Thất bại: Dữ liệu không hợp lệ hoặc người đứng tên không xác nhận, hợp đồng giữ nguyên.
[Luồng sự kiện chính] 1. Hệ thống thông báo Chủ trọ khi hợp đồng sắp đến ngày kết thúc. ¶ 2. Một bên mở hợp đồng và gửi đề nghị. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Gia hạn hợp đồng ¶ Extend use case: Điều chỉnh hợp đồng
[Luồng sự kiện phụ] Hai bên không thống nhất: Chủ trọ đóng đề nghị, hợp đồng giữ nguyên.
[Extend use case] Gia hạn hợp đồng ¶ 1. Một bên gửi đề nghị gia hạn kèm ngày kết thúc mong muốn; hệ thống thông báo bên còn lại. ¶ 2. Sau khi thống nhất, Chủ trọ ghi nhận ngày kết thúc mới, ngày hiệu lực và chứng từ. ¶ 3. Hệ thống kiểm tra và gửi để người đứng tên xác nhận. ¶ 4. Người đứng tên xác nhận; hệ thống cập nhật thời hạn, lưu phiên bản mới và thông báo các thành viên. ¶ Rẽ nhánh 1: 3.1 Ngày mới không muộn hơn hiện tại hoặc xung đột phiếu giữ phòng → Hiển thị lỗi. ¶ Rẽ nhánh 2: 4.1 Người đứng tên không xác nhận → Hợp đồng giữ nguyên.
[Extend use case] Điều chỉnh hợp đồng ¶ 1. Sau khi thống nhất, Chủ trọ chọn “Điều chỉnh hợp đồng”, nhập nội dung thay đổi, ngày hiệu lực và chứng từ. ¶ 2. Hệ thống kiểm tra đúng một người đứng tên, người đại diện hoặc thành viên chịu trách nhiệm thanh toán theo chế độ. ¶ 3. Người đứng tên xác nhận; hệ thống lưu phiên bản mới và lịch sử. ¶ 4. Thay đổi thanh toán áp dụng từ kỳ tiếp theo; thành viên mới được tạo hoặc liên kết tài khoản. ¶ Rẽ nhánh 1: 2.1 Không hợp lệ → Hiển thị lỗi. ¶ Rẽ nhánh 2: 3.1 Người đứng tên không xác nhận → Hợp đồng giữ nguyên.

===== MỤC 3.2.1.15 =====
TIÊU ĐỀ: Trả phòng, thanh lý và quyết toán
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase trả phòng, thanh lý và quyết toán]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Khách thuê
Use case chính (hình elip ở giữa khung): Trả phòng, thanh lý và quyết toán
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Yêu cầu trả phòng; Thanh lý hợp đồng và quyết toán tiền cọc
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase trả phòng, thanh lý và quyết toán
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Trả phòng, thanh lý và quyết toán
[Tác nhân] Chủ trọ, Khách thuê
[Mô tả] Khách thuê gửi yêu cầu trả phòng và xem bảng quyết toán; Chủ trọ ghi nhận ngày chấm dứt, lập quyết toán tiền cọc, công nợ và hoàn tất thanh lý hợp đồng.
[Điều kiện tiên quyết] Hợp đồng đang còn hiệu lực (yêu cầu trả phòng); hoặc biên bản trả phòng đã hoàn tất, do Khách thuê xác nhận hoặc Chủ trọ hoàn tất ghi nhận, và chỉ số cuối kỳ đã chốt (quyết toán).
[Điều kiện hậu quyết] Thành công: Hợp đồng chuyển sang chờ thanh lý rồi đã thanh lý; khoản hoàn hoặc thu thêm được ghi nhận; trạng thái phòng được cập nhật. ¶ Thất bại: Thiếu căn cứ hoặc hai bên chưa thống nhất, quyết toán chưa hoàn tất.
[Luồng sự kiện chính] 1. Khách thuê hoặc Chủ trọ mở hợp đồng. ¶ 2. Hệ thống hiển thị thông tin hợp đồng và trạng thái. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Yêu cầu trả phòng ¶ Extend use case: Thanh lý hợp đồng và quyết toán tiền cọc
[Luồng sự kiện phụ] Việc trả phòng trước hạn không làm hệ thống tự tính lại tiền thuê, tự hoàn tiền thuê trả trước hoặc tự khấu trừ tiền cọc.
[Extend use case] Yêu cầu trả phòng ¶ 1. Khách thuê chọn “Yêu cầu trả phòng”, nhập ngày dự kiến và lý do. ¶ 2. Hệ thống kiểm tra ngày, lưu yêu cầu và thông báo Chủ trọ. ¶ 3. Chủ trọ nhập ngày chấm dứt được hai bên chấp thuận. ¶ 4. Hệ thống ghi nhận, chuyển hợp đồng sang chờ thanh lý và thông báo các thành viên. ¶ Rẽ nhánh 1: 2.1 Ngày dự kiến sớm hơn ngày gửi → Hiển thị lỗi. ¶ Rẽ nhánh 2: 1.1 Khách báo trực tiếp → Chủ trọ tự ghi nhận việc trả phòng.
[Extend use case] Thanh lý hợp đồng và quyết toán tiền cọc ¶ 1. Khi biên bản trả phòng đã được Khách thuê xác nhận hoặc Chủ trọ đã hoàn tất ghi nhận, Chủ trọ chọn “Lập quyết toán”; hệ thống tổng hợp điện nước, dịch vụ cuối kỳ, công nợ, tiền trả trước, khoản điều chỉnh chờ quyết toán, tiền cọc đang giữ. ¶ 2. Chủ trọ nhập tiền thuê đến ngày chấm dứt, phần hoàn, các khoản khấu trừ kèm lý do. ¶ 3. Hệ thống tính kết quả và gửi bảng quyết toán cho Khách thuê xem. ¶ 4. Khi hai bên thống nhất, Chủ trọ chọn “Hoàn tất quyết toán”; hệ thống ghi nhận khoản hoàn hoặc thu thêm, tách tiền cọc cấn trừ công nợ, khoản khấu trừ và phần hoàn; chỉ khoản khấu trừ có bản chất doanh thu mới vào doanh thu; chuyển hợp đồng sang đã thanh lý, cập nhật phòng. ¶ Rẽ nhánh 1: 2.1 Khoản khấu trừ thiếu lý do → Hiển thị lỗi. ¶ Rẽ nhánh 2: 1.1 Biên bản chưa được Khách thuê xác nhận → Vẫn lập được quyết toán, khoản khấu trừ không mặc nhiên coi là đã thống nhất. ¶ Rẽ nhánh 3: 4.1 Chưa thống nhất → Chủ trọ điều chỉnh bảng quyết toán.

===== MỤC 3.2.1.16 =====
TIÊU ĐỀ: Quản lý thu chi và thống kê
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý thu chi và thống kê]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ
Use case chính (hình elip ở giữa khung): Quản lý thu chi và thống kê
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Ghi nhận khoản thu chi khác; Xem thống kê
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý thu chi và thống kê
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý thu chi và thống kê
[Tác nhân] Chủ trọ
[Mô tả] Chủ trọ ghi nhận khoản thu chi khác; xem tiền thực thu, khoản chi, doanh thu, chênh lệch thu chi, công nợ, tiền cọc đang giữ và số phòng theo trạng thái.
[Điều kiện tiên quyết] Chủ trọ đã đăng nhập.
[Điều kiện hậu quyết] Thành công: Khoản thu chi được lưu; thống kê hiển thị đúng dữ liệu đã xác nhận của nhà trọ. ¶ Thất bại: Dữ liệu không hợp lệ, hệ thống hiển thị lỗi.
[Luồng sự kiện chính] 1. Chủ trọ vào mục “Thu chi” hoặc “Thống kê”. ¶ 2. Hệ thống hiển thị dữ liệu theo thời gian. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Ghi nhận khoản thu chi khác ¶ Extend use case: Xem thống kê
[Luồng sự kiện phụ] Các khoản phát sinh từ nghiệp vụ đã xác nhận được hệ thống tự ghi nhận, không nhập lại và không sửa trực tiếp trong mục “Thu chi”.
[Extend use case] Ghi nhận khoản thu chi khác ¶ 1. Chủ trọ chọn “Thêm khoản”, chọn thu hoặc chi, nhập nội dung, số tiền, ngày và chứng từ. ¶ 2. Hệ thống kiểm tra và lưu, cập nhật danh sách theo thời gian. ¶ Rẽ nhánh 1: 2.1 Nội dung trống, số tiền không lớn hơn 0 hoặc ngày không hợp lệ → Hiển thị lỗi.
[Extend use case] Xem thống kê ¶ 1. Hệ thống tổng hợp số liệu tháng hiện tại. ¶ 2. Chủ trọ chọn tháng hoặc khoảng thời gian khác; hệ thống tính lại. ¶ 3. Hệ thống hiển thị thực thu, khoản chi, doanh thu, chênh lệch, công nợ, số phòng theo trạng thái; tiền cọc đang giữ theo dõi riêng; cọc giữ lại khi hủy phiếu là doanh thu khác; khoản cấn trừ cọc không tính là khoản thu mới. ¶ Rẽ nhánh 1: 3.1 Không có dữ liệu → Các chỉ số hiển thị 0.

===== MỤC 3.2.1.17 =====
TIÊU ĐỀ: Quản lý thông báo
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Usecase quản lý thông báo]]
Loại: Sơ đồ use case UML; khung hệ thống ghi “Ứng dụng quản lý nhà trọ”; tác nhân là hình người que đặt ngoài khung.
Tác nhân: Chủ trọ, Khách thuê
Use case chính (hình elip ở giữa khung): Quản lý thông báo
Use case mở rộng (hình elip, mỗi elip nối đến use case chính bằng mũi tên nét đứt hướng về use case chính, nhãn «extend»): Gửi thông báo chung; Xem thông báo
Liên kết: mỗi tác nhân nối với use case chính bằng đường liền không mũi tên.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Usecase quản lý thông báo
BẢNG ĐẶC TẢ:
[Tên use case] Usecase Quản lý thông báo
[Tác nhân] Chủ trọ, Khách thuê
[Mô tả] Chủ trọ gửi thông báo chung của nhà trọ; Chủ trọ và Khách thuê nhận, xem và tra cứu lại thông báo về phiếu báo phí, thanh toán, sự cố và hợp đồng.
[Điều kiện tiên quyết] Người dùng đã đăng nhập.
[Điều kiện hậu quyết] Thành công: Thông báo được lưu trong ứng dụng cho từng người nhận và chuyển đến thiết bị nếu được. ¶ Thất bại: Dữ liệu không hợp lệ hoặc không có người nhận, hệ thống hiển thị lỗi.
[Luồng sự kiện chính] 1. Người dùng vào mục “Thông báo” hoặc chạm vào thông báo trên thiết bị. ¶ 2. Hệ thống hiển thị danh sách thông báo của tài khoản. ¶ 3. Hệ thống hiển thị các chức năng: ¶ Extend use case: Gửi thông báo chung ¶ Extend use case: Xem thông báo
[Luồng sự kiện phụ] Chuyển thông báo đến thiết bị không thành công: nội dung vẫn được lưu trong ứng dụng.
[Extend use case] Gửi thông báo chung ¶ 1. Chủ trọ chọn “Tạo thông báo”, nhập tiêu đề, nội dung, chọn toàn bộ khách đang thuê hoặc một số phòng. ¶ 2. Hệ thống kiểm tra dữ liệu và người nhận. ¶ 3. Hệ thống lưu thông báo cho từng người nhận và yêu cầu dịch vụ thông báo chuyển đến thiết bị. ¶ Rẽ nhánh 1: 2.1 Thiếu tiêu đề, nội dung hoặc không có người nhận → Hiển thị lỗi.
[Extend use case] Xem thông báo ¶ 1. Hệ thống hiển thị danh sách thông báo mới nhất trước, kèm dấu chưa đọc. ¶ 2. Người dùng chọn một thông báo; hệ thống đánh dấu đã đọc và hiển thị nội dung. ¶ 3. Thông báo gắn với đối tượng: hệ thống kiểm tra quyền rồi chuyển đến màn hình tương ứng. ¶ Rẽ nhánh 1: 3.1 Không còn quyền với đối tượng → Chỉ hiển thị nội dung thông báo.

KIỂM TRA SAU KHI LÀM (báo lại kết quả từng dòng):
1. Không còn nội dung "Quản lý hồ sơ và điểm uy tín", "vị trí GPS", "điểm uy tín" trong mục 3.2.1.
2. Mục 3.2.1 có một đoạn văn và đúng 17 mục con 3.2.1.1 đến 3.2.1.17; mỗi mục có một khối mô tả sơ đồ, một chú thích hình và một bảng đặc tả.
3. Tổng số hàng "Extend use case" trong 17 bảng là 51.
4. Không còn ký hiệu "¶" trong tài liệu.
5. Sau khi cập nhật toàn bộ trường (Ctrl+A rồi F9), chú thích của 17 sơ đồ use case là Hình 3-3 đến Hình 3-19. Cập nhật Mục lục và Mục lục các hình vẽ.
