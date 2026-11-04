# Changelog

## v0.8.13 — 2026-11-04

- **Flow add âm: sửa dứt điểm lỗi báo thất bại dù đã add xong** — tìm ra nguyên nhân thật: trình biên dịch của bản cài đặt dịch sai một câu lệnh trong bước add, nên bản 0.8.12 vẫn báo "thất bại cả N ngôn ngữ" dù mọi track đã lên YouTube. Chạy từ mã nguồn thì không gặp nên các bản trước không bắt được. Đã viết lại câu lệnh và kiểm chứng trên bản biên dịch.

## v0.8.12 — 2026-11-04

- **Flow add âm / Add âm: hết báo thất bại dù track đã lên** — theo đúng cách TV Automation xử lý: YouTube nhận đăng ký track là tính xong; lỗi khi đẩy file âm chỉ ghi log, không đánh dấu thất bại và không add lại.
- **Flow: xem trước clip ngay khi chọn folder** — vừa chọn folder footage, khung bên phải hiện bảng clip sẽ xử lý (xen kẽ giữa các kênh như lúc chạy), kèm ghi chú kênh thiếu folder hoặc folder trống. Có nút chuyển qua lại với job gần nhất.
- **Bảng video của job có cột Kênh** riêng thay cho chữ nhỏ dưới tên video.

## v0.8.11 — 2026-11-03

- **Flow add âm: không add lại track đã lên** — khi request add báo lỗi, flow hỏi YouTube trước; track của ngôn ngữ đó đã có thì tính thành công ngay, không add thêm lần nào. Chỉ thử lại khi track thật sự chưa có.

## v0.8.10 — 2026-11-03

- **Flow add âm: hết báo thất bại dù đã add thành công** — khi request add track lỗi sau khi YouTube đã nhận (ví dụ upload file âm bị timeout), flow nay thử lại tối đa 4 lần như tác vụ Add âm; lần thử lại thấy track "đã có" sẽ tính là thành công.
- **Add âm: bỏ video chỉ trong đợt chạy** — bấm thùng rác chỉ loại video khỏi kết quả quét đang xem; bấm **Add âm** từ kết quả đó sẽ bỏ qua chúng. Không còn ghi nhớ sang lần sau: quét lại sẽ liệt kê đủ.

## v0.8.9 — 2026-11-03

- **Add âm: nút thùng rác chỉ bỏ video khỏi danh sách** — sửa lại so với v0.8.8: bấm thùng rác trên một dòng chỉ loại video đó khỏi kết quả quét, **không xoá video trên YouTube**. Video đã loại được ghi nhớ, các lần quét / add sau tự bỏ qua; khối "Đang bỏ qua N video" có nút **Quét lại tất cả** để bỏ loại trừ.

## v0.8.8 — 2026-11-03

- **Add âm: xoá video ngay trong bảng quét** — rê chuột lên dòng video, bấm thùng rác để xoá vĩnh viễn video đó trên YouTube (có hộp xác nhận). Dòng đã xoá được gạch ngang và lưu lại trong job. Chỉ dùng khi job đã chạy xong.
- **Kênh: chép tên kênh** — bôi đen được tên kênh trong bảng, hoặc bấm biểu tượng sao chép cạnh tên khi rê chuột.

## v0.8.7 — 2026-11-03

- **Add âm: xoá tất cả bản lồng tiếng hiện có** — mục "Bản lồng tiếng hiện có, trước khi thêm" cho chọn một trong ba: giữ nguyên, xoá bản lỗi / đang xử lý (như trước), hoặc **xoá tất cả bản hiện có** rồi thêm lại đủ các ngôn ngữ đã cấu hình.

## v0.8.6 — 2026-11-03

- **Sửa quét kênh bị sót** — tài khoản nhiều kênh trước đây có thể chỉ quét được 1–2 kênh khi Chrome còn đăng nhập (Studio mở vào kênh dùng lần cuối nên các kênh đứng trước bị bỏ qua). Giờ quét duyệt đủ mọi mục trong danh sách chuyển kênh và chờ Studio chuyển xong mới lấy thông tin. Log job ghi "Đã quét N kênh từ M mục" để đối chiếu.

## v0.8.5 — 2026-11-03

- **Lịch sử xóa back: cột "Đã qua"** — số ngày kể từ lúc xoá video, tô màu theo mốc: dưới 10 ngày đỏ, 10–20 ngày vàng, trên 20 ngày xanh. Rê chuột xem số ngày chính xác.

## v0.8.4 — 2026-11-03

- **Add âm: cột "Âm hiện có"** — bảng video hiện số audio track của từng video bằng icon: tích xanh đã xử lý, vòng xoay đang xử lý, X đỏ lỗi, kèm số ngôn ngữ còn thiếu. Rê chuột xem từng ngôn ngữ và trạng thái gốc của Studio.
- **Add âm: quét không cần folder nhạc** — nút **Quét + ghép** chỉ cần kênh và loại video. Chưa chọn folder nhạc vẫn quét được video và âm hiện có, chỉ chưa ghép. Nút **Add âm** vẫn yêu cầu folder nhạc và ngôn ngữ.

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
