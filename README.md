# Dental Care — Kiểm thử và đánh giá website quản lý nha khoa

Dự án xây dựng website quản lý nha khoa Dental Care và thực hiện kiểm thử dựa trên tài liệu đặc tả yêu cầu, thiết kế hệ thống và bộ ca kiểm thử.

| Thông tin | Nội dung |
|---|---|
| Học phần | Đánh giá và kiểm định chất lượng phần mềm |
| Trường | Đại học Phenikaa |
| Hệ thống được kiểm thử | Dental Care Management System |
| Phương pháp thực hiện | Kiểm thử thủ công trên giao diện website |
| Công cụ quản lý ca kiểm thử | Microsoft Excel |
| Minh chứng | Ảnh màn hình và video demo có trong link drive |
| Báo cáo | https://drive.google.com/drive/u/0/folders/1xHW1MIWOvdLJJe0ciTzccSaaMKHSPwBu |

## 1. Mục tiêu đề tài

Dental Care là website hỗ trợ quản lý thông tin khách hàng, nhân sự, dịch vụ, lịch khám và các nghiệp vụ liên quan đến tiếp đón, khám bệnh, thanh toán và tính lương.

Hoạt động kiểm thử được thực hiện nhằm:

- Đối chiếu hoạt động của phần mềm với yêu cầu và quy tắc nghiệp vụ đã đặc tả.
- Kiểm tra các trường hợp sử dụng hợp lệ và không hợp lệ.
- Phát hiện sai lệch trong xử lý dữ liệu và nghiệp vụ.
- Ghi nhận dữ liệu đầu vào, kết quả mong đợi, kết quả thực tế và trạng thái của từng ca.
- Lưu bằng chứng để hỗ trợ phân tích lỗi và kiểm thử lại.
- Đánh giá chất lượng hệ thống trong phạm vi đã kiểm tra.

## 2. Phạm vi hệ thống

Hệ thống được mô tả trong tài liệu theo bốn phân hệ:

| Phân hệ | Nội dung chính |
|---|---|
| UC1 — Quản lý hệ thống | Quản lý khách hàng, nhân sự, dịch vụ và bảng giá |
| UC2 — Quản lý lịch khám bệnh | Thiết lập ngày nghỉ, ca làm việc, lịch bận và lịch hẹn |
| UC3 — Tiếp đón và khám bệnh | Tiếp đón, quản lý thông tin khám, thanh toán và doanh thu |
| UC4 — Tính lương nhân viên | Quản lý định mức, hệ số, tính lương bác sĩ, phiếu lương và báo cáo |

Các tác nhân chính gồm:

- **Admin:** quản trị tài khoản, danh mục, cấu hình và các nghiệp vụ được phân quyền.
- **Lễ tân:** quản lý hồ sơ khách hàng, lịch hẹn, tiếp đón và các nghiệp vụ liên quan.
- **Bác sĩ:** thực hiện các nghiệp vụ chuyên môn, quản lý lịch cá nhân và tra cứu thông tin được cấp quyền.

Khách hàng là đối tượng được quản lý hồ sơ trong các luồng nghiệp vụ đang xét.

Phạm vi đặc tả không đồng nghĩa mọi chức năng đã được triển khai đầy đủ. Khi đánh giá, cần đối chiếu từng chức năng với phiên bản phần mềm thực tế; các màn hình sử dụng dữ liệu mẫu chưa đủ căn cứ để xác nhận nghiệp vụ đã hoàn thiện.

## 3. Công nghệ và công cụ

| Thành phần | Công nghệ, công cụ | Vai trò |
|---|---|---|
| Frontend | React, Vite | Xây dựng giao diện website |
| Backend | Node.js, Express | Xử lý yêu cầu và nghiệp vụ |
| Kết nối dữ liệu | Mongoose | Làm việc với MongoDB |
| Cơ sở dữ liệu | MongoDB | Lưu trữ dữ liệu |
| Môi trường cục bộ | Docker Desktop, Docker Compose | Khởi động dịch vụ MongoDB |
| Thực hiện kiểm thử | Trình duyệt web | Thao tác và quan sát kết quả |
| Quản lý test case | Microsoft Excel | Lưu dữ liệu, kết quả và trạng thái |
| Minh chứng | Công cụ chụp ảnh, quay màn hình | Ghi lại quá trình kiểm thử |

Trong phạm vi báo cáo và demo hiện tại, nhóm thực hiện **kiểm thử thủ công**.

Excel được sử dụng để quản lý ca kiểm thử và ghi nhận kết quả, không tự động thực hiện các thao tác trên website.

## 4. Phương pháp kiểm thử

Nhóm kiểm tra phần mềm dựa trên yêu cầu, dữ liệu đầu vào và kết quả quan sát được trên giao diện.

Các nhóm tình huống được lựa chọn gồm:

- Dữ liệu hợp lệ.
- Bỏ trống thông tin bắt buộc.
- Dữ liệu sai định dạng hoặc không đúng độ dài.
- Thông tin định danh bị trùng.
- Tìm kiếm dữ liệu đã tồn tại.
- Tìm kiếm dữ liệu không tồn tại.
- Kiểm tra dữ liệu sau khi lưu và tải lại trang.

Mỗi tình huống cần có kết quả mong đợi được xác định trước khi thực hiện. Kết quả thực tế được đối chiếu với kết quả mong đợi để đánh giá trạng thái.

## 5. Quy trình thực hiện

1. Đọc yêu cầu và xác định chức năng cần kiểm tra.
2. Chọn ca kiểm thử tương ứng trong file Excel.
3. Chuẩn bị tài khoản, dữ liệu và điều kiện trước khi chạy.
4. Kiểm tra kết quả mong đợi của ca.
5. Thực hiện các thao tác trên website.
6. Quan sát thông báo, giao diện và dữ liệu được lưu.
7. Đối chiếu kết quả thực tế với kết quả mong đợi.
8. Ghi kết quả, trạng thái và lưu ảnh hoặc video minh chứng.
9. Ghi nhận sai lệch, phân tích nguyên nhân và kiểm thử lại sau khi sửa.

### Quy ước trạng thái

| Trạng thái | Ý nghĩa |
|---|---|
| Passed | Kết quả thực tế đáp ứng kết quả mong đợi |
| Failed | Kết quả thực tế có sai lệch so với mong đợi |
| Not Run | Chưa thực hiện ca kiểm thử |
| Not Completed | Đã thực hiện nhưng chưa hoàn thành hoặc chưa đủ căn cứ kết luận |

Với ca nhập dữ liệu không hợp lệ, hệ thống từ chối đúng yêu cầu thì ca có thể được ghi nhận **Passed**.

Số ca Failed không đồng nghĩa với số lỗi độc lập, vì một lỗi có thể ảnh hưởng đến nhiều ca kiểm thử.

## 6. Tổ chức bộ TestCase

File `TestCase.xlsx` được chia theo bốn phân hệ:

- UC1 — Quản lý hệ thống.
- UC2 — Quản lý lịch khám bệnh.
- UC3 — Tiếp đón và khám bệnh.
- UC4 — Tính lương nhân viên.

Các trường thông tin chính:

| Cột | Nội dung |
|---|---|
| Category | Nhóm kiểm thử |
| Test Case ID | Mã định danh ca kiểm thử |
| Test Case Description | Mô tả nội dung cần kiểm tra |
| Steps to Perform | Các bước thực hiện |
| Step Expected Result | Kết quả mong đợi ở bước thực hiện |
| Test Input Value | Dữ liệu đầu vào thực sự sử dụng |
| Test Case Expected Result | Kết quả mong đợi của ca |
| Test Case Program Result | Kết quả thực tế quan sát được |
| Status | Trạng thái đánh giá |

### Ví dụ các ca quản lý khách hàng

| Mã ca | Nội dung |
|---|---|
| UC1.1_FUNC_004 | Thêm khách hàng mới hợp lệ |
| UC1.1_FUNC_005 | Tìm kiếm khách hàng theo CCCD |
| UC1.1_FUNC_006 | Tìm kiếm khách hàng theo số điện thoại |
| UC1.1_FUNC_007 | Tìm kiếm khách hàng theo họ tên |
| UC1.1_FUNC_008 | Tìm kiếm không có kết quả |
| UC1.1_EXC_001 | Kiểm tra trường hợp trùng CCCD |

Khi thực hiện lại bộ ca, cần lưu riêng kết quả của từng đợt chạy. Không ghi Passed trước khi thực hiện và không ghi các bước xác minh chưa thực sự tiến hành.

## 7. Nội dung demo kiểm thử thủ công

Do thời gian trình bày có hạn, demo tập trung vào một số tình huống của chức năng quản lý khách hàng.

| Tình huống | Kết quả mong đợi |
|---|---|
| Thêm khách hàng với dữ liệu hợp lệ | Tạo thành công, thông tin được lưu đúng |
| Thêm khách hàng trùng CCCD | Từ chối và không tạo bản ghi mới |
| Tìm kiếm theo họ tên | Hiển thị khách hàng phù hợp với từ khóa |
| Tìm kiếm theo số điện thoại | Hiển thị đúng khách hàng tương ứng |
| Tìm kiếm theo CCCD | Hiển thị đúng hồ sơ tương ứng |
| Tìm kiếm với từ khóa không tồn tại | Không trả về khách hàng phù hợp |
| Bỏ trống các trường bắt buộc | Yêu cầu bổ sung thông tin và không cho lưu |
| Nhập số điện thoại sai định dạng | Phát hiện dữ liệu không hợp lệ và chặn lưu theo yêu cầu |
| Nhập CCCD không đúng độ dài | Phát hiện dữ liệu không hợp lệ và chặn lưu theo yêu cầu |

Đăng nhập được thực hiện trước khi truy cập chức năng quản lý khách hàng. Nếu đánh giá đăng nhập như một chức năng riêng, cần ghi nhận ca và kết quả tương ứng.

### Cách lưu minh chứng

- Chụp rõ dữ liệu đầu vào, thông báo hoặc kết quả cần chứng minh.
- Đặt tên ảnh gắn với mã ca hoặc chức năng.
- Ghi nhận kết quả vào đúng dòng trong Excel.
- Video thể hiện thao tác, quá trình đối chiếu và cách ghi kết quả.
- Với ca thêm dữ liệu, có thể tải lại trang và tìm lại bản ghi để xác minh dữ liệu đã lưu.

Bảng tình huống trên mô tả nội dung kiểm tra, không thay thế kết quả thực thi và không xác nhận rằng mọi ca đều Passed.

## 8. Tổng hợp kết quả kiểm thử

Bản TestCase được đối chiếu trước đợt chạy lại demo có số liệu:

| Phân hệ | Tổng số ca | Passed | Failed | Not Run | Not Completed |
|---|---:|---:|---:|---:|---:|
| UC1 | 167 | 109 | 54 | 2 | 2 |
| UC2 | 158 | 88 | 66 | 2 | 2 |
| UC3 | 105 | 51 | 50 | 2 | 2 |
| UC4 | 237 | 144 | 89 | 2 | 2 |
| **Tổng** | **667** | **392** | **259** | **8** | **8** |

Tỷ lệ Passed trên tổng số ca của bản này:

**392 / 667 × 100% = 58,77%.**

**Lưu ý:** Đây là số liệu của bản tổng hợp trước đợt quay lại demo. Khi xóa kết quả và chạy lại, cần cập nhật bảng theo file Excel mới trước khi sử dụng làm kết quả báo cáo cuối cùng. Không dùng số liệu trên để đại diện cho các ca vừa thực hiện trong video.

## 9. Đánh giá và giới hạn

Hoạt động kiểm thử giúp đối chiếu cách xử lý của hệ thống với yêu cầu, phát hiện sai lệch và cung cấp căn cứ để hoàn thiện phần mềm.

Tuy nhiên:

- Demo chỉ minh họa một số ca tiêu biểu.
- Kết quả của một chức năng chưa đại diện cho toàn bộ hệ thống.
- Các ca Failed cần được phân tích và liên kết với lỗi cụ thể.
- Các ca chưa hoàn tất cần tiếp tục thực hiện.
- Một số nội dung trong bộ ca cần được chuẩn hóa dữ liệu và bổ sung bằng chứng.
- Các chức năng đang sử dụng dữ liệu mẫu cần được đánh giá riêng.
- Chưa có đủ căn cứ từ demo để kết luận về bảo mật, hiệu năng hoặc khả năng vận hành thực tế.

Nhóm tiếp tục ưu tiên các sai lệch ảnh hưởng đến dữ liệu và nghiệp vụ, thực hiện kiểm thử lại sau khi sửa và kiểm thử hồi quy các chức năng liên quan.

## 10. Hướng dẫn chạy dự án

### 10.1. Yêu cầu

- Node.js phiên bản 22.12 trở lên.
- Docker Desktop đang chạy Linux containers.
- Trình duyệt web.
- Microsoft Excel để đọc và cập nhật bộ ca kiểm thử.

### 10.2. Khởi động MongoDB

Mở PowerShell tại thư mục dự án:

```powershell
docker compose up -d
```

Kiểm tra trạng thái container:

```powershell
docker compose ps
```

Dữ liệu MongoDB được lưu trong Docker volume và vẫn còn khi dừng container.

### 10.3. Chuẩn bị cấu hình backend

Nếu chưa có file `backend/.env`:

```powershell
if (!(Test-Path "backend\.env")) {
    Copy-Item "backend\.env.example" "backend\.env"
}
```

Không đưa file `.env` chứa thông tin bí mật lên GitHub.

### 10.4. Chạy backend

Trong terminal thứ nhất, từ thư mục dự án:

```powershell
cd backend
npm ci
npm run dev
```

Đợi xuất hiện thông báo:

```text
Backend listening on http://localhost:5000
MongoDB Connected successfully
```

### 10.5. Chạy frontend

Mở terminal thứ hai tại thư mục dự án:

```powershell
cd frontend
npm ci
npm run dev
```

Truy cập:

- Website: http://localhost:5173
- Backend: http://localhost:5000
- Kiểm tra dịch vụ: http://localhost:5000/api/health

Các lần chạy sau có thể bỏ qua `npm ci` nếu thư viện không thay đổi.

### 10.6. Tài khoản demo

Backend tự tạo tài khoản admin khi kết nối cơ sở dữ liệu trống:

- Email: `admin@dentalcare.com`
- Mật khẩu mẫu: `Dentalcare@123`

Tài khoản này phục vụ môi trường demo. Chức năng gửi email kích hoạt cần cấu hình `MAIL_USER` và `MAIL_PASS` trong `backend/.env`; có thể đăng nhập admin mà không cấu hình email.

### 10.7. Dừng dự án

Nhấn `Ctrl+C` ở hai terminal đang chạy frontend và backend.

Tại thư mục dự án:

```powershell
docker compose stop
```

Không xóa Docker volume nếu cần giữ dữ liệu và minh chứng kiểm thử.

## 11. Tài liệu và video demo

| Tài liệu | Nội dung |
|---|---|
| DacTaYeuCau_QuanLyNhaKhoa.docx | Yêu cầu và quy tắc nghiệp vụ |
| ThietKeVaCaiDat_QuanLyNhaKhoa.docx | Thiết kế, thuật toán và cài đặt |
| BaoCaoKiemThu_QuanLyNhaKhoa.docx | Kế hoạch, kết quả và đánh giá kiểm thử |
| TestCase.xlsx | Bộ ca và kết quả thực thi |
| Ảnh minh chứng | Kết quả quan sát được của các ca |
| Video demo | Quá trình thao tác và ghi nhận kiểm thử thủ công |

**Video demo:** Bổ sung đường dẫn sau khi tải video lên và kiểm tra quyền xem.

## 12. Nhóm thực hiện

| Thành viên | MSSV | Công việc chính |
|---|---|---|
| Nguyễn Đức Hiếu | 23010614 | Phân tích yêu cầu, kiến trúc; phát triển các chức năng quản lý hồ sơ, nhân sự, dịch vụ, bảng giá và lịch làm việc; đặc tả và kiểm thử phần được giao |
| Phạm Tiến Chiêu | 23010526 | Thiết kế lớp và dữ liệu; các nghiệp vụ lịch hẹn, tiếp đón, khám, thanh toán và doanh thu; phối hợp tích hợp, kiểm thử và tổng hợp báo cáo |
| Bùi Hoàng Thái Anh | 23010543 | Giao diện và thiết kế xử lý phân hệ lương; thuật toán tính lương, giờ quy đổi và hệ số; đặc tả và kiểm thử phần được giao |

## 13. Hướng hoàn thiện

- Chuẩn hóa các ca kiểm thử có nội dung lặp hoặc dữ liệu chưa cụ thể.
- Hoàn thiện các chức năng còn thiếu hoặc đang dùng dữ liệu mẫu.
- Gắn kết quả với bằng chứng, phiên bản phần mềm và người thực hiện.
- Phân tích, ưu tiên và theo dõi các sai lệch đã phát hiện.
- Kiểm thử lại sau khi sửa lỗi.
- Kiểm thử hồi quy các phần có liên quan.
- Mở rộng kiểm tra phân quyền, tính nhất quán dữ liệu và các yêu cầu phi chức năng.

## 14. Tài liệu làm căn cứ

- Tài liệu đặc tả yêu cầu của Dental Care.
- Tài liệu thiết kế và cài đặt hệ thống.
- Báo cáo kiểm thử phần mềm.
- Bộ TestCase Excel.
- Mã nguồn và kết quả thực thi trên môi trường cục bộ.

Dữ liệu dùng trong demo là dữ liệu giả lập. Không đưa hồ sơ cá nhân thật, mật khẩu ứng dụng email, API key hoặc các thông tin bí mật lên kho mã nguồn.
