PROMPT 12 – MỤC 3.3, 3.4 VÀ CHƯƠNG 4 (dán toàn bộ nội dung dưới đây cho AI Word; chỉ dùng sau khi đã chạy xong Prompt 11)

VAI TRÒ: Bạn là người triển khai nội dung vào tài liệu LVTN.docx. Toàn bộ nội dung dưới đây đã được phân tích và chốt. Bạn chèn đúng nguyên văn từng chữ. Không tự viết thêm, không diễn đạt lại, không rút gọn, không suy luận, không sửa phần khác của tài liệu.

PHẠM VI: Từ tiêu đề "3.3 KIẾN TRÚC BẢO MẬT VÀ TOÀN VẸN DỮ LIỆU" đến trước tiêu đề "Chương 5. KẾT LUẬN". Không sửa Chương 5 trở đi.

ĐỊNH DẠNG CHUNG:
- Tiêu đề cấp 3 mới (3.3.3, 3.3.4, 4.1.2 trở đi): dùng đúng kiểu và cách đánh số tự động của tiêu đề "3.3.1 Phân quyền và kiểm soát truy cập theo vai trò" (với mục 3.3) và "4.1.1 Thử nghiệm đăng nhập và quản lý hồ sơ" (với mục 4.1).
- Đoạn văn và gạch đầu dòng: dùng đúng định dạng đoạn văn và gạch đầu dòng đang có của tài liệu. Dòng bắt đầu bằng "- " là một gạch đầu dòng; phần chữ in đậm đặt trong dấu ** ** (chỉ in đậm, không ghi dấu **).
- Bảng kịch bản thử nghiệm: dùng đúng mẫu bảng 6 cột đang có ở mục 4.1.1 ("Test Case | Mô tả | Các bước thực hiện | Kết quả mong đợi | Kết quả thực tế | Trạng thái"). Mỗi dòng dữ liệu dưới đây gồm 4 ô ngăn cách bằng " || " ứng với 4 cột đầu; hai cột "Kết quả thực tế" và "Trạng thái" để TRỐNG. Trong cột "Các bước thực hiện", mỗi bước "B1.", "B2."... xuống dòng trong cùng ô.
- Chú thích hình ở mục 3.4: tạo bằng cơ chế chú thích có trường đánh số tự động, đúng kiểu chú thích hình đang có; ngay trên mỗi chú thích chèn một đoạn trống căn giữa làm chỗ để ảnh màn hình.

===== VIỆC 1: MỤC 3.3.1 =====
Dưới tiêu đề "3.3.1 Phân quyền và kiểm soát truy cập theo vai trò" (hiện đang trống), chèn:
- **Xác thực bằng mã truy cập:** Sau khi đăng nhập, máy chủ cấp mã truy cập JWT thời hạn ngắn và mã làm mới lưu dạng băm trong bảng sessions. Mọi API, trừ đăng ký, đăng nhập, khôi phục mật khẩu và điểm tiếp nhận thông báo giao dịch, đều đi qua middleware xác thực; mã hết hạn hoặc phiên đã đăng xuất bị từ chối với mã lỗi 401.
- **Phân quyền theo vai trò đã chọn:** Một tài khoản có thể có cả hai vai trò nhưng mỗi phiên chỉ hoạt động theo vai trò đã chọn khi đăng nhập. Nhóm API của Chủ trọ chỉ chấp nhận phiên có vai trò Chủ trọ; nhóm API của Khách thuê chỉ chấp nhận phiên có vai trò Khách thuê.
- **Cách ly dữ liệu giữa các nhà trọ:** Máy chủ không tin mã nhà trọ do ứng dụng gửi lên mà tự xác định nhà trọ từ tài khoản Chủ trọ đang đăng nhập. Mọi truy vấn đọc, ghi trên các bảng có cột house_id đều kèm điều kiện house_id của nhà trọ đó; yêu cầu đến bản ghi của nhà trọ khác bị từ chối với mã lỗi 403.
- **Phạm vi dữ liệu của Khách thuê:** Khách thuê chỉ truy cập được hợp đồng mà tài khoản là thành viên và các dữ liệu thuộc hợp đồng đó như phiếu báo phí, chỉ số, thanh toán, sự cố. Thành viên đã rời hợp đồng chỉ xem được lịch sử trong thời gian còn là thành viên. Khách thuê không có quyền sửa chỉ số, xác nhận tiền mặt hay quyết định chi phí sửa chữa.
- **Kiểm tra quyền ở máy chủ, không dựa vào giao diện:** Việc ẩn nút trên ứng dụng chỉ phục vụ trải nghiệm; quyền thực hiện luôn được kiểm tra lại tại máy chủ cho từng yêu cầu.

===== VIỆC 2: MỤC 3.3.2 =====
Dưới tiêu đề "3.3.2 Bảo mật định danh và bảo vệ dữ liệu" (hiện đang trống), chèn:
- **Băm mật khẩu một chiều:** Mật khẩu được băm bằng thuật toán bcrypt trước khi lưu; hệ thống không lưu và không ghi nhật ký mật khẩu ở dạng rõ. Mật khẩu ban đầu của tài khoản Khách thuê chỉ xuất hiện một lần trong phản hồi tạo tài khoản cho Chủ trọ.
- **Mã OTP có thời hạn và giới hạn số lần thử:** Mã OTP gồm 6 chữ số, chỉ lưu dạng băm, hết hiệu lực sau 5 phút, bị vô hiệu sau 5 lần nhập sai và chỉ dùng được một lần. Thông tin khôi phục chưa xác minh không được dùng để khôi phục mật khẩu.
- **Xác thực lại với thao tác nhạy cảm:** Thay đổi thông tin khôi phục, tài khoản ngân hàng nhận tiền và kết nối dịch vụ thông báo biến động số dư yêu cầu nhập lại mật khẩu hiện tại.
- **Bảo vệ đường truyền và khóa bí mật:** Ứng dụng và máy chủ giao tiếp qua HTTPS. Khóa bí mật ký JWT, thông tin kết nối cơ sở dữ liệu và khóa của các dịch vụ bên ngoài được đặt trong biến môi trường, không đưa vào mã nguồn.
- **Xác thực thông báo giao dịch ngân hàng:** Mỗi nhà trọ có địa chỉ tiếp nhận và khóa xác thực riêng; khóa chỉ lưu dạng băm. Thông báo không mang đúng khóa bị từ chối và không được xử lý. Ứng dụng không lưu thông tin đăng nhập ngân hàng và không truy cập tài khoản ngân hàng của Chủ trọ.
- **Kiểm soát tệp tải lên:** Chỉ chấp nhận tệp ảnh định dạng JPEG hoặc PNG có dung lượng giới hạn; tệp được lưu với tên do máy chủ sinh ngẫu nhiên và chỉ được tải về sau khi kiểm tra quyền theo nhà trọ hoặc hợp đồng.

===== VIỆC 3: THÊM MỤC 3.3.3 VÀ 3.3.4 =====
Ngay sau nội dung mục 3.3.2 và TRƯỚC tiêu đề "3.4 HỆ THỐNG MÀN HÌNH", chèn hai tiêu đề cấp 3 mới cùng nội dung:

TIÊU ĐỀ: Toàn vẹn giao dịch thanh toán
- **Giao dịch cơ sở dữ liệu:** Các thao tác ghi nhận khoản thu, phân bổ vào phần phải trả, cập nhật công nợ và trạng thái yêu cầu thanh toán được thực hiện trong một giao dịch cơ sở dữ liệu của InnoDB thông qua Prisma; nếu một bước lỗi, toàn bộ thao tác được hoàn tác.
- **Chống ghi nhận trùng:** Cặp (house_id, provider_txn_id) của bảng bank_transactions là duy nhất nên một giao dịch ngân hàng gửi lặp chỉ được lưu một lần. Cột bank_transaction_id và payment_request_id của bảng payments là duy nhất nên một giao dịch ngân hàng hoặc một yêu cầu thanh toán chỉ tạo tối đa một khoản thu, kể cả khi Chủ trọ xác nhận thủ công cùng lúc với lần tự động xác nhận. Khi thông báo giao dịch đến sau một khoản đã được Chủ trọ xác nhận thủ công và khớp tài khoản nhận, số tiền, thời điểm, mã tham chiếu, hệ thống không tự tạo khoản thu mà chuyển giao dịch sang danh sách cần đối chiếu; các lần chuyển tiền độc lập không bị coi là trùng chỉ vì cùng thuộc một phiếu.
- **Điều kiện tự động xác nhận chặt chẽ:** Hệ thống chỉ tự xác nhận khi khớp đồng thời tài khoản nhận, mã tham chiếu, thời điểm ngân hàng ghi nhận trong thời hạn yêu cầu, số tiền chính xác và nghĩa vụ còn đủ số dư; các trường hợp khác được chuyển sang đối chiếu thủ công, không suy đoán theo nội dung gần giống.
- **Khóa phiếu đã có thanh toán:** Phiếu báo phí đã phát hành chỉ được chỉnh sửa khi chưa có khoản thanh toán nào được xác nhận; khi chỉnh sửa, các yêu cầu VietQR đang chờ theo số tiền cũ bị vô hiệu. Phiếu đã có thanh toán được xác nhận không được sửa hoặc hủy; sai lệch được ghi thành khoản điều chỉnh riêng trong bảng invoice_adjustments, liên kết với phiếu gốc.
- **Tính toán tiền bằng số nguyên:** Mọi số tiền lưu theo đơn vị đồng bằng kiểu số nguyên; kỳ thuê lẻ chỉ làm tròn một lần đến 1.000 đồng; phần dư khi chia đều được cộng từng đồng theo thứ tự danh sách nên tổng các phần phải trả luôn bằng tổng phiếu.

TIÊU ĐỀ: Truy vết thay đổi và sao lưu dữ liệu
- **Không ghi đè dữ liệu lịch sử:** Mức phí dịch vụ và trạng thái áp dụng dịch vụ được lưu thành bản ghi mới theo ngày hiệu lực; phiếu đã phát hành không bị tính lại khi cấu hình thay đổi.
- **Nhật ký thay đổi:** Mọi điều chỉnh chỉ số đã chốt, chỉnh sửa phiếu đã phát hành chưa có thanh toán, gia hạn phiếu giữ phòng, thay đổi hợp đồng và xử lý khoản trả dư đều được ghi vào bảng audit_logs với người thực hiện, thời điểm, giá trị trước, giá trị sau và lý do. Không có API nào cho phép sửa hoặc xóa bảng này.
- **Không xóa lịch sử gốc:** Khoản điều chỉnh của phiếu đã có thanh toán, biên bản trả phòng được Chủ trọ hoàn tất khi Khách thuê chưa xác nhận và kết quả quyết toán đều được lưu thành bản ghi riêng có người thực hiện và thời điểm, không ghi đè dữ liệu gốc.
- **Sao lưu định kỳ:** Cơ sở dữ liệu được sao lưu tự động tối thiểu mỗi 24 giờ bằng công cụ mysqldump cùng thư mục lưu tệp; mục tiêu thiết kế là thời điểm khôi phục không quá 24 giờ và thời gian khôi phục không quá 8 giờ. Việc khôi phục thử được ghi nhận ở Chương 4.

===== VIỆC 4: MỤC 3.4 HỆ THỐNG MÀN HÌNH =====
1. XÓA dòng chữ "Mota" và chú thích "Giao diện giới thiệu" đang có trong mục 3.4.
2. CHÈN ngay dưới tiêu đề "3.4 HỆ THỐNG MÀN HÌNH" đoạn văn sau:
Giao diện ứng dụng được thiết kế cho màn hình điện thoại theo hướng đơn giản, mỗi màn hình phục vụ một nhiệm vụ chính. Sau màn hình chào, người dùng chọn vai trò Chủ trọ hoặc Khách thuê; mỗi vai trò có thanh điều hướng dưới cùng riêng. Giao diện Chủ trọ tập trung vào phòng, hợp đồng, chỉ số, phiếu báo phí và công nợ; giao diện Khách thuê tập trung vào phiếu báo phí cần thanh toán, lịch sử thanh toán, sự cố và thông báo. Các số tiền được hiển thị phân biệt rõ số phải trả, số đã trả và số còn thiếu; trạng thái phòng, phiếu và giao dịch được thể hiện bằng nhãn chữ để người dùng không phải đoán theo màu sắc.
3. Sau đoạn văn, chèn lần lượt các chú thích hình sau (mỗi chú thích có một đoạn trống căn giữa ngay phía trên để chèn ảnh):
CHÚ THÍCH HÌNH: Giao diện màn hình chào và chọn vai trò
CHÚ THÍCH HÌNH: Giao diện đăng nhập
CHÚ THÍCH HÌNH: Giao diện đăng ký tài khoản Chủ trọ và xác minh OTP
CHÚ THÍCH HÌNH: Giao diện trang chủ của Chủ trọ
CHÚ THÍCH HÌNH: Giao diện danh sách phòng theo trạng thái
CHÚ THÍCH HÌNH: Giao diện thêm phòng
CHÚ THÍCH HÌNH: Giao diện khai báo dịch vụ và đơn giá
CHÚ THÍCH HÌNH: Giao diện lập phiếu giữ phòng
CHÚ THÍCH HÌNH: Giao diện lập hợp đồng
CHÚ THÍCH HÌNH: Giao diện ghi nhận và chốt chỉ số điện nước
CHÚ THÍCH HÌNH: Giao diện chi tiết phiếu báo phí của Chủ trọ
CHÚ THÍCH HÌNH: Giao diện theo dõi công nợ
CHÚ THÍCH HÌNH: Giao diện giao dịch cần đối chiếu
CHÚ THÍCH HÌNH: Giao diện quản lý sự cố
CHÚ THÍCH HÌNH: Giao diện thống kê
CHÚ THÍCH HÌNH: Giao diện trang chủ của Khách thuê
CHÚ THÍCH HÌNH: Giao diện phiếu báo phí của Khách thuê
CHÚ THÍCH HÌNH: Giao diện thanh toán VietQR
CHÚ THÍCH HÌNH: Giao diện thông báo
CHÚ THÍCH HÌNH: Giao diện mục “Tôi”

===== VIỆC 5: CHƯƠNG 4 – MỤC 4.1 =====
1. CHÈN ngay dưới tiêu đề "4.1 CÁC KỊCH BẢN THỬ NGHIỆM" đoạn văn sau:
Các kịch bản thử nghiệm được xây dựng từ các chức năng mở rộng ở mục 3.2.1 và các quy tắc nghiệp vụ đã xác định, tập trung vào những điểm dễ sai: tính tiền kỳ lẻ, chia đều nghĩa vụ, cấn trừ tiền cọc, xác nhận thanh toán, cách ly dữ liệu giữa các nhà trọ và chống ghi nhận trùng giao dịch. Thử nghiệm được thực hiện trên bản dựng ứng dụng chạy trên điện thoại Android, máy chủ Node.js và cơ sở dữ liệu MySQL với dữ liệu mẫu. Dịch vụ SMS OTP chạy ở chế độ thử nghiệm; thông báo giao dịch ngân hàng được mô phỏng bằng cách gửi yêu cầu đúng định dạng của dịch vụ thông báo biến động số dư đến địa chỉ tiếp nhận. Cột “Kết quả thực tế” và “Trạng thái” được ghi sau khi thực hiện từng kịch bản.
2. ĐỔI tên tiêu đề "4.1.1 Thử nghiệm đăng nhập và quản lý hồ sơ" thành "Thử nghiệm tài khoản và xác thực" (giữ số mục tự động).
3. Trong bảng của mục 4.1.1: GIỮ dòng tiêu đề cột, XÓA dòng dữ liệu "1 | Đăng nhập thành công với tài khoản hợp lệ. | B1. Truy cập trang đăng nhập. B2. Nhập email hợp lệ..." (dòng ví dụ của đề tài khác), rồi thêm các dòng của mục 4.1.1 dưới đây.
4. Sau bảng của mục 4.1.1, chèn lần lượt các mục 4.1.2 đến 4.1.14, mỗi mục gồm tiêu đề và một bảng 6 cột theo đúng mẫu bảng của mục 4.1.1.

--- MỤC 4.1.1: Thử nghiệm tài khoản và xác thực ---
1 || Đăng ký tài khoản Chủ trọ thành công. || B1. Chọn vai trò Chủ trọ, chọn “Đăng ký”. B2. Nhập số điện thoại chưa đăng ký, mật khẩu hợp lệ, xác nhận mật khẩu. B3. Nhập đúng mã OTP. || Tài khoản được tạo với vai trò Chủ trọ, ứng dụng chuyển đến màn hình thiết lập nhà trọ.
2 || Đăng ký với số điện thoại đã tồn tại. || B1. Chọn “Đăng ký”. B2. Nhập số điện thoại đã có tài khoản. B3. Chọn “Đăng ký”. || Hệ thống không gửi OTP, thông báo số điện thoại đã được đăng ký và hướng dẫn đăng nhập.
3 || Nhập sai mã OTP quá 5 lần. || B1. Thực hiện đăng ký đến bước nhập OTP. B2. Nhập sai mã 5 lần. B3. Nhập mã đúng. || Sau lần sai thứ 5, mã bị vô hiệu; lần nhập mã đúng vẫn bị từ chối, người dùng phải yêu cầu gửi mã mới.
4 || Đăng nhập sai mật khẩu. || B1. Nhập số điện thoại đã đăng ký và mật khẩu sai. B2. Chọn “Đăng nhập”. || Hệ thống thông báo thông tin đăng nhập không đúng, không tạo phiên đăng nhập.
5 || Lần đăng nhập đầu của tài khoản Khách thuê mới. || B1. Đăng nhập bằng số điện thoại và mật khẩu ban đầu do Chủ trọ chia sẻ. B2. Nhập mã OTP gửi qua SMS. || Hệ thống yêu cầu xác minh số điện thoại trước khi vào giao diện Khách thuê; sau khi xác minh, người dùng vào được giao diện Khách thuê.
6 || Tài khoản có cả hai vai trò đăng nhập theo vai trò đã chọn. || B1. Chọn vai trò Khách thuê trên màn hình chào. B2. Đăng nhập bằng tài khoản vừa là Chủ trọ vừa là Khách thuê. || Ứng dụng mở giao diện Khách thuê; các API của Chủ trọ gọi từ phiên này bị từ chối.
7 || Quên mật khẩu qua thư điện tử đã xác minh. || B1. Chọn “Quên mật khẩu”, nhập số điện thoại chính. B2. Chọn thư điện tử đã xác minh. B3. Nhập mã OTP nhận được và mật khẩu mới. || Mật khẩu được cập nhật; đăng nhập bằng mật khẩu mới thành công, mật khẩu cũ bị từ chối.
8 || Thêm thông tin khôi phục vượt giới hạn. || B1. Tài khoản đã có hai thư điện tử khôi phục. B2. Thêm thư điện tử thứ ba và nhập đúng mật khẩu. || Hệ thống từ chối và thông báo vượt giới hạn hai địa chỉ thư điện tử.

--- MỤC 4.1.2: Thử nghiệm quản lý nhà trọ và phòng ---
1 || Tạo nhà trọ thứ hai trên cùng tài khoản. || B1. Tài khoản Chủ trọ đã có nhà trọ. B2. Gọi chức năng tạo nhà trọ mới. || Hệ thống mở thông tin nhà trọ hiện có để cập nhật, không tạo nhà trọ thứ hai.
2 || Nhập ngày lập phiếu không hợp lệ. || B1. Vào “Thông tin nhà trọ”. B2. Nhập ngày dự kiến lập phiếu là 29. B3. Chọn “Lưu”. || Hệ thống báo lỗi ngày lập phiếu phải từ 1 đến 28, không lưu.
3 || Thêm nhiều phòng giống nhau. || B1. Chọn “Thêm phòng”. B2. Nhập tên gốc “Phòng”, giá thuê 3.000.000, số lượng 10. B3. Chọn “Lưu”. || Hệ thống tạo 10 phòng từ “Phòng 1” đến “Phòng 10”, cùng giá thuê, trạng thái Trống.
4 || Thêm phòng có tên trùng. || B1. Nhà trọ đã có “Phòng 3”. B2. Thêm tên gốc “Phòng”, số lượng 5. || Hệ thống báo “Phòng 3” bị trùng và không lưu phòng nào.
5 || Tạm ngừng phòng đang thuê. || B1. Chọn phòng có trạng thái Đang thuê. B2. Chọn “Tạm ngừng sử dụng”. || Hệ thống từ chối và nêu lý do phòng đang có hợp đồng còn hiệu lực.
6 || Xóa nhóm phòng còn phòng. || B1. Vào “Nhóm phòng”. B2. Chọn xóa nhóm đang chứa phòng. || Hệ thống từ chối và yêu cầu chuyển các phòng sang nhóm khác trước.

--- MỤC 4.1.3: Thử nghiệm dịch vụ và đơn giá ---
1 || Khai báo dịch vụ điện tính theo người. || B1. Chọn “Thêm dịch vụ”, loại Điện. B2. Chọn phương pháp tính theo người. B3. Chọn “Lưu”. || Hệ thống báo phương pháp tính không phù hợp với loại khoản phí, không lưu.
2 || Cập nhật đơn giá điện có ngày hiệu lực. || B1. Đơn giá điện đang là 3.500 đồng/kWh. B2. Cập nhật đơn giá 4.000 đồng/kWh, hiệu lực từ ngày 01 tháng sau. B3. Mở lịch sử thay đổi. || Lịch sử có hai mức phí với hai ngày hiệu lực; phiếu của tháng hiện tại vẫn dùng 3.500 đồng/kWh.
3 || Thay đổi đơn giá không ảnh hưởng phiếu đã phát hành. || B1. Phát hành phiếu tháng hiện tại. B2. Cập nhật đơn giá dịch vụ có hiệu lực từ đầu tháng hiện tại. B3. Mở lại phiếu đã phát hành. || Số tiền trên phiếu đã phát hành không thay đổi.

--- MỤC 4.1.4: Thử nghiệm giữ phòng và tiền cọc ---
1 || Lập phiếu giữ phòng thành công. || B1. Chọn phòng Trống, chọn “Giữ phòng”. B2. Nhập thông tin người giữ, ngày nhận dự kiến, thời hạn, tiền cọc 1.000.000. || Phiếu được tạo với tiền cọc chưa nhận; phòng chuyển sang Đã giữ chỗ.
2 || Tiền cọc giữ phòng vượt giá thuê một tháng. || B1. Chọn phòng Trống có giá thuê 3.000.000. B2. Lập phiếu giữ phòng với tiền cọc 3.500.000. || Hệ thống báo lỗi tiền cọc không được vượt giá thuê một tháng đã thỏa thuận, không tạo phiếu.
3 || Lập phiếu thứ hai cho phòng đã có phiếu chưa xử lý. || B1. Chọn phòng đang có phiếu giữ phòng chưa xử lý. B2. Lập phiếu giữ phòng mới. || Hệ thống từ chối và nêu nguyên nhân phòng đã có phiếu giữ phòng chưa xử lý.
4 || Phiếu giữ phòng quá hạn. || B1. Để phiếu qua thời hạn giữ mà chưa lập hợp đồng. B2. Mở danh sách phiếu. || Phiếu chuyển sang trạng thái quá hạn, Chủ trọ nhận thông báo; phiếu không tự hủy, tiền cọc không tự bị xử lý.
5 || Hủy phiếu và hoàn một phần tiền cọc. || B1. Phiếu có tiền cọc thực nhận 1.000.000. B2. Chọn “Hủy phiếu”, hoàn 600.000, nhập lý do. || Phiếu chuyển sang đã hủy; 400.000 được ghi nhận là doanh thu khác; phòng trở về Trống nếu không còn phiếu hoặc hợp đồng khác.
6 || Tiền cọc giữ phòng không được tính vào doanh thu. || B1. Xác nhận đã nhận cọc 1.000.000. B2. Mở “Thống kê” tháng hiện tại. || Doanh thu không tăng; chỉ số tiền cọc đang giữ tăng 1.000.000.

--- MỤC 4.1.5: Thử nghiệm hợp đồng và thành viên ---
1 || Lập hợp đồng từ phiếu giữ phòng. || B1. Mở phiếu có cọc thực nhận 1.000.000, chọn “Lập hợp đồng”. B2. Nhập thông tin hợp đồng, một người đứng tên, tiền cọc bảo đảm 3.000.000. B3. Chọn “Lưu”. || Hợp đồng được lưu; phiếu chuyển sang đã lập hợp đồng; phòng chuyển sang Đang thuê; cọc bảo đảm 3.000.000 được ghi nhận riêng.
2 || Cọc giữ phòng lớn hơn tiền thuê kỳ đầu. || B1. Phiếu giữ phòng có cọc thực nhận 3.000.000, giá thuê 3.000.000. B2. Lập hợp đồng bắt đầu ngày 21, kỳ đầu tính 10 ngày. B3. Lập phiếu tháng đầu. || Tiền thuê kỳ đầu 1.000.000 được cấn trừ đủ 1.000.000, phiếu không có tiền thuê âm; 2.000.000 được ghi là khoản Chủ trọ cần hoàn cho người đặt cọc, tách khỏi phiếu.
3 || Hợp đồng có hai người đứng tên. || B1. Lập hợp đồng. B2. Đánh dấu hai thành viên là người đứng tên. B3. Chọn “Lưu”. || Hệ thống báo hợp đồng phải có đúng một người đứng tên, không lưu.
4 || Thành viên có số điện thoại đã có tài khoản. || B1. Thêm thành viên có số điện thoại của một tài khoản Chủ trọ khác. B2. Lưu hợp đồng. || Hệ thống liên kết tài khoản hiện có, bổ sung vai trò Khách thuê, không tạo tài khoản trùng và không đổi mật khẩu.
5 || Thành viên không có số điện thoại. || B1. Thêm thành viên chỉ có họ tên. B2. Lưu hợp đồng. || Thành viên được ghi nhận là người cư trú, không tạo tài khoản.
6 || Nhập hợp đồng đang thuê có công nợ đầu kỳ. || B1. Chọn phòng Trống, chọn “Nhập hợp đồng đang thuê”. B2. Nhập công nợ đầu kỳ 500.000, tiền cọc đang giữ 2.000.000, chỉ số ban đầu. || Hợp đồng được lưu; phiếu báo phí đầu tiên có khoản công nợ đầu kỳ 500.000; không có khoản cấn trừ cọc giữ phòng.

--- MỤC 4.1.6: Thử nghiệm bàn giao và chỉ số điện nước ---
1 || Chỉ số trong biên bản nhận phòng làm chỉ số ban đầu. || B1. Lập biên bản nhận phòng với chỉ số điện 1.200. B2. Khách thuê xác nhận. B3. Chốt chỉ số điện kỳ đầu là 1.300 và lập phiếu. || Tiền điện kỳ đầu tính theo 100 kWh.
2 || Chỉ số mới nhỏ hơn chỉ số cũ. || B1. Chỉ số đã chốt kỳ trước là 1.300. B2. Nhập chỉ số kỳ này 1.250, chọn “Chốt chỉ số”. || Hệ thống từ chối và yêu cầu kiểm tra lại.
3 || Cảnh báo tiêu thụ bất thường. || B1. Ba kỳ trước tiêu thụ khoảng 100 kWh. B2. Nhập chỉ số cho mức tiêu thụ 600 kWh. || Hệ thống hiển thị cảnh báo; Chủ trọ có thể nhập lại hoặc xác nhận tiếp tục, khi tiếp tục chỉ số được đánh dấu bất thường.
4 || Tính tiêu thụ khi thay công tơ. || B1. Chỉ số đã chốt kỳ trước 1.300. B2. Ghi nhận thay công tơ: chỉ số cuối công tơ cũ 1.350, chỉ số đầu công tơ mới 0. B3. Chốt cuối kỳ công tơ mới 40. || Lượng tiêu thụ của kỳ là 90 kWh (50 của công tơ cũ và 40 của công tơ mới).
5 || Khách thuê không sửa được chỉ số; Chủ trọ điều chỉnh có lưu lịch sử. || B1. Khách thuê thử gọi chức năng sửa chỉ số. B2. Khách thuê gửi phản hồi. B3. Chủ trọ điều chỉnh chỉ số kèm lý do. || Bước 1 bị từ chối; sau bước 3 chỉ số mới được lưu, nhật ký thay đổi có người thực hiện, thời điểm, giá trị trước, giá trị sau và lý do.

--- MỤC 4.1.7: Thử nghiệm tính phí và phiếu báo phí ---
1 || Tiền phòng tháng đầy đủ. || B1. Hợp đồng giá thuê 3.500.000, thuê trọn tháng. B2. Lập phiếu. || Khoản tiền phòng bằng 3.500.000 (100% giá thuê tháng).
2 || Tiền phòng kỳ lẻ 10 ngày. || B1. Hợp đồng giá thuê 3.500.000, kỳ đầu tính 10 ngày. B2. Lập phiếu. || Khoản tiền phòng bằng 1.167.000 (10 × 3.500.000 / 30 = 1.166.666,67, làm tròn một lần đến 1.000 đồng).
3 || Cấn trừ cọc giữ phòng một lần. || B1. Hợp đồng lập từ phiếu có cọc thực nhận 1.000.000. B2. Lập phiếu tháng đầu. B3. Lập phiếu tháng thứ hai. || Phiếu tháng đầu có khoản cấn trừ −1.000.000; phiếu tháng thứ hai không có khoản cấn trừ.
4 || Chia đều có phần dư. || B1. Hợp đồng chế độ chia đều, ba thành viên chịu trách nhiệm thanh toán. B2. Phiếu có tổng 1.000.001. || Ba phần phải trả lần lượt là 333.334, 333.334, 333.333; tổng bằng 1.000.001.
5 || Phát hành phiếu thiếu chỉ số. || B1. Phiếu nháp có khoản điện theo công tơ chưa có chỉ số chốt. B2. Chọn “Phát hành”. || Hệ thống từ chối, chỉ rõ khoản điện còn thiếu; phiếu giữ trạng thái nháp.
6 || Hạn thanh toán khi phát hành muộn. || B1. Số ngày cho phép thanh toán là 5; ngày dự kiến lập phiếu là ngày 5. B2. Phát hành phiếu vào ngày 10. || Hạn thanh toán là ngày 15 (ngày phát hành thực tế cộng 5 ngày).
7 || Chỉnh sửa phiếu đã phát hành chưa có thanh toán. || B1. Phiếu đã phát hành, chưa có thanh toán được xác nhận, Khách thuê đã tạo một yêu cầu VietQR đang chờ. B2. Chủ trọ chọn “Chỉnh sửa”, giảm khoản dịch vụ 50.000, nhập lý do. || Phiếu được cập nhật trên cùng mã phiếu, giữ hạn thanh toán, có dấu “Đã điều chỉnh” và lịch sử trước, sau; yêu cầu VietQR đang chờ bị vô hiệu.
8 || Phiếu đã có thanh toán không được sửa hoặc hủy. || B1. Phiếu đã phát hành có một khoản thanh toán đã xác nhận. B2. Chọn “Chỉnh sửa”. B3. Chọn “Ghi nhận điều chỉnh”, chọn giảm 100.000, xử lý bù trừ kỳ sau, nhập lý do. B4. Lập phiếu kỳ sau. || Bước 2 bị từ chối; phiếu gốc và giao dịch đã xác nhận giữ nguyên; khoản điều chỉnh được lưu riêng liên kết với phiếu gốc; phiếu kỳ sau có khoản điều chỉnh −100.000.
9 || Miễn phí dịch vụ trên phiếu nháp không cần lý do. || B1. Mở phiếu nháp. B2. Nhập 0 đồng cho khoản dịch vụ rác, không nhập lý do. B3. Chọn “Lưu”. || Hệ thống chấp nhận, lưu cả mức phí mặc định và số tiền 0 đồng, tính lại tổng và phân bổ lại.

--- MỤC 4.1.8: Thử nghiệm thanh toán VietQR và xác nhận thủ công ---
1 || Tạo yêu cầu vượt số dư. || B1. Phần phải trả còn 1.200.000. B2. Tạo yêu cầu thanh toán 1.500.000. || Hệ thống từ chối vì số tiền vượt số dư còn phải trả.
2 || Yêu cầu thanh toán hết hạn. || B1. Tạo yêu cầu thanh toán. B2. Chờ hơn 15 phút, không chuyển khoản. || Yêu cầu chuyển sang Hết hạn; Khách thuê tạo được yêu cầu mới với mã tham chiếu khác.
3 || Báo chuyển khoản không làm giảm công nợ. || B1. Khách thuê chọn “Tôi đã chuyển” và đính kèm ảnh. B2. Xem công nợ của phiếu. || Báo chuyển khoản ở trạng thái chờ xác nhận; số còn thiếu không đổi.
4 || Chủ trọ xác nhận báo chuyển khoản. || B1. Chủ trọ mở báo chuyển khoản, chọn “Xác nhận”. B2. Xem công nợ. || Khoản thu được ghi nhận; số đã trả tăng và số còn thiếu giảm đúng số tiền; Khách thuê nhận thông báo.
5 || Chủ trọ từ chối báo chuyển khoản. || B1. Chủ trọ chọn “Từ chối”, nhập lý do. || Công nợ giữ nguyên; Khách thuê nhận thông báo kèm lý do.
6 || Thu tiền mặt một phần và trả dư. || B1. Phần phải trả còn 1.000.000. B2. Chủ trọ thu tiền mặt 600.000. B3. Thu tiếp 500.000. || Sau bước 2 còn thiếu 400.000; sau bước 3 phần phải trả đã trả đủ và 100.000 được ghi là khoản trả dư của người trả.

--- MỤC 4.1.9: Thử nghiệm tự động đối chiếu giao dịch ngân hàng ---
1 || Thông báo hợp lệ được tự động xác nhận. || B1. Tạo yêu cầu thanh toán 1.200.000. B2. Gửi thông báo giao dịch đúng khóa, đúng tài khoản, nội dung chứa mã tham chiếu, số tiền 1.200.000, thời điểm trong thời hạn. || Khoản thu được ghi nhận tự động; yêu cầu chuyển sang Đã thanh toán; hai bên nhận thông báo.
2 || Thông báo sai khóa xác thực. || B1. Gửi thông báo giao dịch với khóa sai. || Máy chủ trả mã lỗi 401; không có bản ghi giao dịch hay khoản thu nào được tạo.
3 || Thông báo gửi lặp cùng mã giao dịch. || B1. Gửi lại đúng thông báo của kịch bản 1. || Máy chủ bỏ qua; số khoản thu và công nợ không thay đổi.
4 || Số tiền không khớp. || B1. Tạo yêu cầu 1.200.000. B2. Gửi thông báo giao dịch số tiền 1.000.000 với đúng mã tham chiếu. || Giao dịch vào danh sách cần đối chiếu kèm nguyên nhân số tiền không khớp; công nợ chưa thay đổi.
5 || Thông báo đến muộn nhưng giao dịch trong thời hạn. || B1. Tạo yêu cầu lúc 10:00 (hết hạn 10:15). B2. Gửi thông báo lúc 10:20 với thời điểm ngân hàng ghi nhận 10:10. || Giao dịch vẫn được tự động xác nhận vì thời điểm ngân hàng ghi nhận nằm trong thời hạn.
6 || Thông báo giao dịch đến sau khi Chủ trọ đã xác nhận thủ công. || B1. Chủ trọ xác nhận báo chuyển khoản 1.200.000 của một yêu cầu. B2. Gửi thông báo giao dịch có cùng tài khoản nhận, số tiền, mã tham chiếu và thời điểm. || Hệ thống không tạo khoản thu thứ hai; giao dịch vào danh sách cần đối chiếu với nguyên nhân nghi trùng khoản đã xác nhận thủ công.
7 || Đối chiếu thủ công giao dịch không khớp. || B1. Mở “Giao dịch cần đối chiếu”, chọn giao dịch ở kịch bản 4. B2. Chọn phòng, nghĩa vụ, chọn “Xác nhận”. || Khoản thu 1.000.000 được ghi nhận; giao dịch chuyển sang đã đối chiếu; xác nhận lần hai cùng giao dịch bị từ chối.

--- MỤC 4.1.10: Thử nghiệm công nợ và nhắc thanh toán ---
1 || Đánh dấu quá hạn đúng ngày. || B1. Phiếu có hạn thanh toán ngày 15, chưa trả đủ. B2. Xem công nợ vào ngày 15 và ngày 16. || Ngày 15 chưa đánh dấu quá hạn; ngày 16 khoản được đánh dấu quá hạn.
2 || Nhắc đúng người còn nghĩa vụ. || B1. Hợp đồng chia đều ba người, một người đã trả đủ. B2. Chủ trọ chọn “Nhắc thanh toán”. || Chỉ hai người còn thiếu nhận thông báo nhắc; lịch sử nhắc được lưu.
3 || Không tự tính phạt chậm trả. || B1. Để phiếu quá hạn 10 ngày. B2. Xem lại phiếu và công nợ. || Số phải trả không tăng; hợp đồng không bị tự chấm dứt.

--- MỤC 4.1.11: Thử nghiệm quản lý sự cố ---
1 || Khách thuê gửi yêu cầu sự cố. || B1. Vào “Sự cố”, chọn “Tạo yêu cầu”. B2. Nhập mô tả, chọn mức độ, đính kèm ảnh. || Yêu cầu được tạo với trạng thái Mới; Chủ trọ nhận thông báo.
2 || Chi phí sửa chữa do Khách thuê chịu. || B1. Chủ trọ tiếp nhận, nhập kết quả, chi phí 200.000, bên chịu là Khách thuê. B2. Lập phiếu kỳ tiếp theo. || Phiếu kỳ tiếp theo có khoản phát sinh 200.000; yêu cầu chuyển sang Chờ khách xác nhận.
3 || Sự cố do Chủ trọ tự tạo. || B1. Chủ trọ tạo yêu cầu sự cố cho một phòng. B2. Tiếp nhận, nhập kết quả, chọn “Hoàn tất”. || Yêu cầu chuyển thẳng sang Hoàn tất, không chờ Khách thuê xác nhận.
4 || Khách thuê phản hồi chưa khắc phục. || B1. Khách thuê mở yêu cầu Chờ khách xác nhận. B2. Chọn “Phản hồi”, nhập nội dung. || Yêu cầu trở lại Đang xử lý; Chủ trọ nhận thông báo; lịch sử xử lý có thêm phản hồi.

--- MỤC 4.1.12: Thử nghiệm gia hạn, điều chỉnh, trả phòng và quyết toán ---
1 || Gia hạn cần người đứng tên xác nhận. || B1. Chủ trọ ghi nhận gia hạn đến ngày mới. B2. Người đứng tên chưa xác nhận, xem hợp đồng. B3. Người đứng tên chọn “Xác nhận”. || Sau bước 2 ngày kết thúc chưa đổi; sau bước 3 ngày kết thúc được cập nhật và có phiên bản mới trong lịch sử.
2 || Đổi chế độ thanh toán áp dụng từ kỳ sau. || B1. Phiếu tháng hiện tại đã phát hành ở chế độ đại diện. B2. Điều chỉnh sang chế độ chia đều và được xác nhận. || Phần phải trả của phiếu đã phát hành giữ nguyên; phiếu kỳ sau được phân bổ theo chế độ chia đều.
3 || Khoản khấu trừ quyết toán thiếu lý do. || B1. Lập quyết toán, thêm khoản khấu trừ 300.000 không nhập lý do. B2. Chọn “Lưu”. || Hệ thống báo lỗi khoản khấu trừ phải có lý do.
4 || Tính kết quả quyết toán. || B1. Tiền cọc đang giữ 3.000.000, công nợ còn thiếu 500.000, khấu trừ hư hỏng 300.000 có bản chất doanh thu. B2. Lập quyết toán. B3. Chọn “Hoàn tất quyết toán”. || Kết quả là hoàn cho khách 2.200.000; 500.000 được ghi là cấn trừ từ tiền cọc cho công nợ, không tính vào tiền thực thu và không thành doanh thu mới; chỉ 300.000 được ghi nhận doanh thu; hợp đồng chuyển sang đã thanh lý; phòng chuyển về Trống.
5 || Hoàn tất biên bản trả phòng khi Khách thuê không phản hồi. || B1. Lập biên bản trả phòng, Khách thuê không xác nhận. B2. Chủ trọ chọn “Hoàn tất ghi nhận – Khách chưa xác nhận”, nhập ghi chú. B3. Chọn “Lập quyết toán”. || Biên bản lưu trạng thái Khách chưa xác nhận, chỉ số cuối kỳ được chốt; hệ thống cho lập quyết toán và hiển thị cảnh báo khoản khấu trừ chưa được hai bên thống nhất.

--- MỤC 4.1.13: Thử nghiệm thu chi, thống kê và thông báo ---
1 || Ghi nhận khoản chi khác. || B1. Vào “Thu chi”, thêm khoản chi 150.000 mua vật tư. B2. Xem thống kê tháng. || Khoản chi được lưu; tổng khoản chi trong thống kê tăng 150.000.
2 || Tiền cọc không cộng vào doanh thu. || B1. Có hợp đồng mới với cọc bảo đảm 3.000.000. B2. Xem thống kê. || Doanh thu không bao gồm 3.000.000; chỉ số tiền cọc đang giữ hiển thị riêng.
3 || Gửi thông báo chung theo phòng. || B1. Tạo thông báo chọn đối tượng là hai phòng. B2. Đăng nhập Khách thuê ở phòng khác. || Chỉ khách thuê của hai phòng được chọn nhận thông báo.
4 || Dịch vụ thông báo đẩy không khả dụng. || B1. Ngắt kết nối dịch vụ thông báo đẩy. B2. Phát hành một phiếu báo phí. B3. Khách thuê mở mục “Thông báo”. || Thông báo vẫn có trong mục “Thông báo”; trạng thái chuyển đến thiết bị ghi nhận không thành công.

--- MỤC 4.1.14: Thử nghiệm phân quyền, toàn vẹn dữ liệu và yêu cầu chất lượng ---
1 || Chủ trọ truy cập dữ liệu nhà trọ khác. || B1. Đăng nhập Chủ trọ A. B2. Gọi API xem phòng có mã thuộc nhà trọ của Chủ trọ B. || Máy chủ trả mã lỗi 403, không trả dữ liệu.
2 || Khách thuê truy cập hợp đồng không liên quan. || B1. Đăng nhập Khách thuê. B2. Gọi API xem phiếu báo phí thuộc hợp đồng khác. || Máy chủ trả mã lỗi 403, không trả dữ liệu.
3 || Lỗi giữa chừng khi ghi nhận thanh toán. || B1. Giả lập lỗi sau bước tạo khoản thu và trước bước cập nhật phần phải trả. B2. Kiểm tra cơ sở dữ liệu. || Không có khoản thu nào được lưu; số đã trả không đổi (toàn bộ thao tác được hoàn tác).
4 || Xác nhận thủ công và tự động cùng lúc. || B1. Gửi thông báo giao dịch hợp lệ và đồng thời Chủ trọ chọn “Xác nhận” trên báo chuyển khoản của cùng yêu cầu. || Chỉ một khoản thu được tạo; thao tác còn lại nhận thông báo đã ghi nhận.
5 || Mật khẩu không lưu dạng rõ. || B1. Tạo tài khoản. B2. Xem bảng users và nhật ký máy chủ. || Cột password_hash chỉ chứa giá trị băm; nhật ký không chứa mật khẩu.
6 || Thời gian phản hồi tra cứu (NFR01). || B1. Nạp dữ liệu mẫu 1.000 phòng và 10.000 phiếu. B2. Chạy 20 phiên đồng thời gọi các API tra cứu phổ biến. || Ít nhất 95% yêu cầu hoàn tất trong 3 giây.
7 || Hiển thị trên màn hình nhỏ (NFR08). || B1. Mở các màn hình đăng nhập, phiếu báo phí, thanh toán, nhập chỉ số, gửi sự cố trên điện thoại màn hình nhỏ nhất trong phạm vi hỗ trợ. || Nhãn và nút hiển thị đầy đủ, không bị che khuất, không phải cuộn ngang.
8 || Khôi phục dữ liệu từ bản sao lưu (NFR07). || B1. Sao lưu cơ sở dữ liệu và thư mục tệp. B2. Khôi phục lên máy chủ khác. B3. Đăng nhập và mở dữ liệu. || Dữ liệu được khôi phục đến thời điểm sao lưu; ghi nhận thời gian khôi phục để so với mục tiêu 8 giờ.

===== VIỆC 6: MỤC 4.2 XỬ LÝ CÁC TRƯỜNG HỢP NGOẠI LỆ =====
Dưới tiêu đề "4.2 XỬ LÝ CÁC TRƯỜNG HỢP NGOẠI LỆ" (hiện đang trống), chèn đoạn văn và các gạch đầu dòng sau:
Ngoài các kịch bản chức năng, hệ thống được thiết kế để xử lý các tình huống ngoài ý muốn mà không làm sai lệch dữ liệu. Các trường hợp dưới đây được kiểm tra trong quá trình thử nghiệm:
- **Mất kết nối mạng hoặc phiên hết hạn:** Ứng dụng hiển thị thông báo lỗi và cho phép thử lại; khi mã truy cập hết hạn, ứng dụng dùng mã làm mới để lấy mã mới, nếu không được thì đưa người dùng về màn hình đăng nhập. Thao tác chưa được máy chủ xác nhận không được hiển thị như đã thành công.
- **Gửi lặp yêu cầu do bấm nút nhiều lần:** Nút gửi bị khóa trong lúc chờ phản hồi; ở máy chủ, các ràng buộc duy nhất ngăn tạo trùng phòng, trùng khoản thu hoặc trùng giao dịch ngân hàng.
- **Thông báo giao dịch đến trễ, lặp hoặc sai định dạng:** Thông báo lặp được bỏ qua; thông báo đến trễ được xét theo thời điểm ngân hàng ghi nhận; thông báo sai định dạng hoặc sai khóa bị từ chối và được ghi nhật ký máy chủ.
- **Dịch vụ bên ngoài không phản hồi:** Khi dịch vụ SMS OTP hoặc thư điện tử lỗi, người dùng được thông báo gửi mã không thành công và có thể yêu cầu gửi lại; khi dịch vụ thông báo đẩy lỗi, nội dung vẫn được lưu trong mục “Thông báo”.
- **Tệp tải lên không hợp lệ:** Tệp sai định dạng hoặc vượt dung lượng cho phép bị từ chối kèm thông báo; dữ liệu nghiệp vụ đi kèm không bị lưu dở dang.
- **Truy cập bằng liên kết cũ:** Khi người dùng mở một thông báo hoặc liên kết đến dữ liệu đã bị hủy hoặc không còn quyền truy cập, ứng dụng chỉ hiển thị nội dung thông báo hoặc thông báo không có quyền, không làm ứng dụng dừng hoạt động.
- **Người dùng từ chối cấp quyền máy ảnh hoặc thư viện ảnh:** Ứng dụng thông báo cần cấp quyền để đính kèm ảnh; các chức năng không bắt buộc ảnh vẫn hoạt động bình thường.

KIỂM TRA SAU KHI LÀM (báo lại kết quả từng dòng):
1. Mục 3.3 có bốn mục con 3.3.1 đến 3.3.4, mỗi mục có các gạch đầu dòng với phần đầu in đậm; không còn dấu ** trong tài liệu.
2. Mục 3.4 không còn chữ "Mota"; có một đoạn văn và 20 chú thích hình, mỗi chú thích có một đoạn trống phía trên.
3. Chương 4: mục 4.1 có một đoạn văn và 14 mục con 4.1.1 đến 4.1.14, mỗi mục có một bảng 6 cột; cột "Kết quả thực tế" và "Trạng thái" để trống; không còn dòng ví dụ đăng nhập bằng email.
4. Mục 4.2 có một đoạn văn và 7 gạch đầu dòng.
5. Cập nhật toàn bộ trường (Ctrl+A rồi F9), Mục lục và Mục lục các hình vẽ.
