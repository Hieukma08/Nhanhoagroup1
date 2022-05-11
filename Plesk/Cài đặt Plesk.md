# Cài đặt Plesk trên Linux 
## Các bước cài đặt Plesk trên Linux 
- Đầu tiên chạy câu lệnh cài đặt 
```
sh <(curl https://autoinstall.plesk.com/one-click-installer || wget -O - https://autoinstall.plesk.com/one-click-installer)
```
-> Kết quả như sau 

<img src="/Plesk/image/1.png">

<img src="/Plesk/image/2.png">

- Tiếp theo truy cập vào port 8880 hoặc 8443 
  - đăng nhập vào tài khoản root của server 
  - Cấu hình thông tin tài khoản 

<img src="/Plesk/image/3.png">

- Sau khi cài đặt hoàn tất chúng ta chuyển sang tạo khóa SSL 
- Đăng nhập vào zondns và tạo bản ghi CNAME
- Sau khi lấy được khóa và tải về máy 

<img src="/Plesk/image/6.png" >

- Tiếp thoe trở về giao diện Plesk 
  - Kiếm phần Domain có tên miền vừa đăng kí sau đó tải lên chứng chỉ đã được tải về trước đó 

- Kết quả : Đăng kí cài đặt thành công SSL 

<img src="/Plesk/image/10.png" >




