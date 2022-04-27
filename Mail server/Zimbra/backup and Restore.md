# Backup and Restore
- Bước 1 ; Đăng nhập với user Zimbra và dừng lại các chương trình đang chạy 
```
su zimbra
zmcontrol stop
```
- Đảm bảo rằng Zimbra đã dừng lại hoàn toàn 
```
ps auxww | grep zimbra
```
- `kill-9` Bất kì tiến trình nào còn xót lại 
- Bước 2 : Tọa bản sao lưu 
  - Đảm bảo rằng vị trí sao lưu có đủ dung  lượng để lưu trữ được bản soa 
  - Tất cả thành phầ mà Zimbra cần đều được lưu trữ trong chính sách thư mục Zimbra , nên chỉ cần soa lưu phần thư mục đó vào 1 vị trí an toàn `cp -rp /opt/zimbra/ [vị trí sao lưu]/zimbra_backup. Quá trình có thể mất 1 lúc để lưu
  ( Note : nên gắn ngày sao lưu và file )

  ```
  cp -rp /opt/zimbra /mnt/zimbra_backup.$(date "+%Y%m%d")
  ```
# 2. Restore
- Bước ` : Đảm bảo các chương trình liên quan đến zimbra đã dừng
```
su zimbra
zmcontrol stop
```
- Bước 2 ; Sao chép bản sao lưu đã tạo trước đó vào thư mục /opt và đặt tên là zimbra
```
cp -rp /mnt/zimbra_backup/ /opt
mv /opt/zimbra_backup/ /opt/zimbra
```
- Bước 4 ; cài đặt lại zimbra 
  - Tải lại zimbra 8.8.15
```
wget https://files.zimbra.com/downloads/8.8.15_GA/zcs-8.8.15_GA_3953.RHEL8_64.20200629025823.tgz
``` 
  - Giải nén và cài đặt 
  - `Do you wish to upgrande?` Chọn yes để chạy lại với nhưng dữ liệu cũ

- Bước 3 : Đặt lại nguyên 
  - ```
    chown -R zimbra:zimbra /opt/zimbra/store
    chown -R zimbra:zimbra /opt/zimbra/index
    ```
    ```
    /opt/zimbra/libexec/zmfixperms
    ```
    

