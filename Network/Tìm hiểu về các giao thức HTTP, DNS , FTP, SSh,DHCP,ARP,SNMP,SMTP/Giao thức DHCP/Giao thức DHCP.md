# I. Tổng quan về giao thức DHCP 
## 1 . Khía niệm 
- Giao thức DHCP là giao thức hoặt động ở lớp Application trong mô hình TCP/IP và là giao thức cấu hình địa chỉ iP, DHCP có 2 version : Cho IPv4 và IPv6, sử dụng port 67,68 và dùng giao thức UDP . 
- DHCP server cấp địa chỉ mạng , phân phối thông số cấu hình tương ứng xuống cho client 
- DHCP có hỗ trợ 3 cơ chế cấp địa chỉ IP 
 - Cấp tự động : DHCP gán cho 1 địa chỉ IP thường trực -> 1 client .
 - Cấp động : DHCP gán địa chỉ Ip cho 1 khoảng thời gian hữu hạn nào đó 
 - Cấp thủ công : 1 địa chỉ IP được gán bởi người quản trị . DHCP chỉ để đưa địa chỉ này đến client . 
- Ngoài ra cơ chế cấp động là cơ chế duy nhất được sử dụng để cấp lại địa chỉ mà không còn được sử dụng nữa trên client cho 1 máy client khác 
## Các thuật ngữ trong DHCP 
- DHCP server : máy chủ quản lí việc cấu hình và cấp phát địa chỉ IP cho client 
- DHCP client : Máy trạm nhận thông tin cấu hình từ DHCP server 
- Scope : Phạm vi liên tiếp của các địa chỉ IP có thể cho 1 mạng 
- Exclusion Scope : là địa chỉ nằm trong Scope không cấp phát cho Clients
- Scope Options : Các thông số được cấu hình thêm khi cấp phát IP động cho clients như DNS server , router 
- Resvervation : Địa chỉ đặt trước dành riêng cho máy tính hoặc thiết bị chạy các dịch vụ 
- DHCP Replay Agent :  DHCP Replay Agent là một máy tính hoặc 1 router được cấu hình để lắng nghe và chuyển tiếp các gói tin giữa DHCP client và DHCP server từ subnet này sang subnet khác 

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức DHCP/image/1.png">

## Gói tin DHCP 

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức DHCP/image/2.png">

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức DHCP/image/3.png">


## Các thông điệp DHCP 
- DHCP Discover: Thời gian đầu tiên một máy tính DHCP Client nỗ lực để gia nhập mạng, nó yêu cầu thông tin địa chỉ IP từ DHCP Server bởi việc broadcast một gói DHCP Discover. Địa chỉ IP nguồn trong gói là 0.0.0.0 bởi vì client chưa có địa chỉ IP.

- DHCP Offer: Mỗi DHCP server nhận được gói DHCP Discover từ client đáp ứng với gói DHCP Offer chứa địa chỉ IP không thuê bao và thông tin định cấu hình TCP/IP bổ sung(thêm vào), chẳng hạn như subnet mask và gateway mặc định. Nhiều hơn một DHCP server có thể đáp ứng với gói DHCP Offer. Client sẽ chấp nhận gói DHCP Offer đầu tiên nó nhận được.

- DHCP Request: Khi DHCP client nhận được một gói DHCP Offer, nó đáp ứng lại bằng việc broadcast gói DHCP Request mà chứa yêu cầu địa chỉ IP, và thể hiện sự chấp nhận của địa chỉ IP được yêu cầu.

- DHCP Acknowledge : DHCP server được chọn lựa chấp nhận DHCP Request từ Client cho địa chỉ IP bởi việc gửi một gói DHCP Acknowledge. Tại thời điểm này, Server cũng định hướng bất cứ các tham số định cấu hình tuỳ chọn. Sự chấp nhận trên của DHCP Acknowledge, Client có thể tham gia trên mạng TCP/IP và hoàn thành hệ thống khởi động.

- DHCP Nak: Nếu địa chỉ IP không thể được sữ dụng bởi client bởi vì nó không còn giá trị nữa hoặc được sử dụng hiện tại bởi một máy tính khác, DHCP Server đáp ứng với gói DHCP Nak, và Client phải bắt đầu tiến trình thuê bao lại. Bất cứ khi nào DHCP Server nhận được yêu cầu từ một địa chỉ IP mà không có giá trị theo các Scope mà nó được định cấu hình với, nó gửi thông điệp DHCP Nak đối với Client.

- DHCP Decline : Nếu DHCP Client quyết định tham số thông tin được đề nghị nào không có giá trị, nó gửi gói DHCP Decline đến các Server và Client phải bắt đầu tiến trình thuê bao lại.

- DHCP Release: Một DHCP Client gửi một gói DHCP Release đến một server để giải phóng địa chỉ IP và xoá bất cứ thuê bao nào đang tồn tại.

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức DHCP/image/4.png">

## Ưu , nhược điểm của gioa thức DHCP 
### Ưu điểm 
- DHCP cho phép cấu hình tự động nên có tác dụng giúp các thiết bị kết nối mạng nhanh chóng từ máy tính, laptop, điện thoại, máy tính bảng…
- DHCP giúp quản lý địa chỉ IP một cách khoa học, tránh trường hợp trùng IP trên nhiều, đảm bảo cấu hình tự động cho mọi thiết bị kết nối mạng.
- DHCP quản lý cả địa chỉ IP và các tham số TCP/IP trên cùng một màn hình nên có thể dễ dàng theo dõi các thông số và quản lý chúng qua các trạm.
- Để nâng cấp cơ sở hạ tầng các nhà quản trị mạng có thể thay đổi cấu hình và thông số của IP.
- Người quản lý khi đánh tự động nhờ máy chủ DHCP giúp cho việc quản lý khoa học hơn và tránh bị nhầm lẫn
- Các thiết bị có thể di chuyển tự do giữa các mạng và nhận IP mới tự động.

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức DHCP/image/6.png">

### Nhược điểm 
- Với các thiết bị cố định và cần liên tục và cần truy cập liên tục như máy in , file server thì không phù hợp sử dụng IP động của DHCP vì khi kết nối với máy tính khác thì máy in sẽ phải thường xuyên cập nhật để cài đặt máy tính có thể kết nối với máy in 
- DHCP thường chỉ sử dụng tại các hộ gia đình hoặc mô hình mạng nhỏ 
