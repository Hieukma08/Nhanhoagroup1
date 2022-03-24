# I. Giới thiệu về giao thức HTTP
## Khái niệm 
1. HTTP là gì ? 
- HTTP (Hypertext Tranfer Protocol) là giao thức truyền tải siêu văn bản được sử dụng trong WWW dùng để truyền tải dữ liệu giữa Web  server đến các trình duyệt Web và ngược lại . Gioa thức này đưuọc sử dụng bởi cổng 80 là chủ yếu .
2. HTTPS là gì ? 
- HTTPS ( hypertext Transfer Protocol ) là giao thức Http có sử dụng thêm SSL ( Secure Socket Layer ) để mã hóa giữ liệu trong lúc truyền tải giữ liệu nhằm gia tăng tính an toàn cho việc truyền dữ liệu giữa webserver và trình duyệt web . Giao thức HTTPS thfi sử dụng cổng 433 để truyền dữ liệu 
3. Cấu trúc của HTTP 
- Cấu trúc hoạt động của HTTP rất đơn giản và dễ hiểu . HTTP là một nền tảng cho phép sự giao tiếp giữa hai khía cạnh bất kì là client và server .
  - Client là người dùng , thường truy cập vào HTTP thông qua một công cụ bất kì như trình duyệt web , còn server sẽ đại diện cho phía website , đằng saugiao diện bao gồm có kịch bản phản ứng từ máy chủ và cơ sở giữ liệu 
4. Đặc điểm của giao thức HTTP 
<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức HTTP/image/1.jpg">
- HTTP có thiết kế đơn giản 
  - Thiết kế đơn giản dễ hiểu cho người mới sử dụng 
- HTTP có khả năng mở rộng 
  - HTTP sở hữu tính linh hoạt rất cao . Nó không có bất kì một giới hạn về sự nâng cấp hay mở rộng . Thâm chí , chỉ cần bằng một thỏa thuận thống nhất giữa client và server là 1 tính năng mới của HTTP đã được hoàn thành 
- HTTP là stateless 
  - Mọi phản hồi của HTTp là độc lập vì vậy người dùng không thể tạo sự liên kết giữa thông tin phản hồi được . 
5. Các lỗi khi sử dụng giao thức HTTP 
- HTTP 404 : Not found 
- HTTP 5000 Internet Server Error
- HTTP 403 Forbiden 
.....