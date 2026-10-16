# V8 USB_FIX1 — dữ liệu lắp linh kiện

Đã nhận vào project ngày **11/10/2026**, sau kiểm PCB/CAM cuối. Revision schematic vẫn mang ngày 10/10/2026.

Dùng **`BOM_JLCPCB_V8_USB_FIX1.csv` và `CPL_JLCPCB_V8_USB_FIX1.csv`**: 35 nhóm BOM, **71 linh kiện mỗi bo**, 71 vị trí Top. Quantity tính cho một bo. Tên file V7 trong thư mục `inherited_v7/` chỉ rõ nguồn lịch sử của các bản đối chiếu được giữ lại.

C25 thêm tụ VBUS–GND cục bộ cho U6 USBLC6-2SC6: **100 nF / 50 V / 10% / X7R / 0603, YAGEO CC0603KRX7R9BB104 / LCSC C14663**. Nhóm C8/C10/C12/C13/C14 thêm C25, quantity 5→6; các nhóm và mã linh kiện còn lại giữ nguyên.

C25 ở CPL **X 56,6 mm / Y −53,8 mm / Top / 270°**. X sang phải, Y lên trên từ auxiliary origin hiện hành. Vị trí PCB cục bộ đã đối chiếu native là `(56,6; 53,8)` với góc CAD 270°, không cộng model offset cho tụ này. Giữ nguyên byte toàn bộ 70 dòng CPL trước, gồm tâm housing J3/J4 và các model offset Q2/Q3/U4/U6. `C25_PIN_MAPPING_V8_USB_FIX1.csv` ghi pad 1 `/VBUS` `(56,6; −53,025)` và pad 2 `GND` `(56,6; −54,575)` theo tọa độ assembly.

`ROTATION_CORRECTIONS_V8_USB_FIX1.json` là chỉ mục góc hiện hành, trỏ tới CPL/BOM V8 và các chứng cứ kế thừa. Q2=180°, Q3=270°, U4=270°, U6=0°, L2=90°, R29/R30=270°, C18=0°, C25=270°. D1/D2=0° với cathode bên trái; D3=270° với cathode phía trên khi nhìn Top. Góc máy lắp vẫn phải đối chiếu pin 1/vạch cực trong actual matched-part preview.

## Chứng cứ kế thừa còn áp dụng cho linh kiện giữ nguyên

| Tệp trong `inherited_v7/` | Phạm vi |
|---|---|
| `DIODE_POLARITY_V7_BOOST2.csv/.png` | D1–D3, exact MBR0530T1G/C82046, pad K/A và vạch cathode; geometry linh kiện giữ nguyên |
| `PIN_MAPPING_V7_BOOST2.csv` | 217 dòng pad của 16 linh kiện cần chú ý; thêm C25 bằng file riêng, không coi đây là map đủ 71 linh kiện |
| `PIN1_MAP_V7_BOOST2.png` | Ảnh CAD lịch sử của các linh kiện giữ vị trí/góc; không chứa C25 |
| `ROTATION_CORRECTIONS.json` | Chứng cứ model offset V7 gốc; giữ nguyên nội dung, các đường dẫn lịch sử phải đọc theo project V7 gốc |
| `EXCLUDED_AND_MANUAL_767bdf1a.csv` | 62 thành phần bị loại khỏi BOM/CPL hoặc lắp thủ công, không thay trong USB_FIX1 |

Các bản này được copy nguyên byte; `SUPPORT_MANIFEST.json` ghi nguồn và SHA-256, xác nhận góc/cathode và mã diode khớp BOM/CPL V8. Scope check PCB cuối xác nhận toàn bộ footprint gốc giữ nguyên; xem `../USB_FIX1_REPORTS/SCOPE_CHECK.json`. Không copy ghi chú chế tạo V7 hoặc bảng bốn via dưới pad: chúng không mô tả V8 đã dời via.

## Kiểm dữ liệu đã hoàn tất

`ASSEMBLY_VALIDATION.json` xác nhận BOM/CPL có cùng 71 reference duy nhất, footprint khớp netlist 133 linh kiện; 62 thành phần loại trừ khớp bảng cũ. Mã LCSC có trong schematic đều khớp BOM, gồm C25. Có 16 thành phần kế thừa thiếu trường LCSC trong schematic nhưng BOM cũ có mã; đã liệt kê và giữ nguyên trường linh kiện. Fresh KiCad 10.0.5 ERC **0 lỗi / 0 cảnh báo**. Mọi XML linh kiện cũ và kết nối pin cũ khớp baseline.

Schematic: `FX580 V8 USB_FIX1 engineering DRAFT`, ngày 10/10/2026, SHA-256 `ee99d3e4a1b9a918ae5de7c29e8c223810441aa4a9b3986cfefdc51363b67eaa`. Chỉ C25 thay kết nối điện; chữ U6 và title/rev/date cũng được chỉnh để đọc rõ. `.kicad_pro` giữ nguyên byte. Chứng cứ schematic giao kèm tại `../USB_FIX1_REPORTS/C25_VALIDATION.json` và `C25_HANDOFF.json`. Kiểm native của PCB cuối nằm tại `../USB_FIX1_REPORTS/ELECTRICAL_ASSEMBLY_CHECK.json`.

Đây là dữ liệu assembly hiện hành, đã nhận sau kiểm PCB/CAM cuối. Source, gói V7/V8 cũ và bảng mua không sửa trong bước gom chứng cứ. Chưa có actual matched-part preview hoặc thử USB/ESD trên bo; **chưa chứng minh toàn tuyến 90 Ω**, chưa xác nhận toàn bộ phần cứng đủ điều kiện sản xuất. Gói Gerber hiện hành là `GOI_GERBER_FX580_V8_USB_FIX1_5PCB/FX580_V8_USB_FIX1_GERBER.zip` tại workspace, xuất từ PCB SHA-256 `e93aa1bd2bf7411eaec53a455c684dbb21c05adc65eddb268d3a5f1f0bc06f77`.
