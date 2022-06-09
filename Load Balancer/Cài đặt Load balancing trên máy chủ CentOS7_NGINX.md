# Các bước thiết lập mô hình cân bằng tải Load Balancing 
## Mô hình cân bằng tải (Lab)

<img src ="/Load Balancer/image/1.png">

- Mô hình bảo gồm : 
  - Máy chu Loadbalancer (NGINX : IP : 192.168.142.3).
  - Các máy Client Server (Client 1 : APACHE : 192.168.142.10, Client 2 : IP : 192.168.142.11).
- Các máy được kết nối với mạng Internet .

## Cài đặt 
### Cài đặt máy chủ Load Balancing 
- Thông số RAM : 1 GB , Disk : 20GB 
- Ip : 192.168.142.3

- Các bước cài đặt Load Balancing : 
- **Bước 1**
-  