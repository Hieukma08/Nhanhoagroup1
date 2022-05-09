# Các bước cài đặt Samba trên centos 7
- Cài đặt samba có sẵn trên kho lưu trữ của Centos 
```
yum install samba samba-client
```
- Sau khi khởi động hoàn tất , hãy khởi động dịch vụ Samba và cho phép chúng khởi động khi khởi động hệ thống 
``` 
systemctl start smv.service
systemctl start nmb.service 
systemctl enable smb.service
systemctl snable nmb.service

```
- cấu hình tường lửa 
```
firewall-cmd --permanent --zone=public --add-service=samba
firewall-cmd --zone=public --add-service=samba
```
- Tạo người dùng Samba và cấu trúc thư mục 
  - bắt đầu bằng cách tạo thư mục /samba
  ```
  mkdir samba
  ```
  - đặt quyền sở hữu nhóm `/samba` thư mục thành : sambashare
  ```
  chgrp sambashare /samba
  ```
  Tạo người dùng samba mới có tên là `josh`
  ```
  sudo useradd -M -d /samba/josh -s /usr/sbin/nologin -G sambashare josh
  ```
  - Tạo thư mục chính của người dùng và đăth quyền sở hữ thư mục cho người dùng `josh` và nhóm `sambashare`
  - nếu bạn ko đặt quyền cho thực mục 2770 và admin người dùng tạo 1 tệp mới , người dùng `josh` sẽ không thể đọc ghi tệp này 

```
  chmod 2770 /samba/josh
```
- Thêm tài khoản người dùng vào cơ sở dữ liệu Samba bằng cách đặt mật khẩu cho người dùng : 

```
smpasswd -a josh
```


- Tạo người dùng quản trị khác bằng cách nhập 

```
useradd -M -d /samba/user -s /usr/sbin/nologin -G sambashare sadmin
```
- Đặt mật khẩu và cho phép người dùng 
```
smbpasswd -a sadmin
smbpasswd -e sadmin
```
- tiếp theo tạo thư mục user chia sẻ 
```
mkdir /samba/users
```
- Đặt quyền sở hữu thư mục cho người dùng sadmin và nhóm sambashare
```
chown sadmin:sambashare /samba/users
```
- Thư mục này sẽ có thể truy cập được bời tất cả người dùng xác thực . lệnh sau định cấu hình quyền truy cập ghi /đọc cho các thành viên của sambashare nhóm trong thư mục `/samba/users/`
```
chmod 2770 /samba/users
```
- Định cấu hình chia sẻ Samba
  - Mở tệp cấu hình Samba và nối các phần 
    ```
    nano /etc/samba/smb.conf
    ```
  - edit file thêm 
  ```
  [users]
    path = /samba/users
    browseable = yes
    read only = no
    force create mode = 0660
    force directory mode = 2770
    valid users = @sambashare @sadmin

[josh]
    path = /samba/josh
    browseable = no
    read only = no
    force create mode = 0660
    force directory mode = 2770
    valid users = josh @sadmin

    ```
- Sau đó chúng ta restart lại dịch vụ Samba và thử kiểm tra 
- Kết quả : 

<img src="/SAMBA Server/1.jpg">

