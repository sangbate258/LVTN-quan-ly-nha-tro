PROMPT 11 – MỤC 3.2.3 SƠ ĐỒ HOẠT ĐỘNG VÀ 3.2.4 SƠ ĐỒ TRIỂN KHAI (dán toàn bộ nội dung dưới đây cho AI Word; chỉ dùng sau khi đã chạy xong Prompt 10b)

VAI TRÒ: Bạn là người triển khai nội dung vào tài liệu LVTN.docx. Toàn bộ nội dung dưới đây đã được phân tích và chốt. Bạn chèn đúng nguyên văn từng chữ. Không tự viết thêm, không diễn đạt lại, không rút gọn, không suy luận, không sửa phần khác của tài liệu.

PHẠM VI: Chỉ làm việc trong mục "3.2.3 Sơ đồ hoạt động" và "3.2.4 Sơ đồ triển khai" (đến trước tiêu đề "3.3 KIẾN TRÚC BẢO MẬT VÀ TOÀN VẸN DỮ LIỆU").

VIỆC 1 – XÓA phần còn sót của đề tài khác: tiêu đề "3.2.3.1 Sơ đồ hoạt động của quản lý hồ sơ và điểm uy tín", gạch đầu dòng "Cập nhật thông tin tài khoản" ngay dưới nó và chú thích "Sơ đồ hoạt động của cập nhật thông tin tài khoản" (kể cả hình nếu có). Giữ tiêu đề "3.2.3 Sơ đồ hoạt động", tiêu đề "3.2.4 Sơ đồ triển khai" và chú thích "Sơ đồ triển khai của hệ thống".

ĐỊNH DẠNG:
- Tiêu đề mục con: dùng đúng kiểu và cách đánh số tự động của tiêu đề cấp 4 (như "2.3.1.5 Quy trình đổi mật khẩu"); số mục sẽ là 3.2.3.1 đến 3.2.3.17.
- Dòng bắt đầu bằng "GẠCH ĐẦU DÒNG:" là một gạch đầu dòng, dùng đúng kiểu gạch đầu dòng của mục 3.2.2; chỉ ghi phần chữ sau dấu hai chấm.
- Khối mô tả sơ đồ: chèn nguyên văn từ dòng "[[MÔ TẢ SƠ ĐỒ: ...]]" đến dòng "[[HẾT MÔ TẢ]]", mỗi dòng là một đoạn riêng, phông Consolas cỡ 10, căn trái. Đây là chỗ giữ chỗ cho hình.
- Chú thích hình: đặt ngay dưới khối mô tả sơ đồ, tạo bằng cơ chế chú thích có trường đánh số tự động, đúng kiểu chú thích hình đang có. Không gõ tay số hình.

===== VIỆC 2: MỤC 3.2.3 =====
CHÈN ngay dưới tiêu đề "3.2.3 Sơ đồ hoạt động" một đoạn văn và 17 mục con theo đúng thứ tự dưới đây.
ĐOẠN VĂN:
Sơ đồ hoạt động mô tả luồng xử lý của từng chức năng mở rộng theo ký pháp UML, phân làn theo tác nhân và hệ thống. Mỗi sơ đồ được xây dựng từ quy trình tương ứng ở mục 2.3.1, thể hiện điểm bắt đầu, các hoạt động, điểm quyết định, nhánh xử lý ngoại lệ và điểm kết thúc, làm căn cứ cho việc lập trình và xây dựng kịch bản kiểm thử ở Chương 4.

----- MỤC 3.2.3.1 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý tài khoản và xác thực
GẠCH ĐẦU DÒNG: Đăng ký tài khoản Chủ trọ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của đăng ký tài khoản Chủ trọ]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.1 “Quy trình đăng ký tài khoản Chủ trọ”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của đăng ký tài khoản Chủ trọ
GẠCH ĐẦU DÒNG: Đăng nhập tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của đăng nhập tài khoản]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.2 “Quy trình đăng nhập tài khoản”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của đăng nhập tài khoản
GẠCH ĐẦU DÒNG: Đăng xuất tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của đăng xuất tài khoản]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.3 “Quy trình đăng xuất tài khoản”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của đăng xuất tài khoản
GẠCH ĐẦU DÒNG: Quên mật khẩu
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của quên mật khẩu]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.4 “Quy trình quên mật khẩu”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của quên mật khẩu
GẠCH ĐẦU DÒNG: Đổi mật khẩu
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của đổi mật khẩu]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.5 “Quy trình đổi mật khẩu”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của đổi mật khẩu
GẠCH ĐẦU DÒNG: Cập nhật thông tin tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của cập nhật thông tin tài khoản]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.6 “Quy trình cập nhật thông tin tài khoản”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của cập nhật thông tin tài khoản
GẠCH ĐẦU DÒNG: Cập nhật thông tin khôi phục tài khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của cập nhật thông tin khôi phục tài khoản]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.7 “Quy trình cập nhật thông tin khôi phục tài khoản”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của cập nhật thông tin khôi phục tài khoản
GẠCH ĐẦU DÒNG: Thiết lập tài khoản ngân hàng nhận tiền
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của thiết lập tài khoản ngân hàng nhận tiền]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.8 “Quy trình thiết lập tài khoản ngân hàng nhận tiền”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của thiết lập tài khoản ngân hàng nhận tiền
GẠCH ĐẦU DÒNG: Kết nối dịch vụ thông báo biến động số dư
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của kết nối dịch vụ thông báo biến động số dư]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.9 “Quy trình kết nối dịch vụ thông báo biến động số dư”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của kết nối dịch vụ thông báo biến động số dư

----- MỤC 3.2.3.2 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý nhà trọ, nhóm phòng và phòng
GẠCH ĐẦU DÒNG: Thiết lập thông tin nhà trọ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của thiết lập thông tin nhà trọ]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.10 “Quy trình thiết lập thông tin nhà trọ”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của thiết lập thông tin nhà trọ
GẠCH ĐẦU DÒNG: Quản lý nhóm phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của quản lý nhóm phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.11 “Quy trình quản lý nhóm phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của quản lý nhóm phòng
GẠCH ĐẦU DÒNG: Thêm phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của thêm phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.12 “Quy trình thêm phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của thêm phòng
GẠCH ĐẦU DÒNG: Cập nhật phòng và tạm ngừng sử dụng phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của cập nhật phòng và tạm ngừng sử dụng phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.13 “Quy trình cập nhật phòng và tạm ngừng sử dụng phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của cập nhật phòng và tạm ngừng sử dụng phòng
GẠCH ĐẦU DÒNG: Tra cứu phòng theo trạng thái
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của tra cứu phòng theo trạng thái]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.14 “Quy trình tra cứu phòng theo trạng thái”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của tra cứu phòng theo trạng thái

----- MỤC 3.2.3.3 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý dịch vụ và đơn giá
GẠCH ĐẦU DÒNG: Khai báo dịch vụ, đơn giá và phương pháp tính
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của khai báo dịch vụ, đơn giá và phương pháp tính]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.15 “Quy trình khai báo dịch vụ, đơn giá và phương pháp tính”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của khai báo dịch vụ, đơn giá và phương pháp tính
GẠCH ĐẦU DÒNG: Cập nhật mức phí và trạng thái áp dụng dịch vụ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của cập nhật mức phí và trạng thái áp dụng dịch vụ]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.16 “Quy trình cập nhật mức phí và trạng thái áp dụng dịch vụ”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của cập nhật mức phí và trạng thái áp dụng dịch vụ

----- MỤC 3.2.3.4 -----
TIÊU ĐỀ: Sơ đồ hoạt động của giữ phòng và quản lý tiền cọc
GẠCH ĐẦU DÒNG: Lập phiếu giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của lập phiếu giữ phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.17 “Quy trình lập phiếu giữ phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của lập phiếu giữ phòng
GẠCH ĐẦU DÒNG: Xác nhận tiền cọc giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của xác nhận tiền cọc giữ phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.18 “Quy trình xác nhận tiền cọc giữ phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của xác nhận tiền cọc giữ phòng
GẠCH ĐẦU DÒNG: Gia hạn phiếu giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của gia hạn phiếu giữ phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.19 “Quy trình gia hạn phiếu giữ phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của gia hạn phiếu giữ phòng
GẠCH ĐẦU DÒNG: Hủy phiếu giữ phòng và xử lý tiền cọc
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của hủy phiếu giữ phòng và xử lý tiền cọc]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.20 “Quy trình hủy phiếu giữ phòng và xử lý tiền cọc”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của hủy phiếu giữ phòng và xử lý tiền cọc

----- MỤC 3.2.3.5 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý hợp đồng và thành viên
GẠCH ĐẦU DÒNG: Lập hợp đồng từ phiếu giữ phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của lập hợp đồng từ phiếu giữ phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.21 “Quy trình lập hợp đồng từ phiếu giữ phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của lập hợp đồng từ phiếu giữ phòng
GẠCH ĐẦU DÒNG: Nhập hợp đồng đang còn hiệu lực
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của nhập hợp đồng đang còn hiệu lực]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.22 “Quy trình nhập hợp đồng đang còn hiệu lực”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của nhập hợp đồng đang còn hiệu lực
GẠCH ĐẦU DÒNG: Tạo và liên kết tài khoản Khách thuê
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của tạo và liên kết tài khoản Khách thuê]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.23 “Quy trình tạo và liên kết tài khoản Khách thuê”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của tạo và liên kết tài khoản Khách thuê

----- MỤC 3.2.3.6 -----
TIÊU ĐỀ: Sơ đồ hoạt động của bàn giao phòng
GẠCH ĐẦU DÒNG: Bàn giao phòng khi nhận phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của bàn giao phòng khi nhận phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.24 “Quy trình bàn giao phòng khi nhận phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của bàn giao phòng khi nhận phòng
GẠCH ĐẦU DÒNG: Bàn giao khi trả phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của bàn giao khi trả phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.45 “Quy trình bàn giao khi trả phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của bàn giao khi trả phòng

----- MỤC 3.2.3.7 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý chỉ số điện nước
GẠCH ĐẦU DÒNG: Ghi nhận và chốt chỉ số điện nước
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của ghi nhận và chốt chỉ số điện nước]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.25 “Quy trình ghi nhận và chốt chỉ số điện nước”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của ghi nhận và chốt chỉ số điện nước
GẠCH ĐẦU DÒNG: Ghi nhận thay công tơ
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của ghi nhận thay công tơ]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.26 “Quy trình ghi nhận thay công tơ”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của ghi nhận thay công tơ
GẠCH ĐẦU DÒNG: Phản hồi và điều chỉnh chỉ số đã chốt
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của phản hồi và điều chỉnh chỉ số đã chốt]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Khách thuê | Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.27 “Quy trình phản hồi và điều chỉnh chỉ số đã chốt”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của phản hồi và điều chỉnh chỉ số đã chốt

----- MỤC 3.2.3.8 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý phiếu báo phí
GẠCH ĐẦU DÒNG: Lập phiếu báo phí nháp
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của lập phiếu báo phí nháp]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.28 “Quy trình lập phiếu báo phí nháp”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của lập phiếu báo phí nháp
GẠCH ĐẦU DÒNG: Phân bổ nghĩa vụ thanh toán
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của phân bổ nghĩa vụ thanh toán]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.29 “Quy trình phân bổ nghĩa vụ thanh toán”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của phân bổ nghĩa vụ thanh toán
GẠCH ĐẦU DÒNG: Kiểm tra và phát hành phiếu báo phí
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của kiểm tra và phát hành phiếu báo phí]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.30 “Quy trình kiểm tra và phát hành phiếu báo phí”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của kiểm tra và phát hành phiếu báo phí
GẠCH ĐẦU DÒNG: Điều chỉnh phiếu báo phí đã phát hành
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của điều chỉnh phiếu báo phí đã phát hành]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.31 “Quy trình điều chỉnh phiếu báo phí đã phát hành”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của điều chỉnh phiếu báo phí đã phát hành

----- MỤC 3.2.3.9 -----
TIÊU ĐỀ: Sơ đồ hoạt động của tra cứu thông tin thuê
GẠCH ĐẦU DÒNG: Tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.32 “Quy trình tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của tra cứu hợp đồng, phiếu báo phí và công nợ của Khách thuê

----- MỤC 3.2.3.10 -----
TIÊU ĐỀ: Sơ đồ hoạt động của thanh toán VietQR và báo chuyển khoản
GẠCH ĐẦU DÒNG: Tạo yêu cầu thanh toán VietQR
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của tạo yêu cầu thanh toán VietQR]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.33 “Quy trình tạo yêu cầu thanh toán VietQR”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của tạo yêu cầu thanh toán VietQR
GẠCH ĐẦU DÒNG: Báo chuyển khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của báo chuyển khoản]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.34 “Quy trình báo chuyển khoản và xác nhận thủ công”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Phạm vi: Chỉ vẽ phần của Khách thuê: từ khi chọn “Tôi đã chuyển” và đính kèm chứng từ đến khi hệ thống ghi nhận báo chuyển khoản chờ xác nhận và thông báo cho Chủ trọ.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của báo chuyển khoản

----- MỤC 3.2.3.11 -----
TIÊU ĐỀ: Sơ đồ hoạt động của xác nhận thanh toán và đối chiếu giao dịch
GẠCH ĐẦU DÒNG: Xác nhận báo chuyển khoản
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của xác nhận báo chuyển khoản]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.34 “Quy trình báo chuyển khoản và xác nhận thủ công”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Phạm vi: Chỉ vẽ phần của Chủ trọ: từ khi mở báo chuyển khoản, kiểm tra tiền thực nhận, chọn “Xác nhận” hoặc “Từ chối” đến khi hệ thống thông báo kết quả cho Khách thuê.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của xác nhận báo chuyển khoản
GẠCH ĐẦU DÒNG: Tự động xác nhận giao dịch ngân hàng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của tự động xác nhận giao dịch ngân hàng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Dịch vụ thông báo biến động số dư | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.35 “Quy trình tự động xác nhận giao dịch ngân hàng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của tự động xác nhận giao dịch ngân hàng
GẠCH ĐẦU DÒNG: Đối chiếu thủ công giao dịch không khớp
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của đối chiếu thủ công giao dịch không khớp]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.36 “Quy trình đối chiếu thủ công giao dịch không khớp”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của đối chiếu thủ công giao dịch không khớp
GẠCH ĐẦU DÒNG: Ghi nhận thanh toán tiền mặt
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của ghi nhận thanh toán tiền mặt]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.37 “Quy trình ghi nhận thanh toán tiền mặt”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của ghi nhận thanh toán tiền mặt

----- MỤC 3.2.3.12 -----
TIÊU ĐỀ: Sơ đồ hoạt động của theo dõi công nợ và nhắc thanh toán
GẠCH ĐẦU DÒNG: Theo dõi công nợ và nhắc thanh toán
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của theo dõi công nợ và nhắc thanh toán]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.38 “Quy trình theo dõi công nợ và nhắc thanh toán”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của theo dõi công nợ và nhắc thanh toán

----- MỤC 3.2.3.13 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý sự cố
GẠCH ĐẦU DÒNG: Gửi yêu cầu sự cố
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của gửi yêu cầu sự cố]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Khách thuê | Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.39 “Quy trình gửi yêu cầu sự cố”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của gửi yêu cầu sự cố
GẠCH ĐẦU DÒNG: Xử lý sự cố và ghi nhận chi phí
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của xử lý sự cố và ghi nhận chi phí]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.40 “Quy trình xử lý sự cố và ghi nhận chi phí”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của xử lý sự cố và ghi nhận chi phí
GẠCH ĐẦU DÒNG: Xác nhận kết quả xử lý sự cố
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của xác nhận kết quả xử lý sự cố]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.41 “Quy trình xác nhận kết quả xử lý sự cố”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của xác nhận kết quả xử lý sự cố

----- MỤC 3.2.3.14 -----
TIÊU ĐỀ: Sơ đồ hoạt động của gia hạn và điều chỉnh hợp đồng
GẠCH ĐẦU DÒNG: Gia hạn hợp đồng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của gia hạn hợp đồng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.42 “Quy trình gia hạn hợp đồng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của gia hạn hợp đồng
GẠCH ĐẦU DÒNG: Điều chỉnh hợp đồng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của điều chỉnh hợp đồng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.43 “Quy trình điều chỉnh hợp đồng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của điều chỉnh hợp đồng

----- MỤC 3.2.3.15 -----
TIÊU ĐỀ: Sơ đồ hoạt động của trả phòng, thanh lý và quyết toán
GẠCH ĐẦU DÒNG: Yêu cầu trả phòng
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của yêu cầu trả phòng]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Khách thuê | Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.44 “Quy trình yêu cầu trả phòng”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của yêu cầu trả phòng
GẠCH ĐẦU DÒNG: Thanh lý hợp đồng và quyết toán tiền cọc
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của thanh lý hợp đồng và quyết toán tiền cọc]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.46 “Quy trình thanh lý hợp đồng và quyết toán tiền cọc”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của thanh lý hợp đồng và quyết toán tiền cọc

----- MỤC 3.2.3.16 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý thu chi và thống kê
GẠCH ĐẦU DÒNG: Ghi nhận khoản thu chi khác
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của ghi nhận khoản thu chi khác]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.47 “Quy trình ghi nhận khoản thu chi khác”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của ghi nhận khoản thu chi khác
GẠCH ĐẦU DÒNG: Xem thống kê
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của xem thống kê]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.48 “Quy trình xem thống kê”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của xem thống kê

----- MỤC 3.2.3.17 -----
TIÊU ĐỀ: Sơ đồ hoạt động của quản lý thông báo
GẠCH ĐẦU DÒNG: Gửi thông báo chung
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của gửi thông báo chung]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.49 “Quy trình gửi thông báo chung”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của gửi thông báo chung
GẠCH ĐẦU DÒNG: Xem thông báo
[[MÔ TẢ SƠ ĐỒ: Sơ đồ hoạt động của xem thông báo]]
Loại: Sơ đồ hoạt động UML có phân làn dọc; nút bắt đầu hình tròn đen đặc, nút kết thúc hình tròn đen có viền ngoài, hoạt động là hình chữ nhật bo góc, quyết định và hợp nhánh là hình thoi có ghi điều kiện trên từng nhánh ra.
Làn (từ trái sang phải): Chủ trọ | Khách thuê | Hệ thống
Căn cứ nội dung: đúng theo đoạn văn của mục 2.3.1.50 “Quy trình xem thông báo”. Khi gửi cho AI vẽ, dán đoạn văn đó ngay sau khối này. Chỉ dùng các tác nhân, hoạt động và điều kiện có trong đoạn văn; không thêm bước.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu; mũi tên vuông góc không cắt qua nút.
[[HẾT MÔ TẢ]]
CHÚ THÍCH HÌNH: Sơ đồ hoạt động của xem thông báo

===== VIỆC 3: MỤC 3.2.4 SƠ ĐỒ TRIỂN KHAI =====
CHÈN ngay dưới tiêu đề "3.2.4 Sơ đồ triển khai", TRƯỚC chú thích "Sơ đồ triển khai của hệ thống", lần lượt đoạn văn và khối mô tả sau:
ĐOẠN VĂN:
Hệ thống được triển khai theo mô hình ba thành phần gồm ứng dụng di động, máy chủ ứng dụng và máy chủ cơ sở dữ liệu. Ứng dụng React Native được đóng gói bằng Expo và cài đặt trên điện thoại Android hoặc iOS, giao tiếp với máy chủ qua REST API sử dụng HTTPS. Máy chủ ứng dụng chạy Node.js với Express.js theo kiến trúc nguyên khối, truy cập MySQL thông qua Prisma ORM, lưu tệp hình ảnh và chứng từ trong thư mục trên máy chủ, đồng thời chạy tác vụ định kỳ để lập phiếu báo phí nháp, chuyển yêu cầu thanh toán và phiếu giữ phòng sang trạng thái hết hạn, nhắc hợp đồng sắp kết thúc. Máy chủ kết nối ra ngoài với dịch vụ gửi SMS OTP, dịch vụ thư điện tử và dịch vụ thông báo đẩy của Expo; dịch vụ thông báo biến động số dư gọi vào máy chủ qua địa chỉ tiếp nhận riêng của từng nhà trọ. Trong giai đoạn phát triển và trình diễn, dịch vụ SMS OTP chạy ở chế độ thử nghiệm, mã OTP được ghi vào nhật ký máy chủ thay vì gửi qua nhà mạng.
KHỐI MÔ TẢ SƠ ĐỒ:
[[MÔ TẢ SƠ ĐỒ: Sơ đồ triển khai của hệ thống]]
Loại: Sơ đồ triển khai UML; mỗi nút (node) là khối hộp ba chiều có nhãn «device» hoặc «server» hoặc «external»; thành phần phần mềm bên trong nút là hình chữ nhật có nhãn «component»; đường nối ghi giao thức.
Nút 1 «device» Điện thoại Android / iOS: chứa «component» Ứng dụng di động (React Native, Expo, TypeScript).
Nút 2 «server» Máy chủ ứng dụng (Node.js): chứa «component» REST API (Express.js, TypeScript); «component» Các module nghiệp vụ M1–M8; «component» Prisma Client; «component» Tác vụ định kỳ; «artifact» Thư mục lưu tệp (hình ảnh, chứng từ).
Nút 3 «server» Máy chủ cơ sở dữ liệu: chứa «component» MySQL (InnoDB).
Nút 4 «external» Dịch vụ thông báo biến động số dư (ví dụ SePay).
Nút 5 «external» Dịch vụ gửi SMS OTP.
Nút 6 «external» Dịch vụ thư điện tử (SMTP).
Nút 7 «external» Dịch vụ thông báo đẩy Expo (chuyển tiếp đến FCM / APNs).
Đường nối: Nút 1 — Nút 2 ghi “HTTPS / REST API (JSON)”; Nút 2 — Nút 3 ghi “TCP 3306 (Prisma)”; Nút 4 → Nút 2 ghi “HTTPS webhook (khóa xác thực)”; Nút 2 → Nút 5 ghi “HTTPS API”; Nút 2 → Nút 6 ghi “SMTP/TLS”; Nút 2 → Nút 7 ghi “HTTPS”; Nút 7 → Nút 1 ghi “Thông báo đẩy”.
Bố cục: Nút 1 bên trái, Nút 2 ở giữa, Nút 3 bên phải Nút 2; Nút 4 đến Nút 7 xếp hàng dọc phía dưới Nút 2.
Trình bày: nền trắng, viền và chữ đen, phông cỡ 12, không tô màu.
[[HẾT MÔ TẢ]]

KIỂM TRA SAU KHI LÀM (báo lại kết quả từng dòng):
1. Không còn nội dung "quản lý hồ sơ và điểm uy tín" trong mục 3.2.3.
2. Mục 3.2.3 có một đoạn văn và đúng 17 mục con 3.2.3.1 đến 3.2.3.17, tổng cộng 51 khối mô tả và 51 chú thích hình.
3. Mục 3.2.4 có một đoạn văn, một khối mô tả sơ đồ và chú thích "Sơ đồ triển khai của hệ thống".
4. Sau khi cập nhật toàn bộ trường (Ctrl+A rồi F9), sơ đồ hoạt động đầu tiên là Hình 3-71 và sơ đồ triển khai là Hình 3-122. Cập nhật Mục lục và Mục lục các hình vẽ.
