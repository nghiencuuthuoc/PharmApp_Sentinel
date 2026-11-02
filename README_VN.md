# PharmApp Sentinel

**Nhìn một lần là biết công việc chạy tự động và chương trình khởi động nào đã chạy tốt, bị lỗi hay chưa từng chạy.**

PharmApp Sentinel là công cụ Windows nhỏ gọn, theo dõi các code chạy qua **Windows Task Scheduler** và danh sách **Startup**. Mọi công việc hiện trong một cửa sổ, tô màu theo kết quả, và bạn đọc được log ngay mà không phải đi tìm từng thư mục.

🇬🇧 English: [README.md](README.md)

---

## Công dụng

- Liệt kê mọi **task do người dùng cài** trong Task Scheduler (bỏ qua task của Windows và hãng phần mềm) và mọi **mục Startup chạy code**.
- Mỗi công việc có một **tab riêng**: trạng thái, lịch chạy, lần chạy cuối và kế tiếp, mã kết quả, tiến trình đang chạy, lịch sử chạy, log mới nhất và các file báo cáo gần đây.
- Tô màu để thấy ngay chỗ có vấn đề:

| Màu | Ý nghĩa |
|---|---|
| 🟢 Xanh lá | PASS – chạy xong, exit code 0 |
| 🔴 Đỏ | FAIL – kết quả khác 0 hoặc log ghi lỗi |
| 🔵 Xanh dương | Đang chạy |
| 🟠 Cam | Bị ngắt (đóng cửa sổ hoặc Ctrl+C) |
| 🟡 Vàng | Cảnh báo – task báo OK nhưng log có lỗi |
| 🩷 Hồng | Thiếu file script hoặc file đích |
| ⚪ Xám | Đã tắt, chưa chạy hoặc không rõ |
| 🟣 Tím | **Chưa có log** – công việc không ghi log mà công cụ tìm thấy |

- Công việc chưa có log được đánh dấu rõ **"Chưa có log"** kèm gợi ý cách thêm log để bạn cải tiến sau.
- **Tự quét lại** (mặc định 1 phút, chỉnh từ 30 giây đến 10 phút, hoặc tắt).
- **Nhớ trạng thái lần trước**: mở lại là thấy ngay dữ liệu cũ rồi tự cập nhật.
- **Chỉ đọc, an toàn**: không bao giờ chạy, sửa hay xóa task hoặc script nào.

## Yêu cầu

- Windows 10 hoặc 11
- Không cần cài thêm gì – `PharmAppSentinel.exe` là một file chạy độc lập.

## Bắt đầu nhanh

1. Tải file **`PharmAppSentinel.exe`** trong repo này.
2. Bấm đúp để mở. (Nếu Windows SmartScreen báo không rõ nhà phát hành, chọn **More info → Run anyway**.)
3. Chờ vài giây cho lần quét đầu tiên. Tab **Tổng quan** liệt kê mọi công việc.
4. Bấm vào tab của một công việc để xem chi tiết, hoặc bấm đúp một dòng ở Tổng quan để nhảy tới tab đó.

## Hướng dẫn sử dụng

**Tab Tổng quan**
- Bấm các nút trạng thái có màu phía trên (FAIL, PASS, Chưa có log…) để lọc danh sách.
- Dùng ô chọn và ô tìm kiếm để lọc theo nguồn (Task Scheduler / Startup), trạng thái, hoặc một phần tên, đường dẫn.
- Bấm tiêu đề cột để sắp xếp.

**Tab của một công việc**
- **Thông tin** – lệnh, script, thư mục chạy, lịch, trạng thái, lần chạy cuối và kế tiếp.
- **Tiến trình đang chạy** – tiến trình thật của công việc, kèm thanh tiến độ nếu log có phần trăm.
- **Lịch sử chạy** – các kết quả trước, lấy từ log và từ các lần quét của ứng dụng.
- **Log** – log mới nhất, lỗi màu đỏ, cảnh báo màu vàng, thành công màu xanh. Chuyển giữa nhiều log, tải lại, mở file log hoặc thư mục chứa log.
- **Báo cáo** – các file đầu ra gần script; bấm đúp để mở.
- Nút phía trên: mở thư mục, sửa script bằng Notepad, sao chép lệnh.

**Menu chuột phải** (cũng dùng được bằng phím Menu hoặc Shift+F10)
- Trên một công việc: mở tab chi tiết, sửa, hiện trong thư mục, mở terminal tại đó, thao tác với log, sao chép tên / đường dẫn / lệnh / tóm tắt chẩn đoán, mở trong Task Scheduler, ghim, lọc theo trạng thái hoặc nguồn, quét lại, thuộc tính.
- Trên nhiều công việc: sao chép tên hoặc đường dẫn, ghim, xuất phần đã chọn ra CSV, tóm tắt thuộc tính.
- Trên vùng trống: quét lại, xuất danh sách ra CSV, xóa bộ lọc, mở thư mục dữ liệu.
- Trong khung log: sao chép, chọn tất cả, lọc theo mức độ, theo dõi log trực tiếp.
- Lệnh và tóm tắt chẩn đoán khi sao chép sẽ tự động **che mật khẩu và token**.

**Ghim** – ghim các công việc quan trọng; chúng nằm đầu dải tab kèm biểu tượng 📌.

**Tiện ích khác**
- **Ngôn ngữ:** English (mặc định) hoặc Tiếng Việt – đổi ở thanh trên hoặc **View → Language**.
- **Giao diện:** System, Light, Dark, Luxury Warm hoặc Modern Blue-Gray.
- **Cỡ chữ:** `Ctrl +` phóng to, `Ctrl -` thu nhỏ, `Ctrl 0` về mặc định.
- **Kéo co giãn vùng:** kéo các thanh chia để dành thêm chỗ cho dải tab, bảng hoặc log.
- **Chân trang:** hiện 9 giây rồi tự ẩn; rê chuột vào vạch mảnh ở đáy để hiện lại (hoặc **View → Show Footer**).
- **Phím tắt:** `Ctrl /` xem toàn bộ danh sách. Hay dùng: `F5` quét lại, `Ctrl+Alt+E` sửa script, `Ctrl+Alt+R` hiện trong thư mục, `Ctrl+Shift+C` sao chép đường dẫn, `Alt+Enter` thuộc tính.

## Dữ liệu của bạn

Cài đặt, lần quét gần nhất và lịch sử chạy được lưu trong `%APPDATA%\PharmApp\Sentinel`. Xóa thư mục này để đưa ứng dụng về trạng thái ban đầu.

## Cần biết

- Việc nhận diện log là suy đoán dựa trên script và các thư mục `logs` gần đó; log đánh dấu ★ là log mà script nhắc tới rõ ràng.
- Windows không lưu lịch sử từng lần chạy của task nếu bạn chưa bật, nên lịch sử bắt đầu tích lũy từ lần quét đầu tiên.
- Script chỉ in ra màn hình console thì không có log để đọc – sẽ hiện **Chưa có log**.

---

© 2009-2026 Pharma R&D Platforms • PharmApp • [www.nghiencuuthuoc.com](https://www.nghiencuuthuoc.com) • [www.pharmapp.dev](https://www.pharmapp.dev)
