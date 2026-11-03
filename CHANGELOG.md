# Changelog

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
