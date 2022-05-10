# Các bước cài đặt iptable trên Centos 7 
- Cài đặt gói 
  - yum install iptable
- Xem phiên bản và trạng thái của Iptable
  - rpm -q iptable 
  - service iptable status 
- Tường lửa iptable chưa chạy do CentOS 7 dùng firewalld làm tường lửa mực định , nên ta cần làm : 
  - systemctl mask firewalld 
  - systemctl enable iptables
  - systemctl enable ip6table 
  - systemctl stop firewalld
  - systemctl start ip6table 
# Một số nguyên tắc áp dụng trong Iptable
- Đầu tiên cần xác định các service muốn đóng mở các port tương ứng 
- Sau khi xác định được các port cần mở , cần thiết lập các quy tắc tắt tường lửa tương ứng để cho phép 
  - Để truy cập VPS bằng SSH cần mở port SSH -22
  - Truy cập website , cần mở port HTTP -80 hoặc HTTPS -443
  - Để gửi mail cần mở port SMTP -22 và SMTPS -465/587
  - Để người dùng nhận được mail , cần mở port POP3 110 , POP3S -995 , IMAP -143 và IMAPS -993
- Sau khi xác định được các port cần mở m cần thiết lập các quy tắc tường lửa tương ứng để cho phép 
- Xem lại các rule hiện tại 
```
iptables -l
```
# Cách sử dụng iptables để mở các port cho VPS 
- Để mở port trong iptable , cần chèn chuổi ACCEPT PORT . Cấu trúc lệnh để mở port xxx như sau 
  - iptable -A INPUT -p tcp -m tcp --dpory xxx -j ACCEPT
  - iptable -I INPUT -p tcp -m tcp --dport xxx -j ACCEPT 
    - A tức là Append - chèn vào chuổi INPUT ( chèn xuống cuối) 
    - I tức là Insert -chèn vào chuổi INPUT ( chèn vào chuỗi chỉ định rulenum)
    - Để tránh xung đột với các rule gốc , chúng ta nên chèn rule vào đầu , sử dụng -I
# Mở port SSH 
- Để truy cập VPS qua SSH , bạn cần mở port SSH 22
```
iptables -I INPUT -p tcp -m tcp --dport 22 -j ACCEPT
```

- Có thể cho phép kết nối với VPS qua SSH bằng 1 ip bằng lệnh 
```
iptable -I INPUT -p tcp -s  192.168.142.10 -m tcp --dport 22 -j ACCEPT
```
# Mở port Webserver 
```
iptables -I INPUT -p tcp -m tcp --dport 80 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 443 -j ACCEPT
```
# Mở port MAil 
- SMTP 
```
iptables -I INPUT -p tcp -m tcp --dport 25 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 465 -j ACCEPT
```
- POP3
```
iptables -I INPUT -p tcp -m tcp --dport 110 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 995 -j ACCEPT
```
- IMAP
```
iptables -I INPUT -p tcp -m tcp --dport 143 -j ACCEPT
iptables -I INPUT -p tcp -m tcp --dport 993 -j ACCEPT
```

# Chặn 1 Ip truy cập 
``` 
iptables -A INPUT -s ip-address -j DROP
```
- Chặn 1 ip truy cập 1 port cụ thể 
```
iptables -A INPUT -p tcp -s ip-address -dport -j DROP
```
# Bước cuối :
  - Sau khi thiết lập đầy đủ , bao gồm mwor các port cần thiết hay hạn chế các kết nối , cần block toàn bộ hết nối còn lại và cho phép toàn bộ các kết nối ra ngoài từ VPS
    - iptables -p OUTPUT ACCEPT
    - iptables -P INPUT DROP
  - Load lại 
    - service reload iptables 
# Cách remove 1 rule

- Đầu tiên cần tìm 1 dòng của rule đấy 
  - iptables -L INPUT --line-number
- Xóa theo dòng 
  - sudo iptables -D INPUT 5
  
