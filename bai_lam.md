# bai_lam

# BÀI LÀM

- **Họ tên: Luong quoc tuan**
- **Lớp:**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```bash
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng
●	Hiển thị đường dẫn tuyệt đối của thư mục hiện tại :  pwd
●	Liệt kê nội dung, gồm cả file : ls -Force
●	Di chuyển các file ghi_chu.txt vào docs, các file logo vào media: 
				+ mv .\ghi_chu.txt .\docs
				+ mv .\logo_quan_cafe.PNG .\media
●	Sao chép logo từ media vào backup : cp .\media\logo_quan_cafe.PNG .\backup
●	Xoá file .tmp tại thư mục gốc; không xoá file khác: rm .\temp_001.tmp
●	Dùng đường dẫn tương đối vào logs, liệt kê nội dung rồi quay lại thư mục gốc : 
				+ cd .\logs
				+ ls   (Op2 : Get-Content .\server.log)
				+ cd ..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```
Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/14/2026   7:26 AM                backup
d-----        10/14/2026   7:18 AM                data
d-----        10/14/2026   7:24 AM                docs
d-----        10/14/2026   7:18 AM                logs
d-----        10/14/2026   7:25 AM                media
-a----         10/9/2026   1:18 AM             75 .env
-a----         10/9/2026   1:18 AM           2270 bai_lam.md
```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```bash
Get-Content .\logs\server.log | Select-String "ERROR" > .\logs\daily_report.txt
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```
2025-09-30 08:12:15 [ERROR] Khong tim thay trang /menu (404)
2025-09-30 08:15:15 [ERROR] Het thoi gian cho (timeout)
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.
> 
- [x]  Heading 1: tên dự án
- [x]  Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x]  Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x]  Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x]  Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x]  Blockquote nhắc không upload `.env`

## 4.5. Nâng cao – Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```bash
.\auto_report.ps1
```

### Kết quả hiển thị

```
=== BAO CAO LOI ===

2025-09-30 08:12:15 [ERROR] Khong tim thay trang /menu (404)
2025-09-30 08:15:15 [ERROR] Het thoi gian cho (timeout)
2025-09-30 08:36:15 [ERROR] Thanh toan bi tu choi
2025-09-30 08:42:15 [ERROR] Het thoi gian cho (timeout)
2025-09-30 08:51:15 [ERROR] Het thoi gian cho (timeout)
2025-09-30 08:54:15 [ERROR] Khong tim thay trang /menu (404)

```

## 4.6. Nâng cao – Đếm số dòng lỗi

### Lệnh

```bash
# Ghi lệnh vào đây (xoá dòng này)
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```
(Dán kết quả vào đây – xoá dòng này)
```

## 4.7. Nâng cao – Báo cáo tổng hợp

### Các lệnh đã chạy

```bash
New-Item logs/tong_hop.txt
"=== TONG HOP LOG ===" > logs/tong_hop.txt
Get-Content .\logs\server.log | Select-String "WARNING" >> logs/tong_hop.txt
Get-Content .\logs\server.log | Select-String "ERROR" >> logs/tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```
=== TONG HOP LOG ===

2025-09-30 08:21:15 [WARNING] Thoi gian phan hoi cham
2025-09-30 08:30:15 [WARNING] Anh menu dung luong lon
2025-09-30 08:45:15 [WARNING] Anh menu dung luong lon

2025-09-30 08:12:15 [ERROR] Khong tim thay trang /menu (404)
2025-09-30 08:15:15 [ERROR] Het thoi gian cho (timeout)
2025-09-30 08:36:15 [ERROR] Thanh toan bi tu choi
2025-09-30 08:42:15 [ERROR] Het thoi gian cho (timeout)
2025-09-30 08:51:15 [ERROR] Het thoi gian cho (timeout)
2025-09-30 08:54:15 [ERROR] Khong tim thay trang /menu (404)

```

## 4.8. Nâng cao – Excel

> Phần Excel được chấm trực tiếp trên file `data/orders_thang_9.xlsx`, không cần ghi vào đây.
>