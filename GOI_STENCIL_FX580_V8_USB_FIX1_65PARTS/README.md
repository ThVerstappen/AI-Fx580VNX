# Stencil tự hàn V8 USB_FIX1 sau khi xưởng lắp 6 linh kiện

1 tấm dùng lần lượt cho 2 bo. Top only, không khung, dày 0,12 mm, tấm 100 × 170 mm; căn bo đơn 65,1 × 132,777 mm giữa tấm. 65 linh kiện gồm 25 tụ, 29 trở và 11 linh kiện khác. Giữ nguyên 263 hình paste; bỏ 63 hình paste của J4/L1/L2/Q3/U2/U3.

**Phải duyệt CAM trước chế tạo.** File F.Paste đã có 5 cửa lớn tránh linh kiện lắp sẵn, trong đó L2/Q3 chung một cửa. Các cửa này để thân linh kiện đi qua, không phải vị trí in kem hàn. Cửa U2 theo thân RGT 3 × 3 mm + 0,15 mm mỗi cạnh; các cửa khác theo courtyard + 0,1 mm. Cần đối chiếu kích thước linh kiện thực và mối hàn; check độ bền các cầu thép. Kiểm hình CAM giữ đúng 263 hình paste và 5 cửa tránh; không nhận stencil tự suy từ F.Mask hoặc mở lại đủ 71 linh kiện.

Chỉ dùng bo đã tách rail. Đặt stencil cho thân linh kiện lắp sẵn đi qua cửa; kiểm tất cả vùng paste áp sát bo trước khi in. Che các cửa tránh từ phía trên để kem không rơi lên linh kiện; quét từng vùng bằng dụng cụ nhỏ tránh thân linh kiện nhô lên. Nếu không áp sát hoặc không thể quét vùng nào, vùng đó cần chấm kem bằng tay. Không quét một đường toàn bo qua các linh kiện nhô lên.

ZIP Gerber chỉ gồm F.Paste và Edge.Cuts (outline để tham chiếu, không cắt stencil theo biên bo). README, remark tiếng Anh, hình review, và validation ở ngoài ZIP. Đây là mục stencil độc lập, không thay BOM/CPL 6 linh kiện hoặc Gerber PCB. Chưa upload/đặt hàng/chưa được xưởng duyệt CAM.

Nguồn hướng dẫn: https://jlcpcb.com/help/article/instructions-for-stencil-order và https://jlcpcb.com/help/article/how-to-order-a-stencil .

Cập nhật sau chuẩn bị: người dùng đã cho phép và gói Gerber đã upload thành công lên JLCPCB ngày 11/10/2026, UI báo lưu Projects > Quotes. Chưa Save to Cart, gửi remark, đặt hàng hoặc được xưởng duyệt CAM. VALIDATION.json mô tả kiểm tra hình học ở thời điểm chuẩn bị; xem logs/JLCONE_STENCIL_UPLOAD_20261011.md cho trạng thái upload mới.
