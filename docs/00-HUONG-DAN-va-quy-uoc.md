# LVTN – Hướng dẫn dùng bộ prompt, quy ước vẽ và các điểm đã chốt

Cập nhật: 17/11/2026. Đề tài: Xây dựng ứng dụng di động quản lý nhà trọ quy mô nhỏ.

## 1. Thứ tự sử dụng

Chạy lần lượt, mỗi lần dán toàn bộ một file vào AI Word, đợi nó báo kết quả phần "KIỂM TRA SAU KHI LÀM" rồi mới chạy file kế tiếp.

| Thứ tự | File                                | Nội dung                                            | Hình sau khi xong  |
| ------ | ----------------------------------- | --------------------------------------------------- | ------------------ |
| 1      | 01-prompt-sua-chuong-1              | Sửa 12 câu ở Chương 1 và mục 2.2.4 cho khớp SMS OTP | không đổi          |
| 2      | 02-prompt-muc-2.3.1.6-den-2.3.1.14  | Tài khoản, nhà trọ, phòng                           | Hình 2-15 đến 2-23 |
| 3      | 03-prompt-muc-2.3.1.15-den-2.3.1.24 | Dịch vụ, giữ phòng, hợp đồng                        | Hình 2-24 đến 2-33 |
| 4      | 04-prompt-muc-2.3.1.25-den-2.3.1.32 | Chỉ số, phiếu báo phí, tra cứu                      | Hình 2-34 đến 2-41 |
| 5      | 05-prompt-muc-2.3.1.33-den-2.3.1.41 | Thanh toán, công nợ, sự cố                          | Hình 2-42 đến 2-50 |
| 6      | 06-prompt-muc-2.3.1.42-den-2.3.1.50 | Thay đổi hợp đồng, trả phòng, thu chi, thông báo    | Hình 2-51 đến 2-59 |
| 7      | 07-prompt-muc-2.3.2-den-2.3.4       | Sơ đồ chức năng, kiến trúc, use case tổng quát      | Hình 2-60 đến 2-63 |
| 8      | 08a-prompt-muc-3.1.1-3.1.2          | Xóa phần còn sót, mô hình ý niệm, lược đồ 36 bảng, quan hệ, mô hình luận lý | Hình 3-1, 3-2 |
| 9      | 08b-prompt-muc-3.1.3-bang-vat-ly    | 36 bảng mức vật lý                                  | không đổi          |
| 10     | 09-prompt-muc-3.2.1-use-case-chi-tiet | 17 use case chi tiết, 51 chức năng mở rộng        | Hình 3-3 đến 3-19  |
| 11     | 10a-prompt-muc-3.2.2-tuan-tu-phan-1 | Sơ đồ tuần tự của use case 1 đến 8                  | Hình 3-20 đến 3-51 |
| 12     | 10b-prompt-muc-3.2.2-tuan-tu-phan-2 | Sơ đồ tuần tự của use case 9 đến 17                 | Hình 3-52 đến 3-70 |
| 13     | 11-prompt-muc-3.2.3-3.2.4-hoat-dong-trien-khai | 51 sơ đồ hoạt động, sơ đồ triển khai     | Hình 3-71 đến 3-122 |
| 14     | 12-prompt-muc-3.3-3.4-chuong-4      | Bảo mật và toàn vẹn dữ liệu, 20 chỗ ảnh màn hình, 80 kịch bản thử nghiệm, xử lý ngoại lệ | Hình 3-123 đến 3-142 |

File schema.prisma không dán vào Word. Đây là lược đồ Prisma sinh từ cùng đặc tả với mục 3.1 và đã kiểm tra hợp lệ bằng bộ kiểm tra lược đồ của Prisma 7. Bạn dùng nó làm điểm bắt đầu khi lập trình.

Nếu AI Word báo nội dung quá dài: cắt file làm hai tại một dòng "===== MỤC ... =====", giữ nguyên phần đầu (VAI TRÒ, VỊ TRÍ, ĐỊNH DẠNG) ở cả hai nửa.

Số hình ở cột cuối chỉ đúng khi 5 hình hiện có của mục 2.3.1.1–2.3.1.5 là Hình 2-10 đến 2-14. Trong LVTN.docx hiện tại, năm hình thuộc mục 2.3.1.1 đến 2.3.1.5 được đánh số từ Hình 2-10 đến Hình 2-14. Các hình minh họa mẫu của mục 2.3.2 đến 2.3.4 hiện được đánh số từ Hình 2-15 đến Hình 2-17 và sẽ được thay thế khi triển khai Prompt 07. Sau khi bổ sung các quy trình mới, cần cập nhật trường đánh số tự động và danh mục hình để bảo đảm thứ tự chính xác.

## 2. Cách nhờ AI vẽ draw.io (mẫu prompt của bạn)

Các mục 2.3.1.6 đến 2.3.1.50 không còn khối mô tả sơ đồ. Đoạn văn của từng mục chính là mô tả để vẽ: bạn chỉ thay phần trong dấu ngoặc kép của mẫu dưới đây bằng tên quy trình và đoạn văn của mục cần vẽ, đính kèm ảnh sơ đồ mẫu để AI vẽ theo phong cách đó.

```
Bạn là System Analyst và chuyên gia mô hình hóa quy trình bằng draw.io (hãy sử dụng mcp draw.io đã kết nối).
Hãy tạo sơ đồ flowchart [TÊN QUY TRÌNH] cho luồng dưới đây:
"[DÁN ĐOẠN VĂN CỦA MỤC]".
Yêu cầu:
1. Sơ đồ phải phù hợp đưa vào báo cáo luận văn học thuật, theo phong cách flowchart truyền thống (tham khảo ảnh ví dụ).
2. Sau khi làm xong phải kiểm tra lại xem có chuẩn chưa rồi mới đưa ra sản phẩm cuối cùng.
```

Lưu ý khi dùng:

- Chỉ dán đoạn văn của đúng mục đó, không dán cả tiêu đề hay chú thích.
- Sơ đồ chức năng, kiến trúc và use case tổng quát (file 07) không có đoạn văn nên vẫn giữ khối mô tả riêng trong file 07; bạn cắt khối đó dán vào chỗ trong dấu ngoặc kép như trên và đổi “flowchart” thành đúng loại sơ đồ.
- Sau khi vẽ xong, nên gửi cả file LVTN.docx cho ChatGPT để đối chiếu sơ đồ với đoạn văn, như bạn đã định.

## 3. Các quyết định đã chốt (16/11/2026)

- Xác thực theo SMS OTP như mục 2.3.1.1–2.3.1.5 và file PTTKHTTT; Chương 1 được sửa theo (Prompt 01).
- Chưa có cơ sở dữ liệu hay mã nguồn; mục 3.1 sẽ được thiết kế mới từ 22 yêu cầu chức năng và 24 quy tắc nghiệp vụ.
- Mục 3.2.2 và 3.2.3 làm đủ như file mẫu: 51 sơ đồ tuần tự và 51 sơ đồ hoạt động, mỗi chức năng mở rộng một sơ đồ.
- Mục 2.3.1 có 50 quy trình; danh sách đã duyệt.
- Chương 4: viết kịch bản và kết quả mong đợi; cột "Kết quả thực tế" và "Trạng thái" để trống đến khi chạy thật. Mục 3.4: để chỗ trống cho ảnh màn hình.

## 4. Chi tiết tôi đã tự bổ sung, cần bạn xác nhận

Những điểm dưới đây không có trong yêu cầu chức năng hay quy tắc nghiệp vụ của file PTTKHTTT. Tôi chọn phương án đơn giản nhất để quy trình viết được trọn vẹn. Nếu bạn muốn khác, báo số thứ tự để tôi sửa mục tương ứng.

1. Tên màn hình và nút trong ngoặc kép (“Tài khoản nhận tiền”, “Giữ phòng”, “Thu tiền mặt”...) là tên đề xuất; khi lập trình nên đặt đúng như vậy. (mọi mục)
2. Ngày dự kiến lập phiếu chỉ nhận từ ngày 1 đến ngày 28, để tháng nào cũng có ngày đó. (2.3.1.10)
3. Chỉ xóa được nhóm phòng khi nhóm không còn phòng. (2.3.1.11)
4. Thêm phòng: một màn hình chung cho một hoặc nhiều phòng giống nhau, có trường “Số lượng”; khi số lượng lớn hơn một thì tên phòng là tên gốc và hệ thống tự đánh số từ 1 (“Phòng” + số lượng 10 = Phòng 1 đến Phòng 10); không dùng file Excel; có lỗi thì chưa lưu phòng nào. Mỗi phòng sau đó chỉnh riêng được. (2.3.1.12)
5. Chỉ tạm ngừng được phòng đang Trống; tạm ngừng kéo dài đến khi chủ trọ chọn “Mở lại”. (2.3.1.13)
6. Thiết lập tài khoản nhận tiền: hệ thống chỉ kiểm tra định dạng và cho chủ trọ xem lại trước khi lưu, vì không kết nối ngân hàng. (2.3.1.8)
7. Kết nối biến động số dư: hệ thống cấp địa chỉ tiếp nhận thông báo và khóa xác thực riêng cho từng nhà trọ để chủ trọ khai báo tại dịch vụ. Đã kiểm tra: tài liệu SePay có hỗ trợ xác thực webhook bằng API Key và trường transactionDate. (2.3.1.9)
8. Phòng chuyển sang Đã giữ chỗ ngay khi lập phiếu giữ phòng (nếu đang Trống), chuyển sang Đang thuê ngay khi lưu hợp đồng. (2.3.1.17, 2.3.1.21)
9. Số tiền cọc giữ phòng phải lớn hơn 0 và không vượt quá giá thuê một tháng đã thỏa thuận; tiền cọc giữ phòng chỉ được xác nhận thủ công. Khi cấn trừ cọc vào tiền thuê tháng đầu, nếu cọc lớn hơn số tiền thuê kỳ đầu thì chỉ cấn trừ tối đa số tiền thuê phải trả, phần chênh lệch được ghi nhận là khoản Chủ trọ cần hoàn cho người đặt cọc. (2.3.1.17, 2.3.1.18, 2.3.1.21, 2.3.1.28)
10. Chia đều: phần dư tính theo đơn vị đồng, cộng mỗi người một đồng theo thứ tự danh sách. (2.3.1.29)
11. Phiếu báo phí chưa phát hành được Chủ trọ tự chỉnh sửa. Phiếu đã phát hành nhưng chưa có thanh toán được xác nhận được phép chỉnh sửa trên cùng phiếu, lưu lịch sử và đánh dấu để Khách thuê nhận biết; yêu cầu VietQR đang chờ theo số tiền cũ phải được vô hiệu hóa khi thay đổi số tiền. Phiếu đã có ít nhất một khoản thanh toán được xác nhận thì không được chỉnh sửa hoặc hủy trực tiếp. Nếu phát hiện sai, Chủ trọ ghi nhận khoản điều chỉnh tăng hoặc giảm riêng, liên kết với phiếu gốc; khoản giảm được hoàn hoặc bù trừ kỳ sau, khoản tăng được ghi nhận để thu bổ sung. (2.3.1.31)
12. Sự cố có bốn trạng thái: Mới, Đang xử lý, Chờ khách xác nhận, Hoàn tất; sự cố do chủ trọ tự tạo thì chủ trọ tự đóng. (2.3.1.39–2.3.1.41)
13. Quyết toán: khách xem bảng quyết toán trên ứng dụng, hai bên thống nhất ngoài ứng dụng, chủ trọ bấm hoàn tất. Khách không bấm xác nhận quyết toán trên ứng dụng. (2.3.1.46)
14. Thông báo chung gửi được cho toàn bộ khách đang có hợp đồng hiệu lực hoặc theo phòng. (2.3.1.49)
15. Sơ đồ use case tổng quát chỉ đưa dịch vụ thông báo biến động số dư làm tác nhân ngoài, vì chỉ nó chủ động gọi vào hệ thống; ba dịch vụ còn lại thể hiện ở sơ đồ kiến trúc. (2.3.4)

Bổ sung khi viết Chương 3 và Chương 4 (17/11/2026):

16. Số tiền lưu bằng số nguyên theo đơn vị đồng; khóa chính là số nguyên tự tăng. (3.1)
17. Giá thuê theo bảng giá số người được lưu thành một giá thuê tháng đã thỏa thuận của hợp đồng; khi số người thay đổi thì dùng chức năng điều chỉnh hợp đồng. Thiết kế không có bảng giá theo số người riêng. (3.1, 2.3.1.21)
18. Phiếu giữ phòng lưu “giá thuê tháng đã thỏa thuận” để kiểm tra giới hạn tiền cọc; giá này mặc định lấy giá niêm yết của phòng khi lập phiếu. (3.1, 2.3.1.17)
19. Phần cọc giữ phòng vượt tiền thuê kỳ đầu được tính ngay khi lập hợp đồng và lưu ở hợp đồng thành “khoản cần hoàn cho người đặt cọc”, kèm thời điểm Chủ trọ ghi nhận đã hoàn. (3.1, 2.3.1.21)
20. Dịch vụ được áp dụng hoặc ngừng áp dụng theo từng hợp đồng (bảng contract_services); “chọn phòng” ở 2.3.1.16 hiểu là chọn hợp đồng đang thuê của phòng đó. (3.1)
21. Phiếu báo phí chỉ có hai trạng thái Nháp và Đã phát hành, kèm cờ “Đã điều chỉnh”. Khoản điều chỉnh của phiếu đã có thanh toán lưu ở bảng riêng invoice_adjustments với cách xử lý: đưa vào kỳ sau, hoàn tiền (giảm) hoặc xử lý khi quyết toán (tăng). (3.1, 2.3.1.31)
22. Khoản trả dư lưu thành số dư của từng thành viên (credit_balance) và được bù trừ khi lập phiếu kỳ sau. (3.1, 2.3.1.29, 2.3.1.38)
23. Khi quyết toán, phần tiền cọc cấn trừ công nợ được ghi thành khoản thanh toán hình thức “cấn trừ từ tiền cọc”, không tính vào tiền thực thu; chỉ khoản khấu trừ được Chủ trọ đánh dấu có bản chất doanh thu mới vào doanh thu. (3.1, 2.3.1.46, 2.3.1.48)
24. Biên bản trả phòng có bốn trạng thái: chờ khách xác nhận, khách phản hồi, khách đã xác nhận, Chủ trọ hoàn tất ghi nhận khi khách chưa xác nhận. (3.1, 2.3.1.45)
25. Giao dịch ngân hàng nghi trùng khoản đã xác nhận thủ công được đưa vào danh sách cần đối chiếu; Chủ trọ xử lý bằng “Không liên quan” kèm lý do “đã ghi nhận trước đó”, không tạo khoản thu mới. (2.3.1.35, 2.3.1.36)
26. Lịch sử điều chỉnh của mọi dữ liệu quan trọng dùng chung một bảng nhật ký thay đổi (audit_logs) thay vì mỗi loại một bảng lịch sử. (3.1, 3.3.4)
27. Mã OTP gồm 6 chữ số, hết hiệu lực sau 5 phút, bị vô hiệu sau 5 lần nhập sai. (3.3.2)
28. Kỹ thuật: mã truy cập JWT kèm mã làm mới lưu dạng băm; băm mật khẩu bằng bcrypt; tác vụ định kỳ chạy trong tiến trình máy chủ; thông báo đẩy qua dịch vụ của Expo; sao lưu bằng mysqldump. Đây là thư viện và dịch vụ đi kèm bộ công nghệ đã chốt, không phải công nghệ chính mới. (3.3, 3.2.4)
29. Tệp ảnh chỉ nhận JPEG hoặc PNG, tên tệp do máy chủ sinh ngẫu nhiên. (3.3.2)

## 5. Việc còn mở

Ba việc dưới đây đã được viết vào Chương 3 theo đề xuất. Muốn đổi thì báo để tôi sửa các file liên quan.

- Phiếu giữ phòng: mỗi phòng có tối đa một phiếu giữ phòng chưa xử lý, kể cả phiếu quá hạn; ngày nhận dự kiến không được nằm trong thời gian của hợp đồng chưa thanh lý. (2.3.1.17, 3.1)
- Ảnh và chứng từ: lưu thành tệp trong thư mục trên máy chủ, cơ sở dữ liệu chỉ lưu đường dẫn (bảng attachments). (3.1, 3.2.4)
- SMS OTP: khi phát triển và trình diễn dùng chế độ thử nghiệm, mã OTP ghi vào nhật ký máy chủ; đã ghi rõ ở 3.2.4 và Chương 4. (3.2.4, 4.1)

Việc chỉ bạn quyết được là chức năng nào sẽ thực sự lập trình kịp. Chương 2 và 3 mô tả thiết kế đầy đủ; Chương 4 chỉ được điền “Kết quả thực tế” và “Trạng thái” cho kịch bản đã chạy thật. Kịch bản và ảnh màn hình của chức năng không làm kịp thì xóa khỏi Chương 4 và mục 3.4 trước khi nộp, đồng thời ghi vào mục 5.2.

## 6. Phạm vi đã hoàn thành và phần còn lại

Đã có prompt cho phần sửa Chương 1, toàn bộ Chương 2, Chương 3 và Chương 4. Chưa làm Chương 5, phụ lục hướng dẫn và tài liệu tham khảo bổ sung, vì nằm ngoài phạm vi “đến hết chương 4”. Chương 5 và phụ lục hiện vẫn còn nội dung của đề tài khác (“Trang quản lý”, “Hướng dẫn đăng bài tặng thực phẩm”) và cần viết sau khi có kết quả lập trình.

Cách vẽ các hình ở Chương 3: sơ đồ use case, ERD, mô hình luận lý, sơ đồ tuần tự và sơ đồ triển khai có khối mô tả riêng. Bạn cắt khối đó dán vào chỗ trong ngoặc kép của mẫu prompt ở mục 2, và đổi chữ “flowchart” thành đúng loại sơ đồ. Sơ đồ hoạt động dùng lại đoạn văn của quy trình ở mục 2.3.1, như khối mô tả đã ghi.

Tên chức năng mở rộng ở Chương 3 lấy đúng theo tiêu đề quy trình ở mục 2.3.1 (bỏ chữ “Quy trình”), riêng quy trình 2.3.1.34 được tách thành hai chức năng “Báo chuyển khoản” (Khách thuê) và “Xác nhận báo chuyển khoản” (Chủ trọ).

Danh sách 17 use case đã dùng ở mục 2.3.4 (giữ nguyên tên này cho Chương 3): Quản lý tài khoản và xác thực; Quản lý nhà trọ, nhóm phòng và phòng; Quản lý dịch vụ và đơn giá; Giữ phòng và quản lý tiền cọc; Quản lý hợp đồng và thành viên; Bàn giao phòng; Quản lý chỉ số điện nước; Quản lý phiếu báo phí; Tra cứu thông tin thuê; Thanh toán VietQR và báo chuyển khoản; Xác nhận thanh toán và đối chiếu giao dịch; Theo dõi công nợ và nhắc thanh toán; Quản lý sự cố; Gia hạn và điều chỉnh hợp đồng; Trả phòng, thanh lý và quyết toán; Quản lý thu chi và thống kê; Quản lý thông báo.
