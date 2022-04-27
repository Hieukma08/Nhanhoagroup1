- Khi cài đặt email server zimbra mặc định sẽ sinh ra 1 account admin có toàn quyền quản trị  hệ thống email server . tuy nhiên trong quá trình vận hành người sử dụng không được nhớ mật khẩu admin nên phải thực hiện restart password account admin zimbra 
  - Bươc 1 : SSH vào email server và chuyển sang thao tác với user zimbra 
  ```
  su zimbra
  ```

  - Bước 2 : Kiểm tra những user nào có quyền admin 
  ```
  zmprov gaaa
  ```
  - Bước 3 : Thay đổi mật khẩu tải khoản user1
  ```
  zmprov sp user1@tnhydbg.xyz Tnh@1234
  ```