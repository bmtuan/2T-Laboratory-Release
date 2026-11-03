# Changelog

## v0.8.3 — 2026-11-03

- **Flow xóa back: Lịch sử xoá trong app** — không ghi file txt vào folder output nữa. Mỗi video sau khi xoá được lưu lại và xem ở tab **Lịch sử** ngay trên trang Flow xóa back.
  - Lọc theo hôm nay / 7 ngày / 30 ngày / tất cả, theo kênh, theo trạng thái; tìm theo video id, nhạc hoặc file gốc; nhóm theo ngày.
  - Ghi cả các lần **xoá lỗi** (video vẫn còn trên kênh) kèm link để xoá tay.
  - Nút **Xuất CSV** theo bộ lọc đang chọn (mở được bằng Excel) và **Dọn cũ** để xoá dòng cũ hơn 90 ngày.
  - Tab tự cập nhật khi flow đang chạy xoá thêm video.
- **Kênh: cột Subs** — số subscriber của từng kênh lấy từ YouTube Studio (không mở Chrome), rê chuột xem thêm số video, lượt xem và thời điểm lấy.
  - Tự lấy ngay sau khi quét tài khoản; nút **Lấy subs** trên thanh công cụ, thanh chọn hàng loạt và từng dòng để cập nhật lại.
  - Kết quả được nhớ giữa các lần mở app; mở hộp "Kênh của tài khoản" cũng cập nhật vào cột.
- **Kênh: sắp xếp theo cột** — bấm tiêu đề Subs, Advanced hoặc Nhóm để sắp xếp tăng / giảm, bấm lần nữa để bỏ. Kênh chưa có số liệu hoặc chưa phân nhóm luôn nằm cuối.

## v0.8.2 — 2026-11-03

- Kích hoạt: hiển thị thêm số kênh đã quét của license trên máy này.
- Cải thiện bước kiểm tra license định kỳ và sau khi quét tài khoản.

## v0.8.1 — 2026-11-03

- Cài đặt → Cập nhật phần mềm: ghi chú phiên bản mới hiển thị đúng định dạng Markdown (đậm, danh sách, link) thay vì chữ thô.
- Đóng gói: `npm version` đồng bộ cả phiên bản trong backend/uv.lock.

## v0.8.0 — 2026-11-03

- **Tài khoản: profile Chrome riêng cho từng tài khoản** — mỗi tài khoản Google có một profile Chrome riêng, đăng nhập một lần dùng mãi.
  - Quét đăng nhập chạy trên profile của tài khoản, lưu tên / ảnh Google và cookie dự phòng.
  - Nút **Mở trình duyệt** bật Chrome thật với profile của tài khoản (mặc định vào Gmail); chưa có profile thì tự tạo từ cookie đã lưu.
  - Cài đặt: chọn thư mục chứa profile và trang mở mặc định; xoá profile theo từng tài khoản.
  - Xem chi tiết các kênh của tài khoản: link, tên, logo, số subscriber.
  - Quét tài khoản chạy tối đa 8 tài khoản cùng lúc, cửa sổ Chrome tự xếp trên màn hình.
- **Hàng đợi job** — thêm job mới khi đang có job chạy, job cùng loại xếp hàng chờ; thanh hàng đợi ở trang tác vụ để xem / dừng từng job.
  - Cài đặt: chỉnh số job chạy song song theo từng loại tác vụ, đổi được ngay khi đang chạy.
  - Không cho hai job cùng loại xử lý cùng một kênh; Flow add âm giữ input riêng mỗi job.
- **Lên lịch: quét trạng thái quảng cáo** — bước đặt lịch không còn tự bật quảng cáo và đặt mốc tự động. Video đang bật quảng cáo lúc quét được chèn mốc theo đúng cấu hình như tác vụ Chèn quảng cáo.
  - Thêm nút **Xoá hết** video khỏi bảng.
- Add âm, Flow add âm: nhớ folder nhạc và preset ngôn ngữ theo kênh, dùng chung giữa hai trang.
- Lên lịch, Chèn quảng cáo: tiêu đề video dài cắt ở giữa, nới cột checkbox cho dễ bấm.

## v0.7.0 — 2026-11-03

- **Tác vụ mới: Lên lịch** — đặt giờ công khai cho video nháp / riêng tư / không công khai (port trang "Lên lịch" của Reup Automation).
  - Quét video chưa có lịch của nhiều kênh, tuỳ chọn chỉ giữ video có ít nhất n bản lồng tiếng thành công; thấy số video mỗi kênh đã lên lịch sẵn.
  - Nhập giờ từng video hoặc "Đặt giờ hàng loạt" (ngày bắt đầu + khung giờ + cách nhau N ngày). YouTube tự công khai khi tới giờ, không cần mở app.
  - "Kiểm tra lịch hôm nay" đánh dấu kênh hôm nay chưa có video lên lịch hay công khai.
  - Bật AI để viết lại tiêu đề 80-99 ký tự và mô tả (cần license đã kích hoạt), và tạo thumbnail 1280x720 bằng Google Flow (prompt từ tiêu đề hoặc giống ảnh Google) trong cùng lượt lên lịch.
- **Tác vụ mới: Chèn quảng cáo** — đặt mốc quảng cáo giữa video (port trang "Set Ads" của YoutubeAutomationZ).
  - Quét video theo quyền riêng tư của nhiều kênh, hoặc dán ID / link video.
  - Mốc cố định `hh:mm:ss` (chip, bấm để bỏ) hoặc cách đều mỗi N phút; mốc vượt thời lượng video tự bị bỏ.
  - Tuỳ chọn **Vạch đầu cuối** (quảng cáo đầu và cuối video) và bật quảng cáo cho video trước khi chèn.
- **Studio → Tài khoản Flow** — quản lý tài khoản Google Flow dùng tạo thumbnail ngay trong app, kho dùng chung với Reup Automation: thêm (đăng nhập Google trong Chrome), làm mới phiên, bật / tắt, xoá.
- Trang Kênh: cột **Check Advanced** hiện trạng thái Advanced features (cơ bản / bậc trung / nâng cao) của từng kênh, kiểm tra được hàng loạt.
- Ẩn cửa sổ cmd nháy lên khi render gọi ffprobe / ffmpeg.
- Link tải bản mới nhất cố định: `releases/latest/download/2T.Lab_x64-setup.exe`.

## v0.6.1 — 2026-11-02

- **Sửa lỗi kích hoạt license**: bộ cài v0.6.0 mang theo backend cũ (v0.3.0) dùng product khác nên key 2T Lab bị báo "License không hợp lệ: invalid_license" và thiếu tác vụ Add âm. Bản này đóng gói đúng backend 0.6.1. Ai đã cài v0.6.0 chỉ cần cập nhật rồi kích hoạt lại.
- Quy trình đóng gói: `npm run desktop:build` giờ tự biên dịch backend trước khi build Tauri, không thể lệch phiên bản nữa.

## v0.6.0 — 2026-11-02

- **Tác vụ mới: Add âm** — thêm audio track cho video đã có sẵn trên kênh (port trang "Thêm âm thanh" của Reup Automation).
  - Quét video theo loại: nháp / riêng tư / đã lên lịch / không công khai / công khai.
  - Ghép mỗi video với file nhạc lệch thời lượng ít nhất (trong ngưỡng) ở folder nhạc của kênh, rồi tải nhạc gốc lên làm audio track cho từng ngôn ngữ.
  - Bỏ qua ngôn ngữ đã có bản thành công; tuỳ chọn xoá bản lỗi / đang xử lý trước khi thêm, chỉ lấy video có bản lỗi / đang xử lý, thêm cả bản descriptive.
  - "Quét + ghép" chỉ xem trước cặp ghép, không đụng tới YouTube.
  - Mỗi lần add thành công được ghi vào `audio_history.db` dùng chung để bộ giám sát của Reup add lại đúng file.
- Đổi tên hai tác vụ cũ thành **Flow add âm** và **Flow xóa back**.
- Quy trình phát hành: build trên máy, notes đăng ở repo 2T-Laboratory-Release; app tự kiểm tra bản cập nhật.

## v0.5.0 — 2026-11-02

- Release: version theo tag, đăng bản cập nhật ở repo public
  - Version 0.4.0. Nguồn duy nhất là package.json gốc: tauri.conf.json đọc
    thẳng từ file đó, scripts/sync-version.cjs chép sang frontend, backend,
    Cargo.toml và Cargo.lock.
  - Push tag vX.Y.Z là đủ để phát hành: workflow ghi version theo tag rồi mới
    build; build trên máy cũng lấy version từ tag trên HEAD nếu có.
  - Updater đọc latest.json từ bmtuan/2T-Laboratory-Release; workflow tạo
    release nháp ở repo đó bằng secret RELEASE_TOKEN (repo source giữ private).
