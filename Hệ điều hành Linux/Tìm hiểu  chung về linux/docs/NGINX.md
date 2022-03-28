# Tìm hiểu về NGINX

## Khái niệm 
- NGINX là phần mềm mã nguồn mở để phục vụ web , đảo ngược ủy quyền , lưu vào bộ nhớ đệm , cân bằng tải , phát trực tyến phương tiện và hơn thế nữa . Nó khởi đầ là một máy chủ web được thiết kế để có hiệu suất và độ ổn định tối đa . ngoài các khả năng của máy chủ HTTP , NGINX cũng có thể hoạt động như 1 máy chủ proxy cho  email và một proxy ngược và bộ cân bằng tải cho các máy chủi HTTP , TCP và UDP .

## Một số chúc năng của NGINX
- NGINX được phát triển cho mục đích tối ưu sử dụng bội nhớ RAM nhưng phục vụ được nhiều kết nối đồng thời cao hơn . NGINX sử dụng kiến trúc hướng sự kiến không đồng bộ và có khả năng mở dộng . Ngay cả khi không cần xử lí hàng ngàn truy vấn đồng thời , vậy nên  sử dụng NGINX do hiệu suất cao và yêu cầu bộ nhớ thấp cảu NGINX so với APACHE .
- Một số tính năng thông thường của NGINX bao gồm : 
  - Rrverse Proxy với caching 
  - IPv6 
  - Cân tằng tải 
  - FastCGI hỡ trợ với catching 
  - Redirect URL 
  - xử lí file tĩnh , file index và auto-indexing 
  - TTL/SSL với SNI
  - Hỗ trợ nhúng Perl , Lua ...
  - Hỗ trợ WebSockets
  - Giới hạn kết nối đồng thời từ IP
  - Rewrite URL 
4. Cài đặt NGINX 

