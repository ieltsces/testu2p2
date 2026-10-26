# Lingo Cub Warm-up

Trang khởi động đầu giờ cho lớp Lingo Cub (Việt – Anh – Trung, trẻ 4–10 tuổi).
Các video YouTube tự phát nối tiếp nhau theo thứ tự. Có karaoke hiện lời theo nhạc.

## Có gì trong trang

- **Playlist tự chạy**: video 1 → video 2. Hết danh sách thì hiện màn hình "Great job! 太棒了！".
- **Nút điều khiển**: Trước / Phát – Tạm dừng / Tiếp, Toàn màn hình (để chiếu TV), Lặp lại cả danh sách.
- **Karaoke**: câu đang hát hiện to dưới video, chữ chuyển vàng dần theo nhạc; câu tiếp theo hiện nhỏ bên dưới. Có thể thêm dòng phụ (pinyin, nghĩa tiếng Việt).
- **Soạn lời karaoke** (dành cho giáo viên): dán lời, chạm theo nhạc để canh giờ, tải lại trang đã có lời.

## Đưa lên GitHub Pages

1. Tạo repo mới, ví dụ `warm-up`, chọn **Public**.
2. Bấm **Add file → Upload files**, tải lên `index.html` và `README.md`, bấm **Commit changes**.
3. Vào **Settings → Pages**. Ở mục *Branch* chọn `main`, thư mục `/ (root)`, bấm **Save**.
4. Đợi 1–2 phút, trang sẽ có địa chỉ:
   `https://<tên-tài-khoản>.github.io/warm-up/`

> Phải mở trang qua địa chỉ GitHub. Nếu mở file trực tiếp trên máy (bấm đúp file), YouTube thường không cho phát video nhúng.

## Thêm lời karaoke cho một bài

1. Mở trang trên GitHub, bấm vào video cần soạn trong Playlist.
2. Mở mục **Soạn lời karaoke** ở dưới video.
3. Dán lời bài hát, **mỗi câu một dòng**. Muốn thêm dòng phụ thì viết sau dấu `|`:

   ```
   Hello, hello, how are you? | Xin chào, bạn khỏe không?
   你好，你好 | nǐ hǎo, nǐ hǎo
   ```

4. Bấm **Bắt đầu canh giờ**. Video chạy lại từ đầu.
5. Mỗi khi một câu **bắt đầu được hát**, chạm nút xanh (hoặc phím **Space**). Chạm nhầm thì bấm **Lùi 1 câu**.
6. Hết bài (hoặc bấm **Dừng canh giờ**), lời được lưu kèm mốc giờ dạng `[00:12.40]`.
7. Chữ hiện lệch nhạc thì dùng **Sớm hơn / Muộn hơn 0,2 giây**.
8. Làm xong các bài, bấm **Tải trang đã có lời**. Máy tải về file `index.html` mới.
9. Lên repo, bấm **Add file → Upload files**, tải file `index.html` mới lên (thay file cũ), **Commit changes**.

> Lời soạn trong trang chỉ lưu trên máy của cô. Học sinh chỉ thấy karaoke sau bước 8–9.

Có thể sửa tay mốc giờ hoặc chữ trong ô lời, rồi bấm **Lưu lời đã sửa**.

## Thêm, bớt hoặc đổi thứ tự video

Mở `index.html` (trên GitHub bấm vào file → biểu tượng bút chì), tìm đoạn:

```js
const VIDEOS = [
  { id: "6VR4bW2nX_4", title: "" },
  { id: "wED_ZaR8l2U", title: "" },
];
```

- `id` là phần sau `watch?v=` trong link YouTube.
  Ví dụ `https://www.youtube.com/watch?v=6VR4bW2nX_4` → `6VR4bW2nX_4`.
- `title` để trống thì trang tự lấy tên video; muốn đặt tên riêng thì điền vào, ví dụ `title: "Hello Song"`.
- Thứ tự các dòng là thứ tự phát.

Nếu thêm video mới, cô thêm cả một dòng tương ứng trong phần `karaoke-data` (ngay phía trên), ví dụ `"mã-video-mới": ""`. Nếu quên cũng không sao: nút **Tải trang đã có lời** sẽ tự thêm.

## Khi có lỗi

| Hiện tượng | Cách xử lý |
|---|---|
| Video báo "không phát được" rồi tự chuyển bài | Chủ kênh không cho nhúng video. Thay bằng video khác. |
| Video không chạy khi mở file trên máy | Mở bằng địa chỉ `github.io`. |
| Đã soạn lời nhưng học sinh không thấy | Chưa tải lại `index.html` mới lên GitHub (bước 8–9). |
| Sửa file xong trang chưa đổi | Đợi 1–2 phút rồi tải lại trang (Ctrl+F5). |
