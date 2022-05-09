# Các bước cài đặt NFS 
- Trên máy server 
  - Bước 1 :  Cài đặt NFS 
  ```
  yum install nfs-utils
  ```
  - Bước 2 : Chuẩn bị thư mục để chia sẻ ổ đĩa NFS là /share-data đồng thời thay đổi các quyền cho thư mục đó 
  ```
  mkdir /share-data
  chomod -R 755 /share-data
  chown nfsnobody:nfsnobody /share-data
  ```
  - Bước 3 : Kích hoạt và chạy các dịch vụ cần thiết 
  ``` 
  systemctl enable rpcbind
  ystemctl enable nfs-server
  systemctl enable nfs-lock
  systemctl enable nfs-idmap

  systemctl start rpcbind
  systemctl start nfs-server
  systemctl start nfs-lock
  systemctl start nfs-idmap
  ```
  - Bước 4. Thiết lập quyền truy cập cụ thể vào 1 ip . VD 192.168.142.20
  ```
  /share-data 192.168.142.20(rw)
  ```
  - Bước 5 : Restart lại dịch vụ 
  - Bước 6 : Mở các cổng firewall
- Bên client :
  - Bước 1 : Cài đặt NFS
  ```
  yum install nfs-utils
  ```
  - Bước 2 : Gán ổ đĩa vào máy Client . thiết  lập thư mục share-data từ NFS server có IP là 192.168.142.10 sẽ gắn vào /mnt/nfs/share-data của máy Client
  ```
  mkdir -p /mnt/nfs/share-data
  mount -t nfs 192.168.142.10:/share-data /mnt/nfs/share-data/
  ```



  - Như vậy là đã hoàn tất quá trình cài nfs , chúng ta có thể truy cập vào máy chủ để lấy dữ liệu 
  