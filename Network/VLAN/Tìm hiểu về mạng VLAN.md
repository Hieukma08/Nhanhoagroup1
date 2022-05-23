# 1. Tổng quan về mạng VLAN
# 1.1 Giới thiệu 

![1](https://user-images.githubusercontent.com/87790053/159643559-3f8cacfa-44b5-47bc-9881-f0dec24ba322.png)

 - VLAN là viết tắt của Virtual Local Area Network hay còn gọi là mạng LAN ảo. Một VLAN được định nghĩa là một nhóm logic các thiết bị mạng và được thiết lập dựa trên các yếu tố như chức năng, bộ phận, ứng dụng… của công ty.
 - Việc đặt các thiết bị vào các VLAN khác nhau có các đặc điểm sau:

   + Cung cấp phân đoạn các nhóm thiết bị khác nhau trên cùng một switch.
   + nCung cấp tổ chức dễ quản lý hơn
   + Broadcast, multicast và unicast được tách biệt trong VLAN riêng lẻ
   + Mỗi VLAN sẽ có dải địa chỉ IP riêng
   + Miền quảng bá nhỏ hơn

# 1.2 Lợi ích của việc sử dụng VLAN
+ VLAN giúp tăng hiệu suất mạng LAN cỡ trung bình và lớn vì nó hạn chế bản tin quảng bá 
+ Tăng tính bảo mật 
+ Giảm chi phí : Một switch  có thể hỗ trợ nhiều nhóm hoặc VLANs khác nhau 
+ Hiệu năng tốt hơn 
+ Quán lí đơn giản hơn 

# 1.3 Phân loại VLAN

- Default VLAN : 

![2](https://user-images.githubusercontent.com/87790053/159647810-4bbab836-98fb-4deb-94fe-987166ca7b08.png)
- Default VLAN 
  - Default NAtive VLAN 
  - Default  Managemant VLAN 
  - Không thể xóa hoặc không thể đổi tên 

- Native VLAN 
  - Chỉ sử dụng cho liên kết trunk
  - Tất cả frame đều được gán nhãn 802.1Q trừ các frame trên Native Vlan
- Data VLAN :
  - Dành riêng cho lưu lượng truy cập của người dùng (email hoặc lướt web)
  - Vlan 1 là default data Vlan bởi vì tất cả các interface đều chỉ định tới với Vlan này
- Management VLAN
  - Được sử dụng cho những traffic VTY telet/ssh và không dùng với traffic end user.
  - Thông thường, Vlan này là SVI cho switch layer 2.

- Voice VLAN : 
![18](https://user-images.githubusercontent.com/87790053/159649891-2f4ed910-64e7-4566-9880-6bb538e0e694.png)

- Cần có 1 Vlan riêng vì Voice Traffic yêu cầu:
  - Băng thông đàm bảo
  - Ưu tiên QoS cao (Quaility of Service)
  - Khả năng tránh tắc nghẽn
  - Trễ ít hơn 150 ms từ nguồn đến đích
  - Toàn bộ mạng phải được thiết kế để hỗ trợ giọng nói

# 2. VLAN là một môi trường Multi Switched 

<img src="/VLAN/image_vlan/4.png">

- Địnhk nghĩa một VLAN trunks
  - Đường trunks là một liên kết  điểm - điểm giwuax hai thiết bị  mạng 
  - Các chức năng chính của Trunk cisco :
    - Cho phép nhiều hơn 1 VLAN 
    - Mở rộng VLAN trên toàn bộ mạng 
    - Thoe mặc định , hỗ trợ tất cả các VLAN 
    - Hỗ trợ 802.1Q trunking 

<img src="/VLAN/image_vlan/5.png">

  - Nếu không cấu hình VLAN , tất cả các thiết bị kết nối với switch sẽ nhật được tất cả các traffic unicast, multicast và brodcast

<img src="/VLAN/image_vlan/6.png">

  - Khi có VLAN , traffic unicast ,multicast and broardcast được giới hạn trong 1 VLAN . Nếu không có thiết bị Layer 3 để kết nối các VLAN với nhau , các thiết bị trong VLAN khác không thể giao tiếp .
- Định nghĩa VLAN với 1 tag 

<img src="/VLAN/image_vlan/7.png">

  - Header IEE 802.1Q có độ dài 4byte được tạo ra  
  - Khi tag được tạo ra , FSC phải được tính toàn lại 
  - Khi gửi tới điểm cuối tag này phải được xóa và FCS được tính toàn lại như lúc ban đầu 

| Trường 802.1Q VLAN tag  | Function |
|:---- |:---|
|Type |2 byte , Với giá trị hex là 0x8100 , được dùng như 1 tag  Protacal ID|
| Ưu tiên người dùng  |3 bit|
| CFI |1 bit , có thể hỗ trợ token ring frame trong Ethernet |
| VLAN ID | 12 bit , hỗ trợ lên đến 4096 VLAN |



# 3. Cấu hình VLAN

<img src="/VLAN/image_vlan/9.png">

- catalyst switch 2960 và 3650  hỗ trọ đến 4000 VLAN 
- Dải Vlan thường từ vlan 1- 1005

  - Sử dụng từ nhỏ đến vừa cho việc kinh doanh
  - 1002 -1005 được lưu trữ lại
  - 1, 1002-1005 được tạo tự động và không thể xóa
  - Lưu trữ tại file vlan.dat trong bộ nhớ flash
  - VTP có thể đồng bộ giữa 2 switch
- Dải Vlan mở rộng từ 2006-4095

  - Được sử dụng bởi nhà cung cấp dịch vụ
  - Luôn chạy ở running-config
  - Hỗ trợ nhiều feature Vlan hơn
  - Yêu cầu cấu hình VTP
- Câu lệnh tạo Vlan

  - Vlan được thông tin chi tiết và lưu trữ tại vlan.dat, nên muốn tạo vlan chúng ta phải vào global config

<img src="/VLAN/image_vlan/10.png">

- Câu lệnh assign port cho vlan.

  - Bất khì vlan nào được tạo, ta đều có thể assign cho nó chính xác 1 interface.

<img src="/VLAN/image_vlan/12.png">


# 4. VLAN Trunk

- Trunk ở layer2 và mang traffic cho tất cả các Vlan.

- Câu lệnh cấu hình trunk



- Ví dụ: Có mô hình :

<img src="/VLAN/image_vlan/14.png"> 

  - Subnet cho từng Vlan là: VLAN 10 - Faculty/Staff - 172.17.10.0/24 VLAN 20 - Students - 172.17.20.0/24 VLAN 30 - Guests - 172.17.30.0/24 VLAN 99 - Native - 172.17.99.0/24
  - F0/1 được cấu hình làm trunk port

<img src="/VLAN/image_vlan/15.png"> 

- Để xác nhận cấu hình trunk, ta dùng câu lệnh : Show int fa0/1 switchport 

<img src="/VLAN/image_vlan/16.png"> 

- Trả về các giá trị:

  - Đã bật switchport
  - Admin mode đã bật
  - Đã bật mode hoạt động cho trunk
  - Đóng gói bằng dot1q
  - Native Vlan là 99
  - Tất cả Vlan được tạo trên Switch đều có thể traffic qua trunk này.
- Để reset một trunk về cấu hình mặc định, ta dùng các câu lệnh:

<img src="/VLAN/image_vlan/17.png"> 
