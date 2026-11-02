# Changelog

## v0.5.0 — 2026-11-02

- Release: version theo tag, đăng bản cập nhật ở repo public
  - Version 0.4.0. Nguồn duy nhất là package.json gốc: tauri.conf.json đọc
    thẳng từ file đó, scripts/sync-version.cjs chép sang frontend, backend,
    Cargo.toml và Cargo.lock.
  - Push tag vX.Y.Z là đủ để phát hành: workflow ghi version theo tag rồi mới
    build; build trên máy cũng lấy version từ tag trên HEAD nếu có.
  - Updater đọc latest.json từ bmtuan/2T-Laboratory-Release; workflow tạo
    release nháp ở repo đó bằng secret RELEASE_TOKEN (repo source giữ private).
