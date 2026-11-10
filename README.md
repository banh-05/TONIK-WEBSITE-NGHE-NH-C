# 🎵 Tonik – Website nghe nhạc online

Đồ án môn **Phát triển ứng dụng Web (IS207)** – Trường Đại học Công nghệ Thông tin, ĐHQG-HCM (năm học 2024 – 2025).

**Tonik** là website nghe nhạc trực tuyến cho phép người dùng nghe nhạc theo bài hát, ca sĩ, album, thể loại và bảng xếp hạng; đồng thời có trang quản trị để quản lý nội dung và người dùng.

- Giảng viên hướng dẫn: ThS. Mai Xuân Hùng
- Nhóm thực hiện: Nhóm 9

## ✨ Tính năng

### Khách (chưa đăng nhập)
- Xem và nghe nhạc cơ bản, tìm kiếm bài hát / ca sĩ
- Đăng ký tài khoản, đăng nhập, quên mật khẩu

### Người dùng
- Phát nhạc: tua, chỉnh âm lượng, dừng, chuyển bài, lặp bài, phát ngẫu nhiên
- Xem chi tiết bài hát, ca sĩ, album, thể loại, bảng xếp hạng
- Lưu bài hát, ca sĩ, album yêu thích vào **Thư viện**
- Xem **lịch sử nghe**, chỉnh sửa hồ sơ cá nhân
- Chế độ sáng / tối, thu gọn sidebar, giao diện responsive (desktop và mobile)
- Tải trang bằng AJAX giúp nhạc phát liền mạch khi chuyển trang

### Quản trị viên (Admin)
- Dashboard quản trị
- Quản lý bài hát, ca sĩ, album, người dùng
- Liên kết bài hát – ca sĩ
- Upload file hình ảnh và audio

## 🛠️ Công nghệ sử dụng

| Phần | Công nghệ |
|---|---|
| Front-end | HTML, CSS, JavaScript, jQuery, AJAX |
| Back-end | PHP (MySQLi) |
| Cơ sở dữ liệu | MySQL (đạt chuẩn 3NF) |
| Bảo mật | Prepared statement (chống SQL Injection), phân quyền và kiểm tra SESSION |

## 🗂️ Cấu trúc thư mục

```
Group9-IS207/
├── blank_web/            # Source code website
├── media/                # Hình ảnh, audio, tài nguyên đa phương tiện
├── huongdansudung.pdf    # Hướng dẫn sử dụng
└── play_music.sql        # File cơ sở dữ liệu (cấu trúc + dữ liệu mẫu)
```

## 🗄️ Cơ sở dữ liệu

Gồm 12 bảng:

| Nhóm | Bảng |
|---|---|
| Bảng chính | `BaiHat`, `CaSi`, `Album`, `BangXepHang`, `TheLoai`, `Usr` |
| Bảng liên kết | `BaiHat_CaSi`, `BaiHat_TheLoai`, `BaiHat_BXH` |
| Bảng người dùng | `Usr_BaiHat`, `Usr_CaSi`, `Usr_Album` |
| Lịch sử | `LichSu` |

Các quan hệ chính: bài hát thuộc album / thể loại / bảng xếp hạng, bài hát của ca sĩ, người dùng yêu thích bài hát / ca sĩ / album và nghe bài hát (lịch sử nghe).

## 🚀 Cài đặt và chạy thử

### Yêu cầu
- [XAMPP](https://www.apachefriends.org/) (hoặc WAMP / Laragon) gồm Apache, PHP và MySQL

### Các bước

1. **Clone repo**
   ```bash
   git clone https://github.com/manh-nguyen-it/Group9-IS207.git
   ```
2. **Chép source** vào thư mục web server, ví dụ `C:\xampp\htdocs\Group9-IS207`
3. **Tạo database**
   - Bật Apache và MySQL trong XAMPP
   - Mở `http://localhost/phpmyadmin`, tạo database mới (ví dụ `play_music`)
   - Chọn **Import** → chọn file `play_music.sql` → **Go**
4. **Cấu hình kết nối CSDL**: mở file kết nối trong `blank_web/` và chỉnh lại host, user, password, tên database cho khớp với máy của bạn
5. **Chạy website**: truy cập `http://localhost/Group9-IS207/blank_web/`

> Chi tiết thao tác và ảnh minh họa xem trong file `huongdansudung.pdf`.

## 📸 Giao diện

Thêm ảnh chụp màn hình vào thư mục `media/screenshots/` rồi đặt tại đây, ví dụ:

```markdown
![Trang chủ](media/screenshots/home.png)
![Trang quản trị](media/screenshots/admin.png)
```

## 🔭 Hướng phát triển

- Triển khai lên cloud / hosting để người dùng truy cập công khai
- Tạo và quản lý playlist cá nhân
- Gợi ý bài hát, album, thể loại bằng học máy
- Biểu đồ thống kê cho quản trị viên
- Hiển thị lời bài hát, mở rộng sang mobile app

## 📚 Tài liệu tham khảo

- Tài liệu học tập môn Phát triển ứng dụng Web (IS207), Khoa Hệ thống thông tin, UIT
- [W3Schools](https://www.w3schools.com/) – HTML, CSS, JavaScript, jQuery, PHP

## 📄 Ghi chú

Dự án được thực hiện cho mục đích học tập. Hình ảnh và âm thanh trong dự án thuộc về chủ sở hữu tương ứng.
