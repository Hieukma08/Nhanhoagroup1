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