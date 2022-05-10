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
  -  
