# Giới thiệu về CFS : 
- CFS viết tắt của Config Sever & Firewall là 1 gói ứng dụng hoạt động trên Linux như 1 firewall được phát hành miễn phí để tăng tính bảo mật cho server ( VPS và Dedicate )
- CSF hoạt động dựa trên iptables và tiến trình ldf để quét các file log để phát hiện các dấu hiệu tấn công bất thường .
# Tác dụng của CSF 
- Chống DoS các loại 
- Chống Scan Port 
- Đưa ra các lời khuyên về việc cấu hình server ( VD : Nâng cấp MySQL lên phiên bản mới hơn )
- Chống Syn Flood 
- Chống Ping Flood
- Cho phép ngăn chặn truy cập từ 1 quốc gia nào đó bằng cách chỉ định _ Contry Code chuẩn ISO
- Hỗ trợ IPv6 và Ipv4 
- Cho phép khóa Ip tạm thời và vĩnh viễn ở tầng mạng nên webserver không phải mệt nhọc xử lí yêu cầu từ các ip bị cấm nữa 
- Cho phép bạn chuyển hướng yêu cầu từ các ip bị khóa sang 1 file html để thông báo cho người dùng đó biết Ip đó đã bị khóa 
- Và rất nhiều tính năng khác ,

# Cài đặt CSF : 
- Cài đặt module perl cho CSF-script
```
yum install perl-libwww-perl 
```
- Tải CSF : 
```
cd /tmp
wget https://download.configserver.com/csf.tgz
tar -f csf.tgz
./install.sh
```
# Cấu hình CSF
- Mặc định thì CSF sẽ được cài đặt và chạy ở chế độ "Testing" có nghĩa là server lúc này chưa được bảo vệ toàn diện . Để tắt chế độ này bạn cần cấu hình các lựa chọn TCP_IN , TCP_OUT, UDP_IN và UDP_OUT cho phù hợp với nhu cầu :
  - Mở cấu hình CSF
  ```
  nano /etc/csf/csf.conf
  ```