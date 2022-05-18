# Backup and Restore trên DA 
## Backup trên DA 

- Sau khi tại giao diện chính của DA chọn `Admin BAckup/Transfer` 

<img src="/DirectAdmin/BAckup and Transfer/1.png">

- Màn hình hiển thị ra giao diện cho chúng ta thực hiện việc Backup dữ liệu 
  - Step 1 : `Who` (Tích chọn vào những user muốn backup . Để backup tất cra các user thì chúng ta chọn `All user` )

 <img src="/DirectAdmin/BAckup and Transfer/2.png"> 

  - Step 2 : `When` 
    - `Now` : Để backup trực tiếp 
    - `Cron Schedule` : Để lên lịch backup dữ liệu 

    <img src="/DirectAdmin/BAckup and Transfer/3.png">

  - Step 3 : `Where`
    - Tích chọn `local: /home/admin/user_backups` thì các file backup sẽ nằm trong thư mục này `user_backup` của tài khoản admin 
    - Để backup đến 1 `FTP server backup` thì chọn `FTP` và khai báo tài khoản FTP

    <img src="/DirectAdmin/BAckup and Transfer/4.png">

  - Step 4 : `What`
    - Tích chọn `ALL data` để backup toàn bộ dữ liệu hoặc `select data` để tùy chọn backup Domains Directory , Database data , MAil data...

    <img src="/DirectAdmin/BAckup and Transfer/5.png">

  - Sau đó cuối cùng bấm vào `Submit` để backup 

  <img src="/DirectAdmin/BAckup and Transfer/6.png">

- Với trường hợp muốn  đặt lịch tự động backup các bạn chọn click vào `Cron Schedule` ở mục `When` và thiết lập thời gian backup theo nhu cầu 
- Munite : 0-59 ( Số phát bắt đầu chạy backup )
- Hour: 0- 23h ( giờ chạy backup )
- Day of Month : 1-31 ( Bạn nên để mặc định là * để full các ngày trong tháng )
- Month : 1-12 ( Tương tự chúng ta cũng nên để là * để có thể chọn full tất cả các tháng )
- Day of week : 0-7 ( Ví dụ baqnj muốn backup 1 tuần 2 bản vào thứ 3 và thứ 7 thì điển 2 và 6 )
-  Sau đó chọn `backup` để backup dữ liệu 

## Restore dữ liệu 

- Step 1 : `From Where` : Tích chọn file backup mà bạn muốn restore ở mục file đã backup về máy ( Trường hợp backup FTP chúng ta điền thông tin máy muốn backup  )
- Step 2 : Nếu backup cho FTP chúng ta cần chọn ip  FTP cần backup 
- Step 3 : Submit để thực hiện backup



