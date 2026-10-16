# FX580 V8 USB_FIX1 — 5 PCB trống

Upload **FX580_V8_USB_FIX1_GERBER.zip**. Đây là Gerber mới nhất của projectV8, thay bảnV8 dời4via ngày08/10 cho các thay đổiUSB. File cũ được giữ làm lịch sử.

- 5 PCB riêng /0 PCBA /không stencil; 4 lớp/0,8mm/ENIG,65,100×132,777mm,8cutout.
- Đã làm gọn fanoutUSB, ghép cặp phíaMCU, thêmC25 100nF sátU6 vàviaGND; dời tuyến điều khiển để cải thiệnGND dướiUSB.
- KiểmKiCad10.0.5: ERC0/DRC0/unconnected0/parity0 theo rule hiện hành; rule/ignoredsettings giữ nguyên.
- CAMđộc lập: khớp263lỗ/slot, toàn bộpad và100miền tiếp điểm50phím;0viaholesunderpaste/0exposedviaholes.
- TụC25 làm BOMthành71linh kiện/bo. BOM+CPL nằm trong project, không dùng ở đơn5bo trống này.

Vẫn cần xác nhậntrở kháng trên stackupthực và thửUSB hai chiều cắm, nạpfirmware, truyền dữ liệu, ESD trên bo đãlắp. CADkhông chứng minh bo đạt90Ω hoặc đãqualified. Xem REVIEW_USB_FIX1.md để đọc phạm vi và các đoạn tham chiếu còn hạn chế.

Quote/uploadJLCONE ngày08/10 vẫn làGerberV8cũ; chưa thayfile hoặc đặt hàng trong lượt này. Giá cũ không phải báo giá củaUSB_FIX1.

SHA256ZIP: `b039c28f045806c5d328b72e4b0b51860ec67c10880f7635cf2fb1745c4a5aa3`
SHA256PCB: `e93aa1bd2bf7411eaec53a455c684dbb21c05adc65eddb268d3a5f1f0bc06f77`
