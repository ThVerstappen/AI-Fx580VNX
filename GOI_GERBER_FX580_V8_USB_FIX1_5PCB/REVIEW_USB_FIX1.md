# FX580 V8 USB_FIX1 — bản CAD hiện hành, hoàn tất 11/10/2026

Đã nhận bản đã kiểm vào **Hardware/FX580_Main_EPD_LAYOUT_V8/** và xuất Gerber mới cho **5 PCB trống / 0 PCBA / không stencil**. Đây là revision CAD mới nhất. V7 BOOST2, snapshot V8 dời bốn via ngày 08/10 và các ZIP cũ được giữ nguyên. Project V8 trước sửa được lưu trong `usb_fix_20261010/V8_BEFORE_USB_FIX1.zip`.

## Thay đổi đã nhận

- Fanout D−/D+ quanh U6: 59 đoạn thay bằng 6 đoạn. Các bậc thang USB trên F.Cu được làm gọn thêm từ 40 đoạn thành 8 đoạn. Giữ đoạn cổ hẹp tại R4 vì nối thẳng không đủ clearance 0,15 mm.
- Cặp USB phía MCU: đoạn giữa có width 0,26 mm / gap 0,20 mm, chiều dài song song chồng nhau 2,914 mm; fanout ngắn rộng 0,20 mm. Chênh đường tâm riêng đoạn MCU giảm từ 0,104 xuống 0,091 mm.
- Thêm C25 **100 nF / 50 V / 10% / X7R / 0603, YAGEO CC0603KRX7R9BB104 / LCSC C14663**, giữa VBUS–GND gần U6. Tâm cục bộ (56,6; 53,8) mm, góc 270°; pad 1 VBUS tại (56,6; 53,025), pad 2 GND tại (56,6; 54,575). Đường tâm U6.5→C25.1 dài 5,239 mm; nhánh GND đến via gần dài 1,025 mm.
- Thêm hai via GND tại (55,6; 54,8) / (55,1; 62) mm. Khoảng cách đến hai chuyển lớp D+ tương ứng 0,650 / 1,160 mm. Cả hai nối đồng GND F.Cu/In1.Cu/In2.Cu.
- Dời USB_ILIM_EN trên In1.Cu khỏi vùng dưới cặp MCU. Dời KP_COL7 sang hành lang B.Cu giữa các phím: đoạn dưới U6 dùng hai via mới tại (51,9; 58,15) / (57; 57,8); hai crossing còn lại dùng ba via có sẵn. Tổng cộng thêm bốn via (hai GND, hai KP_COL7), Ø0,5 mm / drill 0,3 mm, tented hai mặt, không chồng pad hoặc phím.
- Schematic chỉ thêm C25 về điện; chữ U6 và title/revision được chỉnh để đọc rõ. BOM có **35 nhóm / 71 linh kiện mỗi bo**, CPL có 71 vị trí Top. Giữ nguyên byte 70 dòng CPL cũ và các model offset/góc đã đối chiếu.

## Kết quả kiểm bản cuối

| Hạng mục | Kết quả |
|---|---|
| KiCad 10.0.5 ERC / refill DRC / unconnected / parity | **0 / 0 / 0 / 0**, theo rules và ignored settings hiện hành; PRO giữ nguyên byte, không nới rule |
| Schematic và pad–netlist | 132 thành phần / 424 kết nối pin cũ khớp; chỉ thêm C25 và hai pin, tổng 133 thành phần / 426 pin / 102 net |
| Phạm vi PCB | 131 block footprint gốc và 3073 route object gốc giữ nguyên; pad/phím, stackup/setup, zone boundary/rule và outline không đổi |
| CAM độc lập Gerbonara/Shapely | 9 Gerber + 2 Excellon + gbrjob; outline kín 65,100 × 132,777 mm, 8 cutout; không có đồng ngoài biên |
| Lỗ/slot | 263 khớp CAD: 255 via + 4 PTH slot + 4 NPTH; via drill 0,3 mm, đường kính đồng 216 × Ø0,6 mm và 39 × Ø0,5 mm |
| Pad CAM | 445 entry / 427 nhóm (layer/ref/pad) khớp native, gồm hai pad C25; sai số biên lớn nhất 0.001039 mm |
| Phím | 50 phím / 100 miền tiếp điểm giữ nguyên Gerber; khe nhỏ nhất 0.349902 mm; B.Mask và toàn bộ đồng hở mặt phím giữ geometry |
| Via dưới F.Paste / lỗ via hở F/B.Mask | **0 / 0**; B.Paste rỗng; không giao stencil |
| Mười đoạn B.Cu mới và vùng phím | Không chồng envelope phím; khoảng cách nhỏ nhất tới envelope 0,030732 mm; clearance tới pad thực đã qua DRC |
| Gói giao | CRC, từng member và manifest được kiểm sau đóng gói; chứng cứ tại PACKAGE_CHECK.json / PROJECT_PACKAGE_CHECK.json |

Độ dài đường tâm J1.A7→MCU D− giảm **43,816331→43,367981 mm**; J1.A6→MCU D+ giảm **46,733099→44,579605 mm**. Vẫn có bốn via D− / ba via D+. Phép tính bỏ thân điện trở và chiều Z của via, nên không phải kết quả đo lệch pha. Các nhánh B7/B6 được ghi riêng trong `ELECTRICAL_ASSEMBLY_CHECK.json`.

## GND tham chiếu và giới hạn

Lấy mẫu điểm giữa với bước ≤0,025 mm trên F.Cu, kiểm đồng GND đã fill trên In1.Cu tại cùng XY:

| Net | V8 trước sửa: đoạn thiếu GND (mm) | USB_FIX1 (mm) |
|---|---:|---:|
| /USB_DM | 7.106353 | 4.019491 |
| /USB_DP | 4.337616 | 1.337108 |
| /USB_DM_MCU | 0.764667 | 0.000000 |
| /USB_DP_MCU | 0.775000 | 0.000000 |

KP_COL7 không còn gây khe dưới tim tuyến USB ở các crossing đã xử lý. D− còn khoảng 0,6 mm chịu khe CHG_ILIM; phần lớn khoảng trống còn lại là đồng USB và antipad của via. Các đoạn USB trên lớp trong vẫn chia sẻ vùng tham chiếu với tín hiệu khác. Phép lấy mẫu này kiểm geometry GND, chưa mô tả đầy đủ dòng hồi hoặc coupling.

Trial dời KP_COL7 có 70 hàng lấy mẫu lệch tim không mất thêm GND. Sau khi làm thẳng USB, một số mẫu lệch ±0,25/±0,5 mm tăng nhẹ đoạn thiếu GND (<0,074 mm). Vì vậy kết quả cải thiện được trình bày theo từng phép đo, không suy thành GND liên tục trên toàn tuyến.

**Toàn tuyến 90 Ω ±10% chưa được chứng minh.** Cần chốt stackup thực và trích xuất SI/TDR nếu yêu cầu xác nhận trở kháng. Width/gap, DRC hoặc phép tính F.Cu lý tưởng chưa đủ. Chưa có bo thật để xác nhận USB/ESD.

## Việc cần kiểm trên bo đã lắp

- Kiểm short, VBUS và 3V3 trước/sau cấp nguồn; ghi dòng và điện áp theo trạng thái nguồn.
- Nhận thiết bị, cắm/rút/reset, **cả hai chiều cắm USB-C**; lưu log.
- Nạp và verify firmware; truyền dữ liệu có kiểm payload/hash; thử boot/reset/sleep–wake. Ghi firmware, cáp, máy tính và lỗi thực.
- Thử ESD theo mức và protocol đã chốt; ghi recovery/hư hỏng, kiểm USB trước/sau.

Cell, boost/thermal, firmware và fit vỏ/màng phím vẫn là các việc riêng của project. Kết quả này xác nhận CAD/CAM local; chưa xác nhận thử nghiệm phần cứng hoặc CAM sản xuất của nhà máy.

## Nguồn và gói giao

PCB SHA-256: `e93aa1bd2bf7411eaec53a455c684dbb21c05adc65eddb268d3a5f1f0bc06f77`

SCH SHA-256: `ee99d3e4a1b9a918ae5de7c29e8c223810441aa4a9b3986cfefdc51363b67eaa`

PRO SHA-256: `ec4bf0921a5091743d0572d866287cb1acbb657c42332ae2b982302fcb21551a`

- Project có thư viện local và BOM/CPL: **Hardware/FX580_Main_EPD_LAYOUT_V8_USB_FIX1_PROJECT.zip**.
- Gerber 5 bo trống: **GOI_GERBER_FX580_V8_USB_FIX1_5PCB/FX580_V8_USB_FIX1_GERBER.zip**.
- Nguồn xuất và checks đầy đủ: `usb_fix_20261010/exports_release_20261011/`; báo cáo giao kèm nằm trong `USB_FIX1_REPORTS/`.

Đã xem ảnh CAM mặt trước, mặt phím, hai lớp trong và zoom USB/GND của đúng revision. Chỉ xử lý local; upload/quote JLCONE ngày 08/10 vẫn là V8 cũ và chưa được thay bằng USB_FIX1. Các giá cũ không phải báo giá cho gói mới.
