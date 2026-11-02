# Changelog

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
