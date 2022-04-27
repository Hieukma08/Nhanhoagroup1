# Các bước cài đặt ZimbraServer
- Để cài đặt được Zimbra MailServer chúng ta cần chuẩn bị 
  - Ram 8GB
  - Tên miền đủ điều kiến "mail.tnhydbg.xyz"
  - Bản ghi A và bản ghi MX cho máy chủ 
- Các bước thực hiện cài đặt 
  - Bước 1 : Cập nhật hệ thống : 
  ```
  sudo yum -y install 
  ```

  - Bước 2 : Kiểm tra bảo mật 
    - Trước hết kiểm tra trạng thái của SeLinux 
    ```
    getenforce
    ```
    - Nếu thấy `enforcing` thì nhập 
    ```
    sudo setenforce 0
    ```
    - sau đó nhập tiếp 
    ```
    getenforce
    ```
    -> chúng ta đã chuyển từ `enforcing` sang `permissive` 

    - Tiếp theo chúng ta cần mở tường lửa cho các port : 25, 80,143,443,465,993,587,9071,7071 của TCP -> reload hiển thị success là thành công .

  - Bước 3 : Config hostname 

  ```
  hostnamectl set-hostname mail.tnhydbg.xyz
  ```
    - Sau đó thêm địa chỉ ip cho hostname 
    ``` 
    nano /etc/hosts
    ```
    -> Save and exit .
    - Next , kiểm tra sự tồn tại của các bản ghi A và MX 
  - Bước 4 : Dowload and Install Zimbra 
    - Dowload 
  ``` wget https://files.zimbra.com/downloads/8.8.15_GA/zcs-8.8.15_GA_3953.RHEL8_64.20200629025823.tgz
  ```
    - Giải nén file 
    ``` 
    tar zcs-8.8.15_GA_3953.RHEL8_64.20200629025823.tgz
    ```
    - chạy file cài đặt 
    ```
    ./install.sh
    ```
    - Nhấn `Y` để chấp nhận cài đặt các package của zm
    - Chọn `7` rồi nhập `4` để chúng ta có thể cài đặt mật khẩu cho root 
    - Sau đó nhập `r` để đồng ý với các thay đổi rồi ấn `a` để lưu lại các thay đổi vừa thực hiện 
    -> Thành công 

- Để kiểm tra sự hoạt động của Zimbra bằng cách sử dụng các câu lệnh sau : 
  - `cd` : rời khỏi thư mục đang thực hiện 
  - `su -zimbra` : Truy cập vào máy chủ zimbra 
  - `zmctrol status` : Kiểm tra các dịch vụ của máy chủ xem có đang hoạt động không 
  - `zmcontrol restart` : Khởi độngh lại thệ thống 
  
  