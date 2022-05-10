# Giới thiệu về FirewallD 
- Firewalld là giải pháp tường lửa mạnh mẽ tương tự như Firewall CSF , được cài đặt mặc định trên RHEL 7 và Centos 7 , nhằm thay thế iptables với những khác biệt cơ bản như :
- FirewallD sử dụng 'zones' và 'service' thay vì 'chain' và 'rules' trong iptables 
- FirewallD quản lí các quy tắc đưcọ thiết lập tự động , có tác dụng ngay lập tức mà không cần mất đi các kết nối với sesion hiện có 

# ZONE
- Trong firewalld , zone là một nhóm các quy tắc nhằm chỉ ra những luồng dữ liệu được cho phép , dựa trên mức độ tin tưởng của điểm xuất phát luồng dữ luệ đó trong hệ thống mạng 
- Các Zone được xác định trước theo mức độ tin cậy , theo thứ tự  từ `ít tin cậy nhất` đến `đáng tin cậy nhất`
  - DROP : ít tin cậy nhất - toàn bộ kết nối đến sẽ bị từ chối mà không phản hồi , chỉ cho phép duy nhất kết nối đi ra 
  - block : Tương tự như drop nhưng kết nối đến bị từ chối và phản hồi bằng tin nhắn từ icpm-host-prohibited
  public : đại diện cho mạng công cộng , không đáng tin cậy . CÁc máy tính /service khác không được tin tưởng trong hệ thống nhưng vẫn cho phép các kết nối đến trên cơ sở chọn từng trường hợp cụ thể 
  - External : Hệ thống mạng bên ngoài trong trường hợp bạn sử dụng tường lửa làm gatewayt , được cấu hình giả lập NAT để giữ bảo mật mạng nội bộ mà vẫn có thể truy cập được 
  - Internal : đôi lập với external zone , sử dụng cho phần nội bộ của gateway , CÁc máy tính thuộc zone này thì khá đáng tin cậy . 
  - DMZ : sử dụng cho các máy tính trong khu vực DMZ , cách li ko cho phép truy cập vào phần còn lại của hệ thống mạng 
  - work : Sử dụng trong công việc , tin tưởng hầu hết các máy tính khác và thêm 1 vài service khác được cho phép hoạt động 
  - home : môi trường gia đình - tin tưởng hầy hết các máy tính và thêm 1 vài service được cho phép hoạt động .
  - trusted : đáng tin cậy nhất và tin tường toàn bộ hệ thống 
  # Quy tắc RUNTIME /Peramnet 
  -  Trong firewalld , các quy tắc được cấu hình thời gian hiệu lực Runtime hoặc permanent 
    - Runtime : có tác dụng ngay lập tức , mất hiệu lực khi reboot hệ thống 
    - Permannet : Không áp dụng cho hệ thống đang chạy , cần reload mới có hiệu lực , tác dụng vĩnh viễn ngay cả khi reboot hệ thống 
    # Cài đặt firewallD
    - Firewalld được cài đặt mặc đinh trên CentOS 7 , Cài đặt nếu chưa có 
      - yum install firewalld 
    - Khởi động FirewallD 
      - systemctl start firewalld
    - Kiểm tra hoạt động 
      - Systeamctl status firewalld 
    - Thiết lập firewalld khởi động cùng hệ thống 
      - Systemctl enable firewalld
    - Ban đầu bạn không nên cho phép firewalld khởi động cùng hệ thống cũng như thiết lập permanent,tránh bị khóa khỏi hệ thống nếu như thiết lập sai . Chỉ thiết lập như vậy khi bạn hoàn thành các quy tắc tường lửa cũng như đã test cần thận 
    - Khởi động lại 
      - systemctl restart firewalld
    - Dùng và vô hiệu hóa Firewall 
      - systemctl stop firewalld
      - systemctl disable firewall
# Cấu hình firewalld
## Thiết lập các zone 
- Liệt kê các zone có trong hệ thống 
  > firewall-cmd --get-zones
- Kiểm tra các zone mặc định 
  > firewall-cmd --get-defult-zone
- Kiểm tra zone active ( Được sử dụng bởi giao diện mạng)
  - Vì FirewallD chưa được thiết lập bất kì 1 quy tắc nào nên zone mặc định cũng đồng thời là zone duy nhất được kích hoạt , điều khiển mọi luồng dữ liệu 
  - firewall-cmd --get-active-zones
- Thay đổi zone mặc ddunhj , vd thành home 
  - firewall-cmd --set-default-zone=home
# Các lệnh liệt kê : 
- Liệt kê toàn bộ quy tắc của zones
>firewall-cmd --list-all-zones
- Liệt kê toàn bộ các quy tắc của zone mặc định và zone active 
> firewall-cmd --list-all
- Liệt kê toàn bộ các quy tắc trong 1 zone cụ thể , vd home :
> firewall-cmd --zone=home --list-all
- Liệt kê dánh sách service /port được cho phép cụ thể ; 
> firewall-cmd --zone=public --list-services
> firewall-cmd --zone=public --list-pots



# Thiết lập Service
- Đây chính là điểm khác biệt của firewallD với iptable - quản lí thông qua các service . Việc  thiết lập tường lửa đã trở lênh dễ dàng hơn bao giờ hết - chỉ cần thêm các service vào zone đang sử dụng 
- Đầu tiền , xác định các service trên hệ thống 
  - firewall-cmd --get-services
- Thông thường cần cho phép các services sau : ssh(22/tcp) ,http(80/tcp),https(443/tcp), smtp(925/tcp),smtp-submission(587/tcp)
- Thiết lập cho phép service trên firewalld sử dụng --add-service
  - firewall-cmd --zone=public --add-service=http
  - firewall --zone=public --add-service=http --pẻmanent
- Ngay lập tức ,zone "public " cho phép kết nối với HTTP trên cổng 80 . Kiểm tra lại 
  - firewall-cmd --zone=public --list-service 
- vô hiệu hóa services trên firewalld , sử dụng -remove-service
  - firewall-cmd --zone=public --remove-service=http
  - firewall-cmd --zone=public --remove-service=http --permanent 
# Thiết lập cho port 
- Mở port với tham số --add-port
  - firewall-cmd --zone=public --add-port=80/tcp
  - firewall-cmd --zone=public --add-port=443/tcp
- Mở 1 dải port : 
  - firewall-cmd --zone=public --add-port=4990-5000/tcp --permanent 
- Kiểm tra lại : 
  - firewall-cmd --zone=public --list-port
- Đóng port với tham số -remove-port
  - firewall-cmd --zone=public --remove-port=999/tcp
  - firewall-cmd --zone=public --remove-port=999/tcp --permanent






