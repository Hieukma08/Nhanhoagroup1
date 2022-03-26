# Process 
 - Mỗi lệnh trên Linux khi thực hiện sẽ `run` một process hoặc `  group các process
## 1. Tổng quan
- Tất cả các chương trình trong Linux thực chất là các process . Process chính là đơn vị cấu thành trên Linux .
## 2. Kiểm tra tất cả các process đang chạy trên hệ thống 
- Sử dụng lện `ps` và show thêm cá thuộc tính `opid, ppid,user,rss,comand` của process 

<img src="/Hệ điều hành Linux/image/15.png">

> Ta có thể thấy mỗi process có một process ID khác nhau và thuộc về một process ID cha nào đó 
## 3. Kiểm tra live các process đang chạy 

- `top`

<img src="/Hệ điều hành Linux/image/16">

 -Thông tin được hiên thị 
 