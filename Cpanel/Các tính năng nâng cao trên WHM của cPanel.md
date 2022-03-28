# Các tính nawg của WHM của cPanel
-  Toàn bộ tính năng của WHM được hiển thị dưới dạng menu 
- Các cấu hình trong phần này :
1. Cấu hình liên quan đến server 
- Thư mục Web lưu trữ 
- Interface chính 
- Thay đổi mật khẩu root
- Remote console SS trên phần web 
- Quản lí tiến trình crontab 
- Quản lí profile Server (Chạy DNS , Mail ,DB,Stand Alone )
- Các support liên quan đến limit mail 

2. Support 

- gửi các Ticket và theo dõi các ticket đã khởi tạo 

3. Cấu hình hostname và DNS

- Chúng ta có thể câu shinfh lại DNS cũng như host name của server
4. Sucurity  Center - Các mode nâng cao về tính bảo mật 
- Trong module này thì các mode bảo mật từ server đến application sẽ được hiển thị để người quản trị có thể cấu hình
- Người quản trị cũng có thể cấu hình Policy cho các task liên quan đến các thông tin pasword của các tài khoản được khởi tạo sau này 
5. Server Contact 
- Cấu hình thông tin email và các thông tin gửi thông báo trong trường hợp có thay đổi tương ứng trên hệ thống 
6. Reseller : Thông tin về các tài khoản và cấu hình cho Reseller . Cấu hình các thông tin liên quan như 
- Show các tài khaorn reseller 
- Quản lí Ip cho share cho reseller
7. Locales - Cấu hình các ngôn ngữ , endcode
8. Backup - restore hệ thống 
9. Cluster - Cấu hình cluster : Quản lí việc kết nối với các server chạy cPanel thành c;uster quản lí trên 1 giao diện duy nhất 
10. System Reboot: Cho phép reboot mềm và reboot cứng server trực tiếp trên Dashboard
11. Server status: Trạng thái các dịch vụ hoạt động trên Server
12. Account Infomation: Thống kê chi tiết danh sách và list domain, tình trạng sử dụng của các tài khoản đang hoạt động trên Cpanel

13. Account Functions: Các tính năng liên quan đến tài khoản account
- Thêm sửa khóa xóa tài khoản
- Limit bandwidth
- chế độ demo
- Thay đổi gói của tài khoản
- Thay đổi template hiển thị
14. transfers - Chuyển đổi tài khoản, dữ liệu tài khoản
- Chuyển đổi addon domain thành user
- Cho phép chuyển dữ liệu người dùng từ một server khác

15. Themes - Cấu hình giao diện: Có thể tùy biến giao diện có sẵn
Package: Quản lý các gói cấu hình: Quản lý các tham số liên quan đến các gói cấu hình cung cấp cho người dùng cuối khi khởi tạo tài khoản

16. DNS Functions: Đối với việc sử dụng cPanel như một DNS server thì giao diện WHM cung cấp đầy đủ các tính năng để có thể quản trị một DNS server
- Quản lý các Zone,
- Quản lý các bản ghi DNS
- Cấu hình các tham số của bản ghi

17. SQL Services - Quản lý DB Quản lý các DB chạy trên server bao gồm tình trạng dịch vụ và cả các thông tin tài khoản, đăng nhập phpmyAdmin
IP Funtions - Các tính năng liên quan đến IP Server:
18. Quản lý các thông tin về range IP cấu hình cho Server. Sử dụng cho việc share IP. MultiIP cho các reseller.

19. Tính năng cũng cho phép quản lý các IP Migrate
20. Software: liên quan đến dịch vụ cPanel và các package trên server: Quản lý các package đã cài đặt trên hệ thống
21. Email - Quản lý email server: Cpanel cũng hỗ trợ email server thế nên việc sử dụng cPanel như 1 email server thì các cấu hình liên quan đến email sẽ được hiển thị chi tiết tại module này
22. System Health - Trạng thái hệ thống: Thống kê tình trạng sử dụng disk cũng như các process đang hoạt động trên hệ thống
23. Cpanel - Quản lý các tùy chỉnh, log và addon plugin, phiên bản
 24. cPanel:Module này hỗ trợ quản lý các Tùy chỉnh giao diện,. addon , plugins, version cpanel

25. SSL/TLS - Quản lý Certificate SSL cho các domain
26. Maket
27. Restart Service - Khởi động lại dịch vụ: Cho phép khởi động lại các dịch vụ đang hoạt động trên server ngay trên giao diện Dashboard
28. Development - Tính năng dành cho nhà phát triển