# Cài đặt MariaDB trên hệ điều hành Linux
## Các bước thực hiện 
- Bước 1 : Sử dụng các lệnh yum để cài đặt các gói MariaDB 
- Chạy lệnh sau để thêm Repository vào hệ thống

> `yum install wget && wget -O /etc/yum.repos.d/MariaDB.repo http://MariaDB.if-not-true-then-false.com/rhel/$(rpm -E %rhel)/$(uname -i)/10`

- Bước 2 :  Xóa cache của yum bằng lệnh 

> yum clean all

- Bước 3:  Update yum 

> yum update

- Bước 4 : Cài đặt Mairiadb 

> yum install MariaDB-server MariaDB-client

- Bước 5 : Khởi động lại MariaDB 

> Service mysql start 

- Bước 6 : Đưa sql vào danh sách các ứng dụng khởi độngh lại khi reboot server

> chkconfig --levels 150 mysql on 

- Bước 7 : Thiết lập mật khẩu root 

> mysql_secure_íntallation

- Bước 8 : Cuối cùng đăng nhập vào MariaDB 

> mysql -u root -p


