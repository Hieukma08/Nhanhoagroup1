# Các bước cài đặt FTP server trên Centos 7 
Bước 1 : Cài đặt dịch vụ FTP với VSFTPD
- Cập nhật gói quản lí : 
```
yum update -y
```
- Cài đặt VSFTPD
```
yum install -y vsftpd
```
- Khởi động dịch vụ và cho phép nó khởi động cùng hệ thống 
```
systemctl start vsftpd
systemctl enable vsftpd
```
- Cấu hình tường lửa cho dịch vụ FTP và port 21 
```
firewall-cmd --permanent --add-port=21/tcp
firewall-cmd --permanent --add-service=ftp
firewall-cmd --reload
```
Bước 2 : Cấu hình VSFTPD
- File cấu hình vsftpd nằm tại `/etc/vsftpd/vsftpd.conf` 
- Copy file cấu hình để backup
```
cp /etc/vsftpd/vsftpd.conf /etc/vsftpd/vsftpd.conf
```
- Chỉnh sửa file cấu hình `vsftp.conf`
```
vi /etc/vsftpd/vsftpd.conf
```
- FTP Acces : Ta không thể kết nối nặc danh mà chỉ cho kết nối cục bộ vào FTP server 
```
anonymous_enable=No
local_enable=YES
```
- Cho phép người dùng nội bộ tải lên 
```
write_enable=YES
```
- Giữ người dùng trong thư mục của họ . Tại đây ta sẽ chroot tất cả các user trừ các user trong chroot_list
```
chroot_local_user=YES
allow_writeable_chroot=YES
chroot_list_enable=YES
chroot_list_file=/etc/vsftpd/chroot_list
```
- Banner khi người dùng login vào FTP server 
```
ftpd_banner="welcome FTP server"
```
- Giới hạn khoảng cho các cổng cho FTP passive 
```
pasv_min_port=30000
pasv_max_port=31000
```
- Giới hạn các User được phép truy cập vào hệ thống : Nếu muốn giới hạn các user local được đăng nhập vào hệ thống FTP server . Ta thêm vào các dòng sau . Khi đó , những User có trong file `/etc/vsftpd/user_list` mới được truy cập vào hệ thống .
```
userlist_enable=YES
userlist_file=/etc/vsftpd/user_list
userlist_deny=NO
```
- Thời gian hệ thống : Ta sử dụng thời gian local 
```
user_localtime=YES
```
Bước 3 : Khởi động lại dịch vụ và cho phép các cổng FTP passive đi qua tường lửa

```
systemctl restart vsftpd
firewall-cmd --permanent --add-port=30000-31000/tcp
firewall-cmd --reload
```

# Truy cập FTP server 
- Tạo user vsfer 
```
adduser vsfer
```
- sau khi tạo user thì thư mục mặc định của tài khoản này sẽ ở /home/vsfer
- Cấp quyền truy cập đến FTP server
  - tạo file 