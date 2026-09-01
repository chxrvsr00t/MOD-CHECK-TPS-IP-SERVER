# ModCheckIpTps (Minecraft Fabric 1.21.x)

Mod Minecraft Fabric hiển thị **Real Server TPS** và **Real IPv4 Server** ở góc dưới màn hình với hiệu ứng **Rainbow RGB**.

---

## Các tính năng chi tiết:

### 1. Đo TPS Server REAL (Không giả lập, tự động đo):
- **Multiplayer**: Bắt gói tin `WorldTimeUpdateS2CPacket` trực tiếp từ máy chủ để tính toán số tick thực tế server chạy được theo thời gian thực (`serverWorldTicks / elapsedSeconds`). Khi server lag hoặc bị delay packet, TPS sẽ tự động sụt giảm chính xác theo mức độ giật lag của server.
- **Singleplayer (Chơi đơn)**: Đo trực tiếp qua thời gian xử lý từng tick (MSPT - Milliseconds Per Tick) từ Integrated Server.

### 2. Tự động lấy IPv4 thật của Server:
- Không hiển thị domain tượng trưng (như `mc.hypixel.net` hay `play.example.com`).
- Lấy trực tiếp địa chỉ **IPv4 thực tế** từ kết nối mạng socket Netty (`ClientConnection.getAddress()`) hoặc giải mã DNS đa luồng nền sang địa chỉ IPv4 (ví dụ: `172.65.234.12` hay `103.x.x.x`).
- Nếu đang chơi **Singleplayer (Chơi đơn)**: Hiển thị chính xác là **`Null`**.

### 3. Hiệu ứng giao diện (HUD):
- Hiển thị ở góc dưới màn hình:
  - Dòng 1: `Tps: 20.0`
  - Dòng 2: `Ip server multi: 123.45.67.89` (hoặc `Null`)
- Hiệu ứng đổi màu cầu vồng **Rainbow RGB Wave** động theo thời gian.
- Khung nền bóng mờ giúp chữ luôn rõ nét và tự động ẩn khi bật F3.

---

## File Mod đã build hoàn chỉnh
File JAR sau khi build:
- **`build/libs/modcheckip-tps-1.0.0.jar`**

### Cách cài đặt:
1. Cài đặt **Fabric Loader** cho Minecraft 1.21.x (1.21.4 / 1.21.5).
2. Thêm mod **Fabric API** vào thư mục `.minecraft/mods/`.
3. Bỏ file `modcheckip-tps-1.0.0.jar` vào thư mục `.minecraft/mods/`.
4. Khởi động game và vào server để kiểm tra!
