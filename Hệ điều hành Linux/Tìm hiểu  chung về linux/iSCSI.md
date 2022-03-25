# SCSI 
## Khái niệm 
**iSCSI**
- iSCSI : là internet SCSI ( Smail computer Sytem interface) : Là 1 giao thức cho phép truền tải các lệnh SCSI qua mạng bằng IP bằng cách sử dụng giao thức TCP/IP . Nó truy cập thiết bị lưu trữ thoe dạng block-level ( truy cập theo từng khối)
- Lệnh iSCSI được đóng gói trong lớp TCP/IP và truyền qua trong nội bộ LAN hoặc cả qua mạng Internet Public 

## Thành phần của iSCSI
- iSCSI Inititor : Là thiết bị client trong kiến trúc hệ thống lưu trữ qua mạng 
- iSCSI Target : Thường là 1 máy chủ lưu trữ 

## Cài đặt 

- `yum -y install targetcli`
- Để khởi động ta dùng lệnh # targetcli, sau đó `# ls` để được bố cục giao diện dạng cây

<img src="/Hệ điều hành Linux/image/12.png">

