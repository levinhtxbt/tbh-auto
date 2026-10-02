<p align="center"><img src="assets/icon.png" width="64" alt="tbh-auto icon"></p>

# Changelog · Lịch sử phiên bản

Installers for every version are in [`installers/`](installers/). To update, run the newer installer over the old one; your settings are kept.
Bộ cài từng phiên bản nằm trong [`installers/`](installers/). Muốn cập nhật thì chạy bộ cài mới đè lên bản cũ; cài đặt được giữ nguyên.

## 1.0.4 · 2026-10-02

[⬇ `tbh-auto-setup-1.0.4.exe`](https://github.com/levinhtxbt/tbh-auto/raw/main/installers/tbh-auto-setup-1.0.4.exe) · SHA256 `f18bd515933b0909c691d1e5c75a5f8286b412ae87f4d605fe48aff6052aeafa`

### <img src="assets/flag_en.png" height="12" alt=""> English

**New**

- 🐞 **Report an issue** (*Help → Report an issue...*, or 🐞 in *About*). The app fills in the tbh-auto, Windows and game versions, Remote Desktop, screen, bot state, the last error and the last 80 log lines. Your Windows user name is hidden. You then open a GitHub issue or send an e-mail yourself; the app never sends anything on its own.
- 🖱️ **Use your PC while the bot runs**: *Bot → Put the cursor back after each click*, on by default. Before each click the bot waits until you leave the mouse and keyboard alone for 0.5 s. It then clicks and puts your cursor and focus back; key presses (Space / Tab) hand the focus back too. The cursor is away for about 0.1 s.
- 🖼️ Stash and bag cells now show only the icon with the count or item level, like in the game. To show item names in the cells, turn on *View → Item names in cells*.
- 🪟 The window remembers its size and position. If the screen got smaller (Remote Desktop from a smaller screen, a monitor unplugged), the window shrinks to fit.

**Fixed**

- 🔍 Buttons are now found at in-between UI zooms (1.25x, 1.75x...).
- 📊 Hero stats: *Block Chance* and *Damage Reduction* from the talent tree now count as the right percentage.
- 🔗 The publisher, support and update links in *Settings → Apps* now point to this repository.

### <img src="assets/flag_vi.png" height="12" alt=""> Tiếng Việt

**Mới**

- 🐞 **Báo lỗi / góp ý** (*Trợ giúp → Báo lỗi / góp ý...*, hoặc nút 🐞 trong *Giới thiệu*). App điền sẵn phiên bản tbh-auto, Windows và game, Remote Desktop, màn hình, trạng thái bot, lỗi gần nhất và 80 dòng log cuối. Tên user Windows được ẩn. Sau đó bạn tự mở issue GitHub hoặc gửi email; app không tự gửi gì.
- 🖱️ **Treo máy mà vẫn dùng chuột**: *Bot → Trả chuột về chỗ cũ sau mỗi click*, mặc định bật. Trước mỗi click, bot chờ bạn ngừng dùng chuột / bàn phím 0,5 giây. Sau đó bot click rồi trả chuột và focus về chỗ cũ; khi bấm phím (Space / Tab) bot cũng trả focus lại. Chuột chỉ rời chỗ khoảng 0,1 giây.
- 🖼️ Ô kho / túi giờ chỉ hiện icon kèm số lượng hoặc cấp trang bị, giống trong game. Muốn hiện tên đồ ngay trong ô thì bật *Hiển thị → Tên đồ trong ô*.
- 🪟 App nhớ kích thước và vị trí cửa sổ. Nếu màn hình nhỏ đi (Remote Desktop từ máy có màn hình nhỏ hơn, rút màn hình phụ), cửa sổ tự thu lại cho vừa.

**Sửa**

- 🔍 Giờ tìm được nút ở các mức zoom UI lẻ (1.25x, 1.75x...).
- 📊 Chỉ số hero: *Block Chance* và *Damage Reduction* lấy từ cây năng lực giờ được tính đúng phần trăm.
- 🔗 Các link nhà phát hành, hỗ trợ và cập nhật trong *Settings → Apps* giờ trỏ về repo này.
