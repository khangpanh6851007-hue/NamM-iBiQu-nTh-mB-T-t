# Tụng Niệm ULTRA 3.0 — GitHub 2026

Website tĩnh tiếng Việt, phát triển từ bản gốc Kinh Chú Đại Bi & Bát Nhã Tâm Kinh và các bản ULTRA trước.

## 1. Tệp cần có trong repository

Đặt các tệp sau ở thư mục gốc repository:

- `index_ultra_3_0_2026.html` — ứng dụng ULTRA 3.0.
- `manifest.webmanifest` — cấu hình cài đặt PWA.
- `sw.js` — service worker lưu bộ khung ứng dụng để hỗ trợ mở lại ngoại tuyến.
- `README.md` — tài liệu hướng dẫn.
- `.github/workflows/deploy.yml` — GitHub Actions triển khai GitHub Pages.

Workflow sẽ tạo bản `index.html` trong thư mục triển khai từ `index_ultra_3_0_2026.html`, vì vậy không cần tự đổi tên tệp nguồn.

## 2. Tính năng

- Giữ lại hai bài gốc: Chú Đại Bi và Bát Nhã Tâm Kinh.
- Thư viện mục lục tham khảo 186 mục: Trường Bộ DN 1–34 và Trung Bộ MN 1–152, liên kết đến SuttaCentral.
- Bộ đếm niệm Phật, tổng số lần tích lũy.
- Chuông và mõ điện tử, điều chỉnh nhịp.
- Lịch tháng, dấu ngày thực hành và tóm tắt tuần.
- Thống kê ngày thực hành, số lần niệm, bài đã đánh dấu và chuỗi ngày liên tiếp.
- Thư viện nội dung cá nhân, lịch và dữ liệu ULTRA 2.0.
- Xuất/nhập JSON để sao lưu và chuyển dữ liệu.
- Giao diện hoa sen, hiệu ứng ánh sáng, responsive.
- PWA/service worker cache bộ khung ứng dụng để mở lại ngoại tuyến.

**Lưu ý về thư viện:** 186 mục là mục lục theo số hiệu kèm liên kết nguồn, không phải 186 bản dịch toàn văn được nhúng sẵn. Hãy kiểm tra ngôn ngữ, bản dịch, nguồn và quyền sử dụng tại trang gốc trước khi sao chép/phân phối.

## 3. Triển khai lên GitHub Pages

1. Tạo hoặc mở repository GitHub.
2. Đưa các tệp nguồn vào thư mục gốc theo mục 1.
3. Tạo thư mục `.github/workflows/` và đặt workflow tải kèm thành `.github/workflows/deploy.yml`.
4. Commit và push lên nhánh `main`.
5. Mở **Settings → Pages**. Chọn **GitHub Actions** làm nguồn triển khai.
6. Mở tab **Actions** để xem workflow `Deploy Tụng Niệm ULTRA 3.0` chạy. Khi hoàn tất, mở URL GitHub Pages được hiển thị trong job deploy.

Workflow tự tạo `site/index.html` từ `index_ultra_3_0_2026.html` và đưa kèm `manifest.webmanifest`, `sw.js`.

## 4. Cài đặt và sử dụng ngoại tuyến

- Mở website GitHub Pages bằng HTTPS và truy cập online lần đầu.
- Service worker sẽ cache tệp HTML chính, manifest và các tài nguyên cùng origin được yêu cầu sau đó.
- Có thể dùng menu trình duyệt **Thêm vào màn hình chính / Install app** nếu trình duyệt hỗ trợ.
- Dữ liệu bài riêng, lịch, dấu trang và bộ đếm lưu trên trình duyệt/thiết bị hiện tại.
- Các trang ngoài SuttaCentral/CBETA, MP3 ngoài và nội dung chưa được cache vẫn cần Internet.
- Service worker không hoạt động khi mở trực tiếp bằng `file://`; cần HTTPS hoặc localhost.

## 5. Đồng bộ tài khoản

Đồng bộ thật giữa nhiều thiết bị chưa được bật trong bản website tĩnh. Muốn có đăng nhập và đồng bộ đám mây cần cấu hình backend (ví dụ Firebase Authentication và Firestore), quy tắc bảo mật theo tài khoản, phân quyền và chính sách sao lưu. Không đặt mật khẩu, private key hoặc thông tin bí mật trong HTML công khai.

Trong lúc chưa có backend, hãy dùng chức năng **Xuất dữ liệu ULTRA 3.0** và **Nhập dữ liệu** để chuyển dữ liệu thủ công.

## 6. Nguồn tham khảo

- SuttaCentral: https://suttacentral.net/
- Phương pháp biên tập SuttaCentral: https://suttacentral.net/methodology
- CBETA: https://cbeta.org/en

Các liên kết nguồn là nơi tra cứu; ứng dụng không xác nhận mọi bản dịch ở nguồn đều có cùng ngôn ngữ hoặc quyền tái sử dụng.
