<p align="center"><img src="assets/icon.png" width="64" alt="tbh-auto icon"></p>

# Changelog · Lịch sử phiên bản

Installers are attached to each [GitHub Release](https://github.com/levinhtxbt/tbh-auto/releases). To update, run the newer one over your version; your settings are kept.
Bộ cài được đính kèm trong từng [GitHub Release](https://github.com/levinhtxbt/tbh-auto/releases). Muốn cập nhật thì chạy bộ cài mới đè lên bản đang dùng; cài đặt được giữ nguyên.

## 1.0.5 · 2026-10-02

[⬇ `tbh-auto-setup-1.0.5.exe`](https://github.com/levinhtxbt/tbh-auto/releases/download/v1.0.5/tbh-auto-setup-1.0.5.exe) · SHA256 `0115d9dd4a8a7fddff26e477a4998b389226d77ccd6461f329bf6456a60c0570`

### <img src="assets/flag_en.png" height="12" alt=""> English

**Fixed**

- ⚗️ **Cube synthesis no longer skips good sets** right after a synthesis, which showed up in the log as *"Auto Fill put in COMMON, empty"*. The bot read the 9 cells while the Cube was still flashing white, and the flash looked like Common items. The fix has three parts:
  - The bot waits an extra 0.5 s after Auto Fill and after ↶ for the flash to fade. This is the new `timing.cube_settle` setting in `config.yml`; raise it on a slow VPS.
  - It reads the cells only once two looks in a row agree, and never takes the white flash for Common items.
  - If the grid is still only partly filled or mixed, it takes the items out and runs Auto Fill once more before giving up.

### <img src="assets/flag_vi.png" height="12" alt=""> Tiếng Việt

**Sửa**

- ⚗️ **Tổng hợp Cube không còn bỏ qua bộ hợp lệ** ngay sau một lần tổng hợp. Trong log lỗi này hiện ra là *"Auto Fill put in COMMON, empty"*. Nguyên nhân là bot đọc 9 ô khi Cube còn đang nháy trắng, và ô nháy trắng trông giống đồ Common. Bản sửa gồm ba phần:
  - Bot chờ thêm 0,5 giây sau Auto Fill và sau ↶ cho hiệu ứng nháy tắt hẳn. Đây là cài đặt mới `timing.cube_settle` trong `config.yml`; VPS chậm thì tăng lên.
  - Bot chỉ đọc khi hai lần nhìn liên tiếp giống nhau, và không bao giờ nhầm ô nháy trắng là đồ Common.
  - Nếu lưới vẫn thiếu ô hoặc lẫn phẩm chất, bot lấy đồ ra và thử Auto Fill thêm một lần rồi mới bỏ qua.

## 1.0.4 · 2026-10-02

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
