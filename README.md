# AI-Fx580VNX

Bo mạch thay thế cho Casio fx-580VN X (ESP32-S3, TCA8418, e-paper 2,13", USB-C, pin LiPo). Đây là phần hoàn thiện nhất: **V8 USB_FIX1** (11/10/2026).

- `Hardware/FX580_Main_EPD_LAYOUT_V8/` — project KiCad 10.0.5 (sch/pcb/lib local, BOM/CPL, báo cáo ERC/DRC/CAM). Đọc `USB_FIX1_REPORTS/REVIEW_USB_FIX1.md` trước.
- `GOI_GERBER_FX580_V8_USB_FIX1_5PCB/` — Gerber/Excellon cho 5 PCB trống.
- `GOI_LAP_6_LINH_KIEN_FX580_V8_USB_FIX1_2BO/` — BOM/CPL lắp 6 linh kiện.
- `GOI_STENCIL_FX580_V8_USB_FIX1_65PARTS/` — stencil 65 linh kiện còn lại.
- `HUONG_DAN_SETUP_MURATA_FX580_V8/` — hướng dẫn đặt PCB/stencil.

Giới hạn: ERC/DRC = 0 nhưng chưa thử USB/ESD trên bo thật; toàn tuyến 90 Ω chưa được chứng minh. Chưa có firmware hoàn chỉnh. Các phiên bản V2–V7, trial và dữ liệu trung gian không đưa lên.
