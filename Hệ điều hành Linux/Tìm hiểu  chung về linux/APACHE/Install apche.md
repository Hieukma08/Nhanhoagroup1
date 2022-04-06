# Cài đặt webserver apache
## Các bước cài đặt Apache 
### Bước 1 : cài đặt Apache 
- 1.  đầu tiên chúng ta cập nhật những update mới nhất của httpd ( apache )
`yum update httpd`
- 2.  Tiếp theo là cài đặt các gói httpd
`yum install httpd`
- 3. Cài đặt firewall để mở cổng 80 phục vụ các request qua HTTP 
`firewall-cmd --permanent --add-service=http`
- 4. reload lại tường lửa để các quy tắc có hiệu lực 
`firewall-cmd --reload`
### Bước 2 : Kiểm tra máy chủ web 
- 1. Khởi động Apache 
`systemctl start httpd`
- 2. Xác định rằng dịch vụ đã chạy 
`systemctl status httpd`
### Bước 3 :Quản lí process Apache 

- Một số lệnh quản lí cơ bản 
  - dừng máy chủ : `systemctl stop httpd`
  - Khởi động máy chủ : `systemctl start httpd`
  - Khởi động lại máy chủ : `systemctl reload httpd`
  ...
### Bước 4 : thiết lập virtual server
**Cách thiết lập Virtual server**
- Tạo folder cho trang web của bạn 
` mkdir -p /var/www/hieutn.com/html`
- Lập 1 folder để bổ sung lưu trữ log cho trang web của bạn 
`mkdir -p /var/www/example.com/log`
- Chỉ định quyền sở hữu folder html với biến $User
`chown -R $USER:$USER /var/www/hieutn.com/html`
- Đảm bảo web của bạn có quyền mặc định 
`chmod -R 755 /var/www`
- Tạo 1 trang index.html để hiển thị nội dung trang web
` vi /var/www/example.com/html/index.html`
- thêm nội dung vào file index.html
- Trước khi tạo virtual server, cần tạo một directiry sites-available để lưu trữ chúng. Ngoài ra, bạn cũng cần tạo một directory sites-enabled. Directoiry này sẽ chứa các symbolic link cho các virual host mà ta muốn publish. Tạo cả hai directiry này bằng lệnh sau:
`mkdir /etc/httpd/sites-available /etc/httpd/sites-enabled`
- Cẫn chỉnh sửa file chính của Apache 
`vi /etc/httpd/conf/httpd.conf` thêm vào cuối dòng sau : 
`IncludeOptional sites-enable/*.conf`
- Tạo file mới trong directory 
`vi /etc/httpd/sites-available/hieutn.com.conf` và thêm dữ liệu vào file : 
<VirtualHost *:80>
    ServerName www.example.com
    ServerAlias example.com
    DocumentRoot /var/www/example.com/html
    ErrorLog /var/www/example.com/log/error.log
    CustomLog /var/www/example.com/log/requests.log combined
</VirtualHost> 

## Kết quả 

<img src="/Hệ điều hành Linux/Tìm hiểu  chung về linux/APACHE/image/1.jpg">
