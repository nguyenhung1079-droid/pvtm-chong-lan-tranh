# Chuyên mục bài viết chống lẩn tránh biện pháp phòng vệ thương mại và gian lận xuất xứ

Website HTML tĩnh gồm 20 bài viết, phục vụ hiển thị chuyên mục và nhúng vào website Cục Phòng vệ thương mại.

Cập nhật tài liệu hướng dẫn: **16/10/2026 — giờ Việt Nam**.

## 1. Các đường dẫn quan trọng

| Nội dung | Đường dẫn |
|---|---|
| Website | [Mở chuyên mục](https://nguyenhung1079-droid.github.io/pvtm-chong-lan-tranh/index.html) |
| Kho mã nguồn | [pvtm-chong-lan-tranh](https://github.com/nguyenhung1079-droid/pvtm-chong-lan-tranh) |
| Trang thử khung nhúng | [thu-frame.html](https://nguyenhung1079-droid.github.io/pvtm-chong-lan-tranh/thu-frame.html) |
| Bản ghi trạng thái | [TRANG_THAI_2026-10-16_1719.md](TRANG_THAI_2026-10-16_1719.md) |
| Nhánh backup | [backup-2026-10-16-1720](https://github.com/nguyenhung1079-droid/pvtm-chong-lan-tranh/tree/backup-2026-10-16-1720) |
| Tải backup | [Bản ZIP ngày 16/10/2026, 17:20](https://github.com/nguyenhung1079-droid/pvtm-chong-lan-tranh/archive/refs/heads/backup-2026-10-16-1720.zip) |

Trang đích dự kiến nhúng trên website Cục:

[Trang chuyên mục trên pvtm.gov.vn](https://pvtm.gov.vn/default.aspx?page=news-detail&do=detail&category_id=2a2f39c9-2f9e-46e2-bb2d-3e974778f666&id=f9966ab3-7bcd-4c49-ad6f-be08e9f6d306)

**Trạng thái nhúng:** đã chuẩn bị mã iframe; chưa xác minh việc lưu mã trong quản trị Cục hoặc hiển thị thực tế trên trang đích.

## 2. Công nghệ và dữ liệu

- HTML, CSS và JavaScript chạy trên trình duyệt.
- Triển khai bằng GitHub Pages.
- Không có cơ sở dữ liệu riêng, không cần máy chủ ứng dụng.
- Nội dung bài nằm trong các tệp HTML.
- Các hình ảnh hiện có được nhúng trực tiếp trong HTML bằng dữ liệu base64; khi sao lưu phải giữ toàn bộ tệp, không cắt bớt chuỗi dữ liệu ảnh.
- Các tài liệu Word nguồn không mặc nhiên nằm trong kho này; cần giữ riêng bản gốc nếu muốn đối chiếu hoặc biên soạn lại.

## 3. Cấu trúc tệp

| Tệp | Chức năng |
|---|---|
| `index.html` | Danh sách đủ 20 bài, ngày đăng và ô tìm kiếm |
| `bai-01.html` đến `bai-20.html` | Nội dung chi tiết từng bài |
| `style.css` | Giao diện và định dạng chung |
| `thu-frame.html` | Trang thử hiển thị trong iframe |
| `.nojekyll` | Cho phép GitHub Pages phục vụ website tĩnh trực tiếp |
| `TRANG_THAI_2026-10-16_1719.md` | Ghi nhận trạng thái đã chốt và mốc mã nguồn |
| `README.md` | Thông tin vận hành và bàn giao |

## 4. Giao diện đã chốt

### Trang danh sách

- Không hiển thị tiêu đề chuyên mục lớn trong vùng nội dung.
- Không hiển thị thống kê “20 bài viết” hoặc số kết quả.
- Giữ ô tìm kiếm theo tiêu đề; hỗ trợ chữ có dấu và không dấu.
- Giữ nguyên tiêu đề bài viết; không thêm “Bài 1”, “Bài 2”… vào tiêu đề.
- Không hiển thị nhãn “Đã có nội dung”.
- Ngày đăng dùng năm 2026.

### Trang chi tiết

- Liên kết về danh sách mang tên **Quay lại chuyên mục**.
- Đã bỏ dãy tab bài viết ở cả đầu và cuối bài.
- Giữ điều hướng Bài trước/Bài sau ở cuối bài.
- Nội dung, bảng, hình ảnh và chú thích được giữ khi chỉnh giao diện.

### Định dạng dùng chung

| Thành phần | Thiết lập |
|---|---|
| Phông chữ | Arial, Helvetica, sans-serif |
| Nội dung trên máy tính | 17px |
| Nội dung trên điện thoại | 16px, tại chiều rộng tối đa 700px |
| Giãn dòng | 1,7 |
| Khoảng cách sau đoạn | 16px |
| Đoạn văn, danh sách | Căn đều hai bên |
| Đề mục trong bài | In đậm, cùng cỡ chữ nội dung |
| Ngày đăng, nguồn | Định dạng riêng, căn trái |
| Nội dung ô bảng | Căn trái; bảng có thể cuộn ngang |
| Hình ảnh | Giữ tỷ lệ, không vượt chiều rộng nội dung |

Thay đổi định dạng chung tại `style.css`, tránh sửa lặp lại từng bài.

## 5. Mã nhúng vào website Cục

Trong trang quản trị, mở bài viết đích, chọn chế độ **HTML/Mã nguồn**, dán đoạn sau tại vị trí cần hiển thị:

```html
<iframe
  src="https://nguyenhung1079-droid.github.io/pvtm-chong-lan-tranh/index.html"
  title="Chuyên mục Bài viết chống lẩn tránh biện pháp phòng vệ thương mại và gian lận xuất xứ"
  width="100%"
  height="1400"
  style="display:block;width:100%;border:0;background:#fff;"
  loading="lazy">
</iframe>
```

- Liên kết nội bộ mở bài trong khung; “Quay lại chuyên mục” trở về index.
- Chiều cao 1400px có thể chỉnh theo bố cục trang đích.
- Đây là khung có chiều cao cố định; nội dung dài có thể tạo thanh cuộn.
- Chưa triển khai tự động điều chỉnh chiều cao giữa hai tên miền.
- Nếu khung biến mất sau khi lưu, kiểm tra trình soạn thảo có loại bỏ thẻ iframe hoặc website có chặn nhúng hay không.
- Trang thử iframe chỉ giúp kiểm tra khung thử; không thay thế kiểm tra trên website Cục.

## 6. Cách cập nhật

### Sửa nội dung một bài

1. Xác định đúng tệp `bai-XX.html`.
2. Sửa phần nội dung trong `<article>...</article>`.
3. Giữ nguyên hình ảnh, bảng, chú thích và đường dẫn liên quan.
4. Nếu đổi tiêu đề, cập nhật cả thẻ title, tiêu đề h1 và liên kết tương ứng trên index.
5. Nếu đổi ngày đăng, cập nhật cả nội dung hiển thị và thuộc tính datetime; kiểm tra mọi vị trí ngày đăng trong bài.
6. Xem trước rồi commit với mô tả rõ ràng.

### Thêm bài mới

1. Tạo tệp theo mẫu trang chi tiết hiện tại.
2. Liên kết với `style.css`; dùng UTF-8 và `lang="vi"`.
3. Thêm tiêu đề, ngày đăng và liên kết vào danh sách trong index.
4. Cập nhật điều hướng bài trước/bài sau.
5. Không đưa trở lại tiêu đề chuyên mục, thống kê số bài hoặc dãy tab nếu chưa có yêu cầu mới.

### Sửa giao diện

1. Sửa `style.css`.
2. Kiểm tra bài có nhiều bảng, bài có hình và bài có danh sách.
3. Kiểm tra ở chiều rộng máy tính và điện thoại.
4. Giữ nguyên nội dung và ngày tháng ngoài phạm vi yêu cầu.

Sau khi cập nhật, theo dõi quá trình triển khai trong GitHub Actions/Pages nếu có. Khi bản triển khai hoàn tất, tải lại trang; trên Windows có thể dùng **Ctrl + F5**.

## 7. Kiểm tra trước khi bàn giao

- Số lượng liên kết trên index khớp các bài thực tế.
- Tiêu đề, ngày đăng và nội dung khớp tài liệu đã được xác nhận.
- Không mất đoạn cuối, bảng, hình ảnh hoặc nguồn.
- Không có liên kết sai hoặc bài trước/bài sau không tồn tại.
- Tìm kiếm hoạt động, kể cả khi không có kết quả.
- Không có JavaScript còn tham chiếu đến bộ đếm đã xóa.
- Hiển thị trên điện thoại phù hợp; bảng không làm vỡ trang.
- Kiểm tra trang nhúng thực tế khi có quyền truy cập.
- Không kết luận nội dung chuyên môn đã được kiểm chứng chỉ từ việc kiểm tra giao diện.

## 8. Mốc trạng thái và sao lưu

| Mốc | Thông tin |
|---|---|
| Mã nguồn giao diện đã chốt | `90323ec64e0692959511d423363a2ef0dfdcce3d` |
| Mã nguồn kèm bản ghi trạng thái | `64078e348ea48110338b7c245fa333db60cb2641` |
| Nhánh backup ngày 16/10/2026, 17:20 | `backup-2026-10-16-1720` |

Nhánh backup được tạo từ commit `64078e348ea48110338b7c245fa333db60cb2641`. Bản này có mã nguồn website và bản ghi trạng thái; **chưa bao gồm lần viết lại README này hoặc các thay đổi phát sinh sau đó**.

Nhánh backup nằm trong cùng kho GitHub, không phải bản sao độc lập. Để có bản lưu ngoài GitHub, tải ZIP và lưu vào thiết bị hoặc nơi lưu trữ riêng.

### Tạo backup mới

1. Xác định commit hiện tại đã kiểm tra.
2. Tạo nhánh `backup-YYYY-MM-DD-HHMM` từ đúng commit đó.
3. Ghi ngày giờ Việt Nam và các thay đổi trong bản ghi trạng thái.
4. Tải ZIP nếu cần bản sao độc lập.
5. Không sửa nhánh backup cũ khi cập nhật website.

### Khôi phục

1. Chọn nhánh backup hoặc commit cần khôi phục.
2. Tạo nhánh phục hồi riêng để kiểm tra.
3. Đối chiếu và đưa các tệp cần phục hồi về main bằng commit mới hoặc pull request.
4. Kiểm tra rồi triển khai lại.
5. Không reset hoặc force push làm mất lịch sử khi chưa được yêu cầu rõ ràng.

## 9. Tiếp tục dự án hoặc dùng mẫu cho dự án mới

Khi tiếp tục, đọc README và bản ghi trạng thái, kiểm tra phiên bản hiện tại trước khi chỉnh sửa. Giữ các lựa chọn giao diện đã chốt trừ khi có yêu cầu mới.

Prompt mẫu tổng quát đã được xuất riêng thành tệp **Prompt_mau_du_an_website_dang_bai.md** trong phiên làm việc; chưa đưa tệp đó vào kho này.

Với dự án tương tự, chuẩn bị:
- Tài liệu bài viết và thứ tự.
- Ngày đăng đã xác nhận.
- Tên chuyên mục, cơ quan và mẫu giao diện.
- Kho GitHub và trang đích cần nhúng nếu có.

Không công khai mật khẩu, khóa truy cập, dữ liệu cá nhân hoặc tài liệu nội bộ trong kho.
