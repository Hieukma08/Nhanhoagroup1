# I. NAT 
## 1. Khái niệm 
1. NAT là gì ?
- NAT( Network Addrest Translation ) là một kĩ thuật chuyển đổi từ một địa chỉ IP này thành một địa chỉ IP khác . Thông thưởng , NAT được dùng phổ biến trong mạng dử dụng địa chỉ cục bộ , cần truy cập đến mạng cộng đồng .Ví trí thực hiện NAT là router biên kết nối giữa hai mạng .
2.  Nhiệm vụ, cơ chế hoạt động của NAT  của NAT 
- Chuyển tiếp giữa nhưng gói tin giữa các lớp mạng khác nhau 
- NAT được coi như 1 firewall 
- Duy trì một bảng thông tin về mỗi gói dữ liệu được truyền qua 
- Thông qua cơ chế mạng có thể lọc được các gói tin gửi đến hay gửi đi từ địa chỉ IP và cho phép ngăn chặn truy caaoj đến một port cụ thể 
3. Ưu , nhược điểm của NAT 
**Ưu điểm**
- Tiết kiệm địa chỉ IPv4 : lượng người dùng truy cập internet ngày càng tăng cao , điều này dẫn đến nguy cơ thiếu hụt địa chỉ IPv4 . Kĩ thuật NAT sẽ giúp giảm thiểu đưcọ số lượng địa chỉ Ip cần sủ dụng .
- Giúp che giấu IP bên trong mạng LAN 
-  NAT có thể chia sẻ kết nối Internet cho nhiều máy tính và thiết bị di động khác nhau trong mạng LAN chỉ với 1 địa chỉ IP public duy nhất .
- Giúp nhà quản trị lọc được các gói tin đến và xét duyệt được quyền truy cập của IP puclic đến từ 1 port bất kì 
**Nhược Điểm**
- Khi dùng NAT , CPU sẽ phải tốn thời gian để thay đổi địa chỉ IP . Điều này làm tăng độ trễ trong quá trình switch . làm ảnh hưởng đến tốc độ đường truyền , của mạng Internet 
- NAT có khả năng che giấu địa chỉ IP trong mạng LAN nên kĩ thuật viên sẽ khó khăn khi kiểm rea nguồn gốc IP hoặc truy tìm dấu vết của gói tin .
- NAT giấu địa chỉ IP khiến cho 1 số ứng dụng chỉ sử dụng IP không thể hoạt động được 
## 2. Phân loại NAT 
1. Static NAT 
 - Static NAT là phương thức NAT một đôi 1 . Một IP private sẽ được map với 1 IP puclic 
 - NAT tĩnh được sử dụng khi thiết bị cần truy câp từ bên ngoài mạng 

 <img src="/NAT/image/1.jpg">

- Trong Static NAT , địa chỉ IP của máy tính này là 190.168.132.10 luôn được router biên dịch đến địa chỉ IP 213.18.123.110

 2. Dynamic NAT 
 3. Overloading NAT 
 4. Overlapping NAT 
 5. 

