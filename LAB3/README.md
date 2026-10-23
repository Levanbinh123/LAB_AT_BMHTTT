README – Tổng kết thực hành LAB 3
Họ Tên : Lê Văn Bình
Lớp : CNPM1
MSSV : 1150080086
1. Mục tiêu bài thực hành
Bài LAB 3 giúp tìm hiểu các kiến thức cơ bản về an toàn thông tin trên Windows, bao gồm kiểm tra tài sản hệ thống, nhận diện rủi ro, theo dõi hoạt động đăng nhập, kiểm tra cơ chế duy trì hoạt động (Persistence) và phân tích lưu lượng mạng bằng Wireshark.
2. Môi trường thực hành
Hệ điều hành: Windows 10 Home Single Language, 64-bit.
Công cụ: PowerShell, Windows Defender, Windows Firewall, Sysmon, Autoruns, Wireshark và Python HTTP Server.
Thư mục lưu bằng chứng: C:\LAB3\Evidence
Thư mục chứa tài nguyên lab: C:\hihi\LAB3_Threats_Assets\LAB3_Threats_Assets\lab3_assets
3. Những nội dung đã thực hiện
TH1 – Kiểm tra tài sản và bảo mật hệ thống
Kiểm tra thông tin hệ điều hành và kiến trúc máy tính.
Kiểm tra trạng thái Windows Defender và tính năng bảo vệ thời gian thực.
Kiểm tra trạng thái Windows Firewall trên các cấu hình Domain, Private và Public.
Kiểm tra các tài khoản người dùng cục bộ.
Kiểm tra những cổng TCP đang lắng nghe trên máy.
Thực hiện kiểm tra khả năng phát hiện của Windows Defender bằng tệp thử nghiệm EICAR. Kết quả ghi nhận phát hiện thành công (ActionSuccess: True).
TH2 – Nhận diện tài sản, lỗ hổng, mối đe dọa và rủi ro
Xác định các tài sản cần bảo vệ trong môi trường Windows.
Tìm hiểu mối liên hệ giữa tài sản, lỗ hổng, mối đe dọa và rủi ro.
Chuẩn bị tài nguyên phục vụ bài lab và xác định đường dẫn thực tế của thư mục dữ liệu.
Sử dụng các kết quả kiểm tra hệ thống làm cơ sở để phân tích rủi ro.
TH3 – Theo dõi sự kiện xác thực
Tạo tài khoản thử nghiệm cục bộ lab3user.
Tìm hiểu cách bật chính sách kiểm tra sự kiện đăng nhập thành công và thất bại bằng auditpol.
Tìm hiểu các mã sự kiện Windows thường dùng để phân tích xác thực như 4624, 4625 và 4648.
Đã gặp lỗi RUNAS ERROR: Unable to acquire user password khi thử chạy chương trình bằng tài khoản thử nghiệm. Vì vậy, chưa xác nhận được thao tác runas thành công; cần kiểm tra thêm sự kiện trong Event Viewer để hoàn thiện phần bằng chứng.
TH4 – Kiểm tra cơ chế Persistence
Tìm hiểu cách kiểm tra mục tự khởi động trong Registry tại:HKCU\Software\Microsoft\Windows\CurrentVersion\Run
Tạo tác vụ theo lịch có tên LAB3_Persistence_Demo để thực hiện thao tác thử nghiệm vô hại.
Kiểm tra trạng thái tác vụ và xác nhận tác vụ chạy thành công bằng tệp kết quả:C:\LAB3\Evidence\task_ran.txt
Kết quả ghi nhận:LAB3_TASK_OK
Chuẩn bị sử dụng Autoruns để kiểm tra các mục tự khởi động.
Thực hành khởi chạy Python HTTP Server tại 127.0.0.1:8080 để phục vụ bài kiểm tra lưu lượng HTTP.
TH5 – Wireshark: HTTP và HTTPS
Tìm hiểu cách chọn giao diện bắt gói tin loopback trong Wireshark để theo dõi lưu lượng trên máy cục bộ.
Thực hành gửi yêu cầu HTTP đến máy chủ thử nghiệm bằng curl.exe.
Sử dụng bộ lọc Wireshark để tìm lưu lượng HTTP và TCP cổng 8080.
Tìm hiểu cách quan sát lưu lượng TLS/HTTPS trên cổng 443.
Phân biệt thông tin có thể quan sát trong HTTP không mã hóa với dữ liệu ứng dụng được mã hóa trong HTTPS.
Lưu ý: Cần lưu ảnh chụp và kiểm tra tệp bắt gói tin thực tế trước khi xác nhận toàn bộ TH5 đã hoàn thành.
4. Bằng chứng thực hành
Các tệp bằng chứng được dự kiến lưu trong C:\LAB3\Evidence, bao gồm:
Ảnh chụp kết quả kiểm tra hệ thống.
Kết quả kiểm tra Windows Defender và Firewall.
Kết quả thử nghiệm tác vụ theo lịch.
Kết quả kiểm tra Autoruns.
Ảnh chụp lưu lượng HTTP và TLS/HTTPS trong Wireshark.
Các tệp văn bản ghi lại thông tin tiến trình, cổng mạng và kết quả thực thi.
Chỉ đưa vào báo cáo những tệp thực sự tồn tại và có kết quả kiểm tra tương ứng.
5. Kết luận
Qua bài thực hành LAB 3, Em đã làm quen với các công cụ quản trị và kiểm tra bảo mật trên Windows, biết cách thu thập thông tin hệ thống, kiểm tra trạng thái bảo vệ, nhận diện các yếu tố rủi ro, tìm hiểu sự kiện xác thực và kiểm tra cơ chế tự khởi động. Tôi cũng đã xác nhận được tác vụ thử nghiệm LAB3_Persistence_Demo thực thi thành công thông qua tệp kết quả LAB3_TASK_OK.
Một số nội dung cần tiếp tục đối chiếu bằng chứng, đặc biệt là thao tác đăng nhập bằng tài khoản thử nghiệm, kết quả kiểm tra Autoruns và ảnh chụp Wireshark. Việc hoàn thiện các bằng chứng này sẽ giúp báo cáo phản ánh chính xác những gì đã thực hiện được.
# LAB3
