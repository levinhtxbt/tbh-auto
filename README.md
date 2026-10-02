# tbh-auto

Auto cho **TBH: Task Bar Hero**: tự mở rương, cất đồ từ túi vào kho và sort, để bạn treo game mà túi không bao giờ đầy.

tbh-auto chỉ **nhìn màn hình** (chụp ảnh, nhận diện nút bằng OpenCV) và **bấm chuột như người**. Nó không đọc memory, không inject vào game, không đụng network, và chỉ *đọc* file save, không bao giờ ghi.

**Bản mới nhất: 1.0.4** (02/10/2026) · [⬇ Tải bộ cài `tbh-auto-setup-1.0.4.exe`](https://github.com/levinhtxbt/tbh-auto/raw/main/installers/tbh-auto-setup-1.0.4.exe) (~73 MB) · [Có gì mới](CHANGELOG.md)

*English: see [below](#english).*

> [!WARNING]
> Nhà phát triển game phạt rất nặng tài khoản dùng "chương trình trái phép" (khoá Steam Market vĩnh viễn, có thể khoá game). Bot chụp màn hình khó bị phát hiện hơn bot đọc memory, nhưng vẫn là vùng xám. Delay đều ngẫu nhiên và click có lệch vài pixel, nhưng **dùng là tự chịu rủi ro**.

## Bot làm gì

1. **Mở rương** khi thấy rương trên thanh taskbar của game (chuột phải). Nếu account đã học rune *Nhấn Space mở tất cả loại rương cùng lúc* và bật *Mở tất cả hộp hàng loạt* trong cài đặt game, bot bấm Space một lần để mở hết.
2. **Cất đồ vào kho** bằng nút *Kho đồ < Túi đồ*. Tab đang mở đầy thì bot tự chuyển sang tab còn chỗ (tối đa 7 tab).
3. **Sort** kho và túi. Cứ 3–5 phút bot cất đồ + sort một lần dù không có rương.
4. *(Tuỳ chọn)* **Tổng hợp đồ bằng Cube**: gộp 9 món cùng phẩm chất thành 1 món cao hơn, trong giới hạn phẩm chất bạn chọn.

Ngoài ra cửa sổ app cho xem đội hình, chỉ số hero (tính giống bảng chỉ số trong game), kho, túi, vàng, stage... đọc thẳng từ file save.

## Yêu cầu

- Windows 10 / 11, 64-bit. Windows 11 trên chip ARM cũng chạy được (Windows tự giả lập x64).
- Đã cài game *TBH: Task Bar Hero* (Steam).
- **Không** cần Python, **không** cần quyền admin.

## Cài đặt

1. Tải [`tbh-auto-setup-1.0.4.exe`](https://github.com/levinhtxbt/tbh-auto/raw/main/installers/tbh-auto-setup-1.0.4.exe).
2. Chạy file. Exe chưa được ký nên Windows SmartScreen có thể hiện *"Windows protected your PC"*: bấm **More info → Run anyway**.
3. Trong bộ cài:
   - **Thư mục cài**: để mặc định `%LOCALAPPDATA%\Programs\tbh-auto`, hoặc chọn thư mục khác như `C:\tbh-auto`. Không chọn được `Program Files`, vì app ghi cài đặt và log ngay cạnh nó.
   - Tick **Create a desktop shortcut** nếu muốn icon ngoài Desktop.
   - Tick **Get item icons & hero names from the installed game** (nên tick): sau khi cài, app đọc icon đồ, chân dung và tên hero từ game đã cài trên máy (chỉ đọc, không sửa file game).
4. Bấm **Finish** để mở tbh-auto. Lần sau mở từ Start menu hoặc Desktop.

Kiểm tra file tải về có đúng không (tuỳ chọn), trong PowerShell:

```powershell
Get-FileHash .\tbh-auto-setup-1.0.4.exe -Algorithm SHA256
```

Kết quả phải là `f18bd515933b0909c691d1e5c75a5f8286b412ae87f4d605fe48aff6052aeafa`.

### Cập nhật lên bản mới

Tải bộ cài bản mới và chạy đè lên bản cũ. Không cần gỡ trước. `config.yml`, cài đặt cửa sổ, vị trí chế độ mù và log được giữ nguyên. Nếu tbh-auto đang mở, bộ cài sẽ đóng nó trước khi thay file.

### Gỡ cài đặt

**Settings → Apps → Installed apps → tbh-auto → Uninstall.** Thao tác này xoá file đã cài và những file app tự tạo (icons, log, cài đặt). File save của game không bị đụng tới.

## Chạy lần đầu

1. **Mở game.** Mở cửa sổ **Kho đồ** (Stash) và cửa sổ **Hero** ở tab **Túi đồ** (Bag), để cả hai cùng hiện trên màn hình. Bot cần thấy nút *Kho đồ < Túi đồ* và các nút sort.
2. **Mở tbh-auto.** App tự tìm file save của game và hiện đội hình, kho, túi.
   Nếu lúc cài bạn không tick lấy icon: vào **Công cụ → Lấy icon & tên từ game**.
3. Bấm **🔍 Dò nút**. Bot đưa game lên trên, dò tỉ lệ UI (zoom 1x, 2x, 3x...) và tìm từng nút, rồi ghi kết quả ra khung Log. Nút nào không thấy sẽ có dòng cảnh báo màu cam.
4. *(Tuỳ chọn)* Tick **Bot → Dry-run** rồi Chạy bot để xem bot *định* bấm gì mà không bấm thật.
5. Bấm **▶ Chạy bot**. Chấm trạng thái ở góc dưới chuyển sang **xanh** là bot đang chạy.
6. Dừng bằng **■ Dừng**, hoặc kéo chuột vào **góc trên bên trái** màn hình (dừng khẩn cấp).

Màu chấm trạng thái (cả trên icon app): xám = chưa chạy · cam = đang chuẩn bị / dò nút / chờ màn hình · xanh = đang chạy · đỏ = lỗi, xem log.

Nút **🇻🇳 VI | 🇬🇧 EN** ở góc trên bên phải đổi ngôn ngữ giao diện và tên đồ / hero. Log luôn bằng tiếng Anh.

## Dùng hằng ngày

| Muốn... | Làm thế này |
|---|---|
| Vẫn dùng máy trong lúc bot chạy | **Bot → Trả chuột về chỗ cũ sau mỗi click** (mặc định bật). Bot đợi bạn ngừng dùng chuột / bàn phím 0,5 giây, click, rồi trả chuột và focus về cửa sổ bạn đang dùng. Mỗi click chuột chỉ rời chỗ khoảng 0,1 giây. |
| Tự tổng hợp đồ bằng Cube | **Bot → Tổng hợp đồ (Cube)...**: chọn phẩm chất tối đa, loại đồ, có lấy đồ trong kho không, bao lâu một lượt. Hộp thoại xem trước số bộ 9 món đủ điều kiện. Đồ đang mặc và đồ khoá bằng **Alt+Click** trong game không bao giờ bị dùng. |
| Treo bot trên máy khác qua Remote Desktop | **Công cụ → Remote Desktop → Giữ bot chạy khi đóng Remote Desktop**. Windows hỏi quyền admin một lần. Từ đó bấm X đóng RDP thì bot vẫn chạy. Chỉ muốn *thu nhỏ* cửa sổ RDP: chạy `rdp_client_keep_rendering.bat` (trong thư mục cài) trên **máy bạn đang ngồi**, rồi kết nối lại. |
| Xem chỉ số hero | Click **ⓘ** trên thẻ hero ở khung Đội hình. Click chân dung để xem cây năng lực, kỹ năng, đồ đang mặc. |
| Hiện tên đồ ngay trong ô kho / túi | **Hiển thị → Tên đồ trong ô** (cửa sổ rộng gần gấp đôi). Mặc định chỉ hiện icon + số lượng / cấp như trong game; click ô để xem chi tiết. |
| File save ở chỗ khác | **File save → Cài đặt file save...** Mặc định: `%USERPROFILE%\AppData\LocalLow\TesseractStudio\TaskBarHero\SaveFile_Live.es3`. |
| Xem bot đã làm gì | Khung Log, hoặc **Logs → Mở file log** (`tbh-auto.log` trong thư mục cài). **Logs → Chi tiết (DEBUG)** để log kỹ hơn. |

Cấu hình chi tiết (delay, phím mở Hero, bật / tắt từng tính năng...) nằm trong `config.yml` ở thư mục cài, mỗi dòng đều có chú thích. Sửa xong thì mở lại app.

### Thư mục cài có gì

| File | Là gì |
|---|---|
| `tbh-auto-gui.exe` | app (mở từ Start menu / Desktop) |
| `tbh-auto.exe` | bản dòng lệnh, chạy trong terminal: `tbh-auto.exe --help` |
| `config.yml` | cấu hình, sửa được; cập nhật bản mới vẫn giữ |
| `templates\` | ảnh mẫu các nút mà bot tìm trên màn hình |
| `icons\` | icon, tên và bảng dữ liệu lấy từ game của bạn |
| `tbh-auto.log` | log |
| `rdp_client_keep_rendering.bat` | cho phép thu nhỏ cửa sổ Remote Desktop mà bot vẫn chạy (chạy trên máy client) |
| `README.md` | tài liệu đầy đủ (mọi tuỳ chọn, cách nhận diện, dòng lệnh) |

## Xử lý sự cố

**Windows không cho chạy bộ cài / app.**
- SmartScreen: **More info → Run anyway**.
- Windows Defender cảnh báo: exe đóng gói bằng PyInstaller hay bị báo nhầm. Thêm thư mục cài vào danh sách loại trừ (Windows Security → Virus & threat protection → Exclusions) nếu bạn tin file này.
- *"An Application Control policy has blocked this file"*: máy bật **Smart App Control** (thường gặp ở Windows 11 cài mới). Smart App Control chặn mọi exe chưa ký và không có nút Run anyway. Muốn chạy thì phải tắt Smart App Control (Windows Security → App & browser control → Smart App Control). Lưu ý: trên một số bản Windows, tắt rồi phải cài lại Windows mới bật lại được.

**Dò nút báo không thấy nút.**
- Kho đồ và Hero (tab Túi đồ) phải *cùng hiện* trên màn hình, không bị cửa sổ khác che.
- Cửa sổ game ở zoom 1x cao khoảng 890 px. Màn hình thấp hơn thì giảm zoom trong game.
- Chạy lại **Dò nút** sau khi đổi zoom hoặc đổi độ phân giải.

**Bot dừng hoặc báo "chờ màn hình" khi dùng Remote Desktop.** Thu nhỏ hoặc đóng RDP làm Windows ngừng vẽ màn hình, nên bot không thấy gì để bấm. Xem dòng Remote Desktop trong bảng ở trên. Màn hình khoá / screen saver có mật khẩu cũng gây ra lỗi này.

**Không có icon đồ / tên hero.** Chạy **Công cụ → Lấy icon & tên từ game**. Nên chạy lại sau mỗi lần game cập nhật.

## Báo lỗi / góp ý

Trong app: **Trợ giúp → Báo lỗi / góp ý...** Viết vài dòng mô tả. App tự điền sẵn phiên bản, Windows, màn hình, trạng thái bot và 80 dòng log cuối (tên user Windows đã được ẩn). Sau đó bấm **Báo lên GitHub** hoặc **✉ Gửi email**. App không tự gửi gì, bạn xem lại rồi mới bấm gửi.

Hoặc mở issue trực tiếp: <https://github.com/levinhtxbt/tbh-auto/issues>.

## Ủng hộ

Nếu tool giúp được bạn: [☕ Buy Me a Coffee](https://buymeacoffee.com/levinhtxbt) (hoặc **Trợ giúp → Ủng hộ** trong app).

---

## English

**tbh-auto** opens chests, moves items from the bag to the stash and sorts both for *TBH: Task Bar Hero*, so you can leave the game running and never fill your bag. It only looks at the screen and moves the mouse like a person. It never reads game memory, injects code or touches network traffic, and it only *reads* the save file.

> [!WARNING]
> The developer bans accounts that use "unauthorized programs" (permanent Steam Market ban, possibly a game ban). Use it at your own risk.

**Install**

1. Download [`tbh-auto-setup-1.0.4.exe`](https://github.com/levinhtxbt/tbh-auto/raw/main/installers/tbh-auto-setup-1.0.4.exe). You need Windows 10 / 11 64-bit (Windows 11 on ARM works too) and the game installed. You don't need Python or admin rights.
2. Run it. If SmartScreen appears, click **More info → Run anyway**: the exe is not code-signed.
3. Keep the default folder or pick one like `C:\tbh-auto`; Program Files is not allowed. Tick **Get item icons & hero names from the installed game**.
4. To update later, run the newer installer over the old one. Your `config.yml` and settings are kept. To uninstall, go to **Settings → Apps → tbh-auto → Uninstall**.

**First run**

1. Start the game. Open the **Stash** window and the **Hero** window on the **Bag** tab, both visible on screen.
2. Open tbh-auto and switch the UI to **🇬🇧 EN** (top right).
3. Click **🔍 Scan buttons** and check the log for orange warnings.
4. Click **▶ Start bot**. To stop it, click **■ Stop**, or move the mouse to the top-left corner of the screen.

**Useful options**

- **Bot → Put the cursor back after each click** (on by default): you can keep using the PC while the bot runs.
- **Bot → Cube synthesis...**: combines 9 items of the same grade into one of a higher grade, up to the grade you choose.
- **Tools → Remote Desktop → Keep the bot running when Remote Desktop closes**: keeps the bot running on a remote PC after you close Remote Desktop.

**Problems or ideas?** In the app, use **Help → Report an issue...**, or [open an issue](https://github.com/levinhtxbt/tbh-auto/issues).
