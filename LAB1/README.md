# LAB 1 - EXAMINING SSH & TELNET IN WIRESHARK

## 1. Thông tin bài thực hành

- **Họ và tên:** Lê Văn Bình
- **Mã sinh viên:** 1150080086

## 2. Mục tiêu

- Tìm hiểu giao thức SSH và Telnet.
- Làm quen với VMware Workstation và máy ảo Windows Server.
- Sử dụng Wireshark để bắt và phân tích gói tin mạng.
- Sử dụng PuTTY để thực hiện kết nối từ xa.
- So sánh khả năng bảo mật giữa SSH và Telnet.

## 3. Môi trường thực hành

- Máy tính thật: Windows.
- Phần mềm ảo hóa: VMware Workstation.
- Máy ảo: Windows Server.
- Phần mềm phân tích mạng: Wireshark.
- Công cụ kết nối từ xa: PuTTY.

## 4. Cấu hình mạng

Mạng thực hành được cấu hình theo chế độ Host-only thông qua VMware VMnet1.

| Thiết bị | Địa chỉ IPv4 |
|---|---|
| Máy thật (VMnet1) | 192.168.92.1 |
| Máy ảo Windows Server | 192.168.92.2 |

**Subnet Mask:** `255.255.255.0`

### Kết quả kiểm tra

- Máy ảo ping được máy thật.
- Máy thật ping máy ảo chưa thành công.
- Cần kiểm tra thêm cấu hình IP và Windows Defender Firewall trên máy ảo.

## 5. Quá trình thực hiện

### 5.1. Cấu hình VMware

Đã kiểm tra địa chỉ IP của máy thật bằng lệnh `ipconfig`, xác định địa chỉ VMnet1 là `192.168.92.1` và địa chỉ máy ảo Windows Server là `192.168.92.2`.

Đã thử sử dụng lệnh `ping` để kiểm tra kết nối giữa hai máy. Kết quả cho thấy kết nối chưa hoạt động hoàn toàn theo cả hai chiều.

### 5.2. Cài đặt OpenSSH Server

Đã mở PowerShell với quyền Administrator và thực hiện lệnh:

```powershell
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
```

Quá trình cài đặt gặp lỗi:

```text
Add-WindowsCapability failed
Error code = 0x8024402C
```

Lỗi chưa được khắc phục. Các vấn đề cần kiểm tra gồm:

- Cấu hình DNS của máy ảo.
- Kết nối Internet.
- Cấu hình Windows Update.
- Cấu hình proxy hoặc các thiết lập mạng liên quan.

### 5.3. Trạng thái thực hiện

- Chuẩn bị môi trường VMware.
- Kiểm tra địa chỉ IP máy thật. hoành thành
- Kiểm tra địa chỉ IP máy ảo. hoàn thành
- Khắc phục kết nối ping giữa hai máy. hoàn thành
- Cài đặt thành công OpenSSH Server. chưa hoàn thành
- Kết nối SSH bằng PuTTY.chưa hoàn thành
- Bắt và phân tích gói SSH bằng Wireshark.chưa hoàn thành
- Thực hành Telnet.chưa hoàn thành
- So sánh dữ liệu SSH và Telnet.chưa hoàn thành

## 6. Kế hoạch tiếp theo

1. Kiểm tra cấu hình mạng và DNS trên Windows Server.
2. Khắc phục lỗi cài đặt OpenSSH Server.
3. Kiểm tra dịch vụ SSH và kết nối bằng PuTTY.
4. Sử dụng Wireshark để bắt gói SSH.
5. Thực hành Telnet trong môi trường thử nghiệm cô lập.
6. Phân tích và so sánh dữ liệu bắt gói của SSH và Telnet.
7. Bổ sung hình ảnh và kết quả thực nghiệm vào báo cáo.

## 7. Kết luận

Đã chuẩn bị môi trường thực hành trên VMware Workstation và kiểm tra cấu hình mạng giữa máy thật với máy ảo Windows Server.

Hiện tại, kết nối mạng chưa hoạt động hoàn toàn theo cả hai chiều và quá trình cài đặt OpenSSH Server gặp lỗi `0x8024402C`. Do đó, các bước kết nối SSH, bắt gói tin bằng Wireshark và thực hành Telnet vẫn đang được thực hiện.

Sau khi khắc phục các vấn đề trên, sẽ tiếp tục thu thập dữ liệu thực tế để hoàn thiện bài thực hành.

## 8. Minh chứng

Các ảnh chụp màn hình được lưu trong thư mục `screenshots/`.

- `network-configuration.png`: Cấu hình mạng VMware.
- `ipconfig.png`: Kết quả lệnh ipconfig.
- `ping-test.png`: Kết quả kiểm tra ping.
- `openssh-install-error.png`: Lỗi cài đặt OpenSSH Server.

Chỉ bổ sung ảnh chụp thực tế đã thu thập được.

## 9. Cấu trúc thư mục

```text
LAB_AT_BMHTTT/
└── LAB1/
    ├── README.md
    ├── word.dox/

```