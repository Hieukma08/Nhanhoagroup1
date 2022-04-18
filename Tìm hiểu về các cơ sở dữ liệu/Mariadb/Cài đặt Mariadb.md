# Cài đặt MariaDB trên hệ điều hành Linux
## Các bước thực hiện 
- Bước 1 : Sử dụng các lệnh yum để cài đặt các gói MariaDB 
- Chạy lệnh sau để thêm Repository vào hệ thống

> `yum install wget && wget -O /etc/yum.repos.d/MariaDB.repo http://MariaDB.if-not-true-then-false.com/rhel/$(rpm -E %rhel)/$(uname -i)/10`

- Xóa cache của yum bằng lệnh 

> yum clean all

- Update yum 

> yum update

