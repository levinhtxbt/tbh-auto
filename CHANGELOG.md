<p align="center"><img src="assets/icon.png" width="64" alt="tbh-auto icon"></p>

# Changelog · Lịch sử phiên bản

Installers are attached to each [GitHub Release](https://github.com/levinhtxbt/tbh-auto/releases). To update, run the newer one over your version; your settings are kept.
Bộ cài được đính kèm trong từng [GitHub Release](https://github.com/levinhtxbt/tbh-auto/releases). Muốn cập nhật thì chạy bộ cài mới đè lên bản đang dùng; cài đặt được giữ nguyên.

## 1.0.8 · 2026-10-03

[⬇ `tbh-auto-setup-1.0.8.exe`](https://github.com/levinhtxbt/tbh-auto/releases/download/v1.0.8/tbh-auto-setup-1.0.8.exe) · SHA256 `6af5152c033ba475c83fd0720ce1a8a78a7ef36131eb01fb054786ed73a173f0`

### <img src="assets/flag_en.png" height="12" alt=""> English

**Fixed**

- 🖥️ **The game window no longer stays blown up after Remote Desktop reconnects.** When the Remote Desktop window was minimised, or the session moved to a VPS console (often 1024x768), the screen was smaller than the game for a moment. The game window then grew as wide as the next screen: its UI 2 to 3.5 times bigger, its top off the screen, and the bot (blind mode too) clicking in the wrong places. Now the bot:
  - notes the size of the game window when it starts;
  - puts the window back to that size whenever it is bigger than the screen, then finds the buttons again. It checks every round, when the screen comes back, and before each blind-mode run;
  - leaves the window alone if you change the zoom in the game and it still fits on the screen, or if the screen is smaller than the game itself (a 1024x768 console).

  If the game is already blown up when you start the bot, set its zoom back in the game first.

### <img src="assets/flag_vi.png" height="12" alt=""> Tiếng Việt

**Sửa**

- 🖥️ **Cửa sổ game không còn bị phóng to sau khi kết nối lại Remote Desktop.** Khi thu nhỏ cửa sổ Remote Desktop, hoặc phiên chuyển sang console của VPS (thường là 1024x768), có lúc màn hình nhỏ hơn cửa sổ game. Sau đó cửa sổ game giãn rộng bằng màn hình kế tiếp: UI to gấp 2 đến 3,5 lần, phần trên tràn khỏi mép màn hình, và bot (cả chế độ mù) bấm sai chỗ. Giờ bot:
  - ghi nhớ kích thước cửa sổ game lúc bắt đầu chạy;
  - đưa cửa sổ về lại kích thước đó mỗi khi nó to hơn màn hình, rồi dò lại các nút. Bot kiểm tra mỗi vòng, khi màn hình quay lại, và trước mỗi lượt chạy mù;
  - không đụng tới cửa sổ nếu bạn tự đổi zoom trong game mà cửa sổ vẫn nằm gọn trong màn hình, hoặc nếu màn hình nhỏ hơn chính cửa sổ game (console 1024x768).

  Nếu lúc chạy bot game đã bị phóng to sẵn, hãy chỉnh lại zoom trong game trước.

## 1.0.7 · 2026-10-02

[⬇ `tbh-auto-setup-1.0.7.exe`](https://github.com/levinhtxbt/tbh-auto/releases/download/v1.0.7/tbh-auto-setup-1.0.7.exe) · SHA256 `9e096275b8aef28a7e08e669b5eb3240832229bd730411ba20574b5d5e5a138d`

### <img src="assets/flag_en.png" height="12" alt=""> English

**Fixed**

- ⚗️ **Cube synthesis no longer skips a run when the Cube opens on another recipe.** The Cube reopens on the recipe used last (Crafting, Alchemy, Corrosion, ...), and the bot used to log a warning and do nothing. Now it picks Synthesis by itself and checks every step on screen:
  - It opens the recipe list and clicks the dropdown again if the list did not open.
  - It picks Synthesis and checks the blue gem next to the recipe name.
  - It tries up to 3 times. If Synthesis still cannot be picked, it saves what it saw to `debug/` (named in the log), closes the list and the Cube, and tries again on the next run.

### <img src="assets/flag_vi.png" height="12" alt=""> Tiếng Việt

**Sửa**

- ⚗️ **Tổng hợp Cube không còn bỏ lượt khi Cube mở ra ở công thức khác.** Cube mở lại ở công thức dùng lần trước (Chế tạo, Giả kim, Ăn mòn...), và bot cũ chỉ ghi cảnh báo rồi không làm gì. Giờ bot tự chọn Tổng hợp và kiểm tra từng bước trên màn hình:
  - Bot mở danh sách công thức, và bấm lại menu nếu danh sách chưa mở.
  - Bot chọn Tổng hợp rồi kiểm tra viên ngọc xanh cạnh tên công thức.
  - Bot thử tối đa 3 lần. Nếu vẫn không chọn được, bot lưu ảnh màn hình vào `debug/` (đường dẫn ghi trong log), đóng danh sách và Cube, rồi thử lại ở lượt sau.

## 1.0.6 · 2026-10-02

[⬇ `tbh-auto-setup-1.0.6.exe`](https://github.com/levinhtxbt/tbh-auto/releases/download/v1.0.6/tbh-auto-setup-1.0.6.exe) · SHA256 `c7cb51e592221f76390712f4e0d5b4f8e281be0a842ddb994025a8b211caf59e`

### <img src="assets/flag_en.png" height="12" alt=""> English

**New**

- 🔄 **tbh-auto updates itself.** At start-up (at most every 6 hours) and with *Help → Check for updates...*, it asks GitHub for the latest version. When a newer one is out, it shows what changed and offers **Update now**. That downloads the installer, checks its SHA256, installs it over your version (keeping `config.yml` and your settings) and opens the new version. Turn off the start-up check with *Help → Check for updates when the app starts*. This is the only connection tbh-auto makes.
- 📦 Installers are now attached to [GitHub Releases](https://github.com/levinhtxbt/tbh-auto/releases) instead of being stored in the repository.

Also contains the Cube fix of 1.0.5 below. Coming from 1.0.5 or older, install this version by hand once; after that, updates come through the app.

### <img src="assets/flag_vi.png" height="12" alt=""> Tiếng Việt

**Mới**

- 🔄 **tbh-auto tự cập nhật.** Khi mở app (tối đa 6 tiếng một lần) và khi chọn *Trợ giúp → Kiểm tra cập nhật...*, app hỏi GitHub bản mới nhất. Nếu có bản mới hơn, app cho xem có gì thay đổi và nút **Cập nhật ngay**. Nút này tải bộ cài, kiểm tra SHA256, cài đè lên bản đang dùng (giữ `config.yml` và các cài đặt) rồi mở bản mới. Tắt tự kiểm tra bằng *Trợ giúp → Tự kiểm tra cập nhật khi mở app*. Đây là kết nối duy nhất mà tbh-auto tạo ra.
- 📦 Bộ cài giờ được đính kèm trong [GitHub Releases](https://github.com/levinhtxbt/tbh-auto/releases) thay vì lưu trong repo.

Bản này có cả bản sửa Cube của 1.0.5 bên dưới. Nếu đang dùng 1.0.5 trở về trước, hãy tự cài bản này một lần; từ đó trở đi app tự cập nhật.

## 1.0.5 · 2026-10-02

*Replaced by 1.0.6, which contains this fix; no separate download. · Đã được thay bằng 1.0.6 (có bản sửa này); không còn tải riêng.*

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
