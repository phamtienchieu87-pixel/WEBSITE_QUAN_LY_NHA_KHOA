# grp4-dental-system

Dental Care Management System

## Chạy trên máy cá nhân

Yêu cầu: Node.js 22.12 trở lên và Docker Desktop đang chạy Linux containers.

Mở PowerShell tại thư mục dự án. Khởi động MongoDB:

```powershell
docker compose up -d
```

Dữ liệu được lưu trong Docker volume `grp4-dental_mongo-data` và vẫn còn khi dừng container.

Nếu chưa có file `backend/.env`, tạo từ cấu hình mẫu:

```powershell
Copy-Item backend/.env.example backend/.env
```

Mở terminal thứ nhất để chạy backend:

```powershell
cd backend
npm ci
npm run dev
```

Mở terminal thứ hai tại thư mục dự án để chạy frontend:

```powershell
cd frontend
npm ci
npm run dev
```

Các lần chạy sau có thể bỏ qua `npm ci` nếu các thư viện không thay đổi.

Truy cập http://localhost:5173. Backend chạy tại http://localhost:5000; kiểm tra API tại http://localhost:5000/api/health.

Backend tự tạo tài khoản admin khi kết nối cơ sở dữ liệu trống:

- Email: `admin@dentalcare.com`
- Mật khẩu: `Dentalcare@123`

Chức năng gửi email kích hoạt cần thêm `MAIL_USER` và `MAIL_PASS` (mật khẩu ứng dụng Gmail) trong `backend/.env`. Có thể đăng nhập admin mà không cấu hình email.

Để dừng: nhấn `Ctrl+C` ở hai terminal, rồi chạy `docker compose stop` tại thư mục dự án. Chạy `docker compose up -d` để khởi động lại MongoDB.

**Link btl:** https://drive.google.com/drive/u/0/folders/1xHW1MIWOvdLJJe0ciTzccSaaMKHSPwBu
