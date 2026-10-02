# Lịch sử phiên bản

Bộ cài từng phiên bản nằm trong [`installers/`](installers/). Cập nhật: tải bộ cài mới và chạy đè lên bản cũ, cài đặt được giữ nguyên.

## 1.0.4 (02/10/2026)

[⬇ `tbh-auto-setup-1.0.4.exe`](https://github.com/levinhtxbt/tbh-auto/raw/main/installers/tbh-auto-setup-1.0.4.exe) · SHA256 `f18bd515933b0909c691d1e5c75a5f8286b412ae87f4d605fe48aff6052aeafa`

**Mới**

- **Báo lỗi / góp ý** (*Trợ giúp → Báo lỗi / góp ý...*, hoặc nút 🐞 trong *Giới thiệu*). App điền sẵn phiên bản, Windows, game, Remote Desktop, màn hình, trạng thái bot, lỗi gần nhất và 80 dòng log cuối, đồng thời ẩn tên user Windows. Sau đó bạn mở issue GitHub hoặc gửi email; app không tự gửi gì.
- **Treo máy mà vẫn dùng chuột**: *Bot → Trả chuột về chỗ cũ sau mỗi click* (mặc định bật). Bot chờ bạn ngừng dùng chuột / bàn phím 0,5 giây, click, rồi trả chuột và focus về cửa sổ bạn đang dùng. Khi bấm Space / Tab, bot cũng trả focus lại sau đó. Mỗi click chuột chỉ rời chỗ khoảng 0,1 giây.
- Ô kho / túi chỉ hiện icon kèm số lượng hoặc cấp trang bị, giống trong game. Muốn hiện tên đồ ngay trong ô thì bật *Hiển thị → Tên đồ trong ô*.
- App nhớ kích thước và vị trí cửa sổ. Nếu màn hình nhỏ đi (RDP từ máy khác, rút màn hình phụ), cửa sổ tự thu lại cho vừa.

**Sửa**

- Tìm được nút ở các mức zoom lẻ của UI (1.25x, 1.75x...).
- Chỉ số hero: *Block Chance* và *Damage Reduction* lấy từ cây năng lực giờ được tính đúng phần trăm.
- Link nhà phát hành, hỗ trợ và cập nhật trong *Settings → Apps* trỏ về repo này.
