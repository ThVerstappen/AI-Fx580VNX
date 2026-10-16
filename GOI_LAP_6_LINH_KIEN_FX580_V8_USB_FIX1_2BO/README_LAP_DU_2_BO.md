# FX580 V8 USB_FIX1 — lắp sáu linh kiện trên đủ hai bo

Yêu cầu **2 bo PCBA**, mỗi bo lắp đủ **J4, L1, L2, Q3, U2 và U3**. Tổng 6 linh kiện/bo × 2 bo = **12 vị trí lắp**. Đây là lắp một phần BOM; 65 linh kiện còn lại trên mỗi bo do người dùng xử lý riêng.

| Vị trí | Mã hãng bắt buộc | Hãng | LCSC | Mỗi bo | Tổng 2 bo |
|---|---|---|---|---:|---:|
| J4 | FH12-24S-0.5SH(55) | HRS(Hirose) | C202112 | 1 | 2 |
| L1 | DFE252012F-R47M=P2 | Murata Electronics | C703140 | 1 | 2 |
| L2 | BCL322515RT-470M-D | TDK | C3220812 | 1 | 2 |
| Q3 | SI1308EDL-T1-GE3 | Vishay Intertech | C469327 | 1 | 2 |
| U2 | BQ24074RGTR | Texas Instruments | C54313 | 1 | 2 |
| U3 | TPS63802DLAR | Texas Instruments | C2845237 | 1 | 2 |

## File upload

- BOM: **BOM_FX580_V8_USB_FIX1_6PARTS.csv** — sáu dòng, Quantity=1 từng dòng, tính cho **một bo**.
- CPL: **CPL_FX580_V8_USB_FIX1_6PARTS.csv** — sáu vị trí Top, tọa độ/góc của **một bo**. Không nhân đôi dòng CPL hoặc Quantity khi chọn PCBA quantity=2.
- Chọn số lượng lắp **2 bo** trên biểu mẫu đặt hàng. Sau khi upload, kiểm đủ cả sáu reference được nhận và không bị bỏ lắp do thiếu hàng/không match part.

Nguồn là BOM/CPL V8 USB_FIX1 đã kiểm. Giữ nguyên từng byte dòng nguồn, gồm tâm housing J4 và góc Q3=270°, L2=90°. Tọa độ mm: X sang phải, Y lên trên từ auxiliary origin hiện hành. Không tự đổi origin hoặc góc.

Gerber tương ứng tại workspace: **GOI_GERBER_FX580_V8_USB_FIX1_5PCB/FX580_V8_USB_FIX1_GERBER.zip**. ZIP này là file PCB riêng; không upload ZIP BOM/CPL như Gerber. Hồ sơ Gerber cũ ghi 5 PCB trống; yêu cầu PCBA trong gói mới này là **2 bo lắp một phần**. Gói mới không thay hoặc cập nhật đơn/quote trên website. Nếu sản xuất 5 PCB thì chọn lắp sáu vị trí này trên 2 PCB; nếu sản xuất 2 PCB thì lắp cả hai.

## Yêu cầu gửi xưởng

Please assemble **2 boards**. Populate **all six positions J4, L1, L2, Q3, U2 and U3 on each board**, totaling 12 component placements. The BOM and CPL describe one PCB; set the assembly quantity to 2. Leave all other positions unpopulated under this partial assembly scope. Supply the exact manufacturer and MPN listed in the BOM. **U2 must be Texas Instruments BQ24074RGTR; U3 must be Texas Instruments TPS63802DLAR.** Do not silently substitute parts or skip a position. Confirm availability and the matched-part placement preview for all six positions, including pin 1 and orientation, before production.

Đoạn tiếng Anh là nội dung đã chuẩn bị để người dùng gửi; chưa gửi cho xưởng. Chưa có matched-part preview mới, quote, đặt hàng hay thanh toán. Những hạn chế kiểm thử phần cứng của project vẫn được giữ trong báo cáo USB_FIX1.

PCB SHA-256: `e93aa1bd2bf7411eaec53a455c684dbb21c05adc65eddb268d3a5f1f0bc06f77`

Gerber SHA-256: `b039c28f045806c5d328b72e4b0b51860ec67c10880f7635cf2fb1745c4a5aa3`
