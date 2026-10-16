# FX580 V8 USB_FIX1 — project hiện hành

Revision mới nhất hoàn tất ngày 11/10/2026. Mở **FX580_Main_EPD_LAYOUT_V8.kicad_pro** bằng KiCad 10.0.5; PCB và schematic cùng tên. Thư viện local dùng `${KIPRJMOD}/lib`.

Đã sửa routing D−/D+, cải thiện GND tham chiếu và thêm tụ C25 gần U6. ERC/DRC/unconnected/parity đều 0 theo rules hiện hành. CAM độc lập xác nhận 263 lỗ/slot, pad và 100 miền tiếp điểm của 50 phím. Chi tiết và giới hạn tại **USB_FIX1_REPORTS/REVIEW_USB_FIX1.md**; toàn tuyến 90 Ω và thử USB/ESD trên bo thật vẫn cần xác nhận.

BOM/CPL hiện hành: `assembly/BOM_JLCPCB_V8_USB_FIX1.csv` và `assembly/CPL_JLCPCB_V8_USB_FIX1.csv`, 35 nhóm / 71 linh kiện mỗi bo. `assembly/inherited_v7/` giữ chứng cứ vị trí/góc/cực của linh kiện không đổi; BOM V7 không bao gồm C25.

Gói Gerber mới trong workspace: `GOI_GERBER_FX580_V8_USB_FIX1_5PCB/FX580_V8_USB_FIX1_GERBER.zip`. Phạm vi 5 PCB trống / 0 PCBA / không stencil. Upload/quote JLCONE cũ chưa được thay trong lượt này.

V7 BOOST2 và V8 ngày 08/10 được giữ làm lịch sử. Project trước sửa nằm trong `usb_fix_20261010/V8_BEFORE_USB_FIX1.zip`; assembly cũ tại `usb_fix_20261010/assembly_before_usb/`. Ba file CAD ở root là bản hiện hành; `MANIFEST_SHA256.json` ghi hash các file giao. Bản ZIP project có đủ thư viện, BOM/CPL và báo cáo, không gồm các candidate/trial.
