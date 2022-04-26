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
    
  