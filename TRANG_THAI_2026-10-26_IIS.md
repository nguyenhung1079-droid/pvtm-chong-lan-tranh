# BÀN GIAO TRẠNG THÁI DỰ ÁN — 26/10/2026

Tài liệu tiếp tục phát triển chuyên mục 20 bài chống lẩn tránh PVTM. Đây là trạng thái mới hơn bản ghi 16/10/2026; không xóa các bản ghi và backup cũ.

## 1. Nguồn và nơi triển khai

- Kho: https://github.com/nguyenhung1079-droid/pvtm-chong-lan-tranh
- Bản GitHub Pages: https://nguyenhung1079-droid.github.io/pvtm-chong-lan-tranh/index.html
- Bản sao IIS: C:\Web\bantin\bai-viet-pvtm
- Địa chỉ HTTP đã kiểm tra: http://bantin.trav.gov.vn/bai-viet-pvtm/
- Địa chỉ HTTPS đã chọn cho iframe: https://bantin.trav.gov.vn/bai-viet-pvtm/
- Site IIS: bantin.trav.gov.vn; thư mục gốc C:\Web\bantin.
- Nguồn giao diện trước triển khai: commit b7a66e9aeb55958064356e26da2fb1ee57ee46e5. Xem deployment.json trong bản sao lưu máy chủ để biết commit tải thực tế.

Website HTML tĩnh, không có CSDL riêng. Nội dung trong HTML; các ảnh hiện có được nhúng base64. Không có cơ chế tự đồng bộ GitHub và IIS: sửa GitHub không tự cập nhật bản sao trên máy chủ.

## 2. Trạng thái đã chốt

- Đủ 20 bài, index có tìm kiếm tiếng Việt có dấu/không dấu.
- Index không hiển thị tiêu đề chuyên mục lớn hoặc thống kê số bài.
- Tiêu đề danh sách lấy theo từng bài, không có tiền tố Bài 1… và nhãn Đã có nội dung.
- Tiêu đề bài 20 trong index đã in hoa; thay đổi này chỉ áp dụng danh sách.
- Bỏ tab chuyển bài cả trên và dưới; giữ Bài trước/Bài sau.
- Liên kết về index là Quay lại chuyên mục.
- CSS chung: Arial 17px, điện thoại 16px tại tối đa 700px; giãn dòng 1,7; sau đoạn 16px; đoạn và danh sách căn đều.
- Đề mục nội dung in đậm cùng cỡ thân bài; bảng cuộn ngang, ảnh giữ tỷ lệ.
- Giữ nội dung, số liệu, bảng, ảnh và chú thích khi chỉnh giao diện.

## 3. Lịch ngày đăng có hiệu lực

Theo danh sách người dùng xác nhận 26/10/2026, thay thế lịch cũ. Giữ thứ tự 01–20; không tự sắp xếp lại theo thời gian. Ngày đã đồng bộ ở index, đầu/cuối bài và thuộc tính datetime.

| Bài | Ngày đăng |
|---|---|
| 01 | 12/08/2026 |
| 02 | 20/08/2026 |
| 03 | 26/08/2026 |
| 04 | 05/09/2026 |
| 05 | 12/09/2026 |
| 06 | 19/09/2026 |
| 07 | 26/09/2026 |
| 08 | 12/08/2026 |
| 09 | 20/08/2026 |
| 10 | 26/08/2026 |
| 11 | 05/09/2026 |
| 12 | 12/09/2026 |
| 13 | 19/09/2026 |
| 14 | 26/09/2026 |
| 15 | 12/08/2026 |
| 16 | 20/08/2026 |
| 17 | 26/08/2026 |
| 18 | 05/09/2026 |
| 19 | 12/09/2026 |
| 20 | 30/09/2026 |

## 4. Mã nhúng mới

```html
<p>
  <iframe
    height="1400"
    src="https://bantin.trav.gov.vn/bai-viet-pvtm/"
    style="display:block;width:100%;border:0;background:#fff;"
    title="Chuyên mục Bài viết chống lẩn tránh biện pháp phòng vệ thương mại và gian lận xuất xứ"
    width="100%">
  </iframe>
</p>
```

Người dùng đã nhận mã và xác nhận hài lòng. Chưa trực tiếp kiểm tra iframe đã lưu và hiển thị trong CMS Cục.

Trang CMS đích đã cung cấp:
https://pvtm.gov.vn/default.aspx?page=news-detail&do=detail&category_id=2a2f39c9-2f9e-46e2-bb2d-3e974778f666&id=f9966ab3-7bcd-4c49-ad6f-be08e9f6d306

Khung cao cố định 1400px; chưa có cơ chế tự tăng chiều cao giữa hai tên miền.

## 5. Triển khai IIS và bằng chứng kiểm tra

- Đã sao chép 22 tệp chạy website: index.html, style.css, bai-01.html đến bai-20.html.
- Đã so sánh SHA256: 22 tệp khớp nguồn.
- HTTP: 23 kiểm tra thành công, gồm URL thư mục, index, CSS và 20 bài.
- Lần đầu di chuyển thư mục từ TEMP gặp HTTP 401, đã rút bản triển khai.
- Lần sau tạo thư mục tại đích rồi sao chép tệp để nhận quyền kế thừa: HTTP thành công.
- HTTPS kiểm tra từ máy chủ còn lỗi tin cậy chứng chỉ. Đây không phải bằng chứng HTTPS bên ngoài hoạt động hoặc hỏng; cần kiểm tra độc lập trước khi xác nhận đầy đủ.
- Không đổi SSL, binding, DNS, firewall, web.config; không restart IIS.
- Chưa kiểm tra trực quan bằng trình duyệt thật cho bản sao mới.

## 6. Backup và bằng chứng trên máy chủ

Thư mục đã tạo: C:\BanTinBackups\bai-viet-pvtm-20261026-143001

Tên thời gian này do đồng hồ máy chủ tạo; không suy diễn thành giờ Việt Nam. Bên trong có:
- source.zip: gói nguồn tải theo commit.
- deployment.json: nguồn, commit, đích và thông tin triển khai.
- http-checks.json: kết quả HTTP.
- failed-deployment: bản rút sau lần đầu lỗi 401; giữ làm bằng chứng, không phải bản đang phục vụ.

Backup GitHub trước hiệu đính:
backup-2026-10-26-truoc-hieu-dinh-ngay

Backup cũ:
backup-2026-10-16-1720

Các nhánh backup nằm cùng kho; gói trên máy chủ là bản lưu khác vị trí. Giữ nguyên các bản cũ.

## 7. Tiếp tục và mở rộng

1. Đọc tài liệu này và README; kiểm tra phiên bản hiện tại cả GitHub và IIS.
2. Xác định rõ đang sửa nguồn GitHub, bản IIS hay cả hai.
3. Backup đúng thư mục chuyên mục trước khi cập nhật; không ghi đè website gốc hoặc các bản tin.
4. Chuẩn bị bản thay đổi, kiểm tra nội dung/ngày/đường dẫn; triển khai trong phạm vi bai-viet-pvtm.
5. Tạo thư mục đích và sao chép để kế thừa quyền website; tránh chuyển nguyên thư mục từ TEMP.
6. Kiểm tra HTTP/HTTPS, CSS, đủ bài, tìm kiếm, điều hướng và khung nhúng.
7. Nếu kiểm tra phục vụ tệp thất bại, khôi phục phiên bản trước; không tự sửa SSL/binding/DNS/firewall hay restart IIS.
8. Ghi commit, ngày cập nhật, kết quả kiểm tra và vấn đề còn lại vào hồ sơ.
9. Nếu bổ sung đồng bộ tự động hoặc CMS, cần thiết kế luồng xem thử, duyệt, backup, triển khai và phục hồi trước khi áp dụng.

Prompt tái sử dụng đã xuất riêng: Prompt_mau_du_an_website_dang_bai.md; không mặc nhiên có trong kho.
