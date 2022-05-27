# Hướng dẫn cài đặt Checkmk trên server Ccentos 7 .
- Mô hình cài đặt check_mk 
  - Mô hình : 
  - Một máy chủ server Centos 7 và hai máy Client là Windows và Ubuntu 
  - Máy Centos 7 : Cấu hình : 2GB RAM , Disk :20 GB
  - Máy Winserver 2016 : Ram 2Gb , Disk 40GB 
  - Máy Ubuntu 20.4 : Ram 4GB , Disk 20GB 

  <img src="/Checkmk/image/1.png">

## Trên máy chủ server Centos 7 : 

- c

- Thiết lập update các package phục vụ cho việc tải và cấu hình phần mềm 
	- ```yum update -y ```
	- ```yum install epel-release wget -y ```
- Thiết lập cấu hình mạng cho máy chủ server 
	- ```ip : 192.168.142.167```
	- ```Subnetmask : 255.255.255.0```
	- ```Getway : 192.168.142.2```
	- ```DNS : 8.8.8.8```

<img src="/Checkmk/image/3.png">


- Thực hiện tắt tường lửa cũng như tắt chế độ bảo mật của Linux 
	- ```Systemctl disable firewalld ```
	- `Systemctl stop firewalld `
- `sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/sysconfig/selinux`
- `sed -i 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config`

- Tiếp theo ta thực hiện cung cấp quyền cho các service của apache và thêm service cho http 

	- `setsebool -P httpd_can_network_connect 1`
	- `firewall-cmd --zone=public --add-service=http –permanent`
	- `firewall-cmd –reload`

- Khi đã cài đặt đủ các package cũng như mở các service , các port hay firewll cho phép cài phần mềm ta tiến hành cài đặt phần mềm checkmk 

- Đầu tiên ta cần kiểm tra phiên bản của Server để có thể chọn được phiên bản phù hợp cho CheckMk 

<img src="/Checkmk/image/4.png">

- Sau khi kiểm tra được phiên bản chúng ta tiến hành vào trang chủ của CheckMk để có thể chọn được phiên bản phù hợp với phiên bản của máy

<img src="/Checkmk/image/5.png">

- Sau khi chúng ta chọn đúng phiên bản ta tiến hành dowload phiên bản về máy : 
	- `wget https://download.checkmk.com/checkmk/2.1.0/check-mk-raw-2.1.0-el7-38.x86_64.rpm`

- Sau khi dowload phiên bản trên về máy ta cần cài đặt một số package để có thể tiến hành cài đặt .

	- `yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm -y `

	- `wget https://download.checkmk.com/checkmk/Check_MK-pubkey.gpg`

	- `rpm --import Check_MK-pubkey.gpg`
	

- Sau khi cài đặt xong các gói chúng ta có thể tiến hành cài đặt phềm mềm bằng lệnh : 
	- `rpm -K check-mk-raw-2.1.0-el7-38.x86_64.rpm`

<img src="/Checkmk/image/6.png">

-  Để kiểm tra phiên bản : 
	- `omd version` 
- Bước tiếp theo ta cần tạo 1 monitoring : 
	- `omd create monitoring` 
- Sau đó chúng ta tiến hành start monitoring 
	- `omd start monitoring`
- Để có thể đổi được mật khẩu chúng ta tiến hành truy nhập vào file config : 

	- `htpasswd -m ~/etc/htpasswd cmkadmin `

Vậy là đã xong phần setup trên máy chủ server 

- Add hosts lên máy Win 16 làm giao diện hiển trị cho server 

<img src="/Checkmk/image/7.png">

- Chúng ta có thể truy cập vào giao diện monitoring theo đường Link : 

`http://checkmk.kmk`

- Khi đó chúng ta sẽ có giao diện quản lí , theo dõi server như hình : 

<img src="/Checkmk/image/8.png">

## Máy Client : Ubuntu 20.4

- Để có thể add 1 host lên check_mk để thực hiện theo dõi service của host đó chúng ta cần làm các bước sau đây 
- Trước tiên cần vào phần setting của monitoring trên Web UI để lấy link dowload agnet : 


	- Ở đây chúng ta có 2 loại file cài đặt : 
	+ *deb : File này dành cho các máy  dùng linux DEBIAN 
	+ *rpm : File này dành cho các máy dùng RHEL 
	 
- Chúng ta dùng máy Client là Ubuntu vì vậy sẽ chọn phiên bản *deb để cài :
- Thực hiện chọn và sao chép địa chỉ liên kết  trên web UI sau đó sao chép địa chỉ để tiến hành tải file đó cài lên máy client Ubuntu :

<img src="/Checkmk/image/9.png">

- Tiến hành tải file agent cài đặt trên máy 
	- `wget  http://checkmk.kmk/monitoring/check_mk/agents/check-mk-agent_2.0.0p24-1_all.deb`


- Tiếp theo chúng ta cần cài Xinetd cho ubuntu 
	-` yum install -y xinetd `
	- `systemctl start xinetd`
	- `systemctl enable xinetd` 

- Sau đó cài đặt bằng lệnh :  `rpm -K check-mk-agent_2.0.0p24-1_all.deb`

- Chúng ta cần truy cập vào file config để có thể chỉnh sửa file check_mk để có thể add host server thực hiện cho việc theo dõi service 

<img src="/Checkmk/image/10.png">

- Thực hiện thay add host server vào đây .

- Vì chúng ta thực hiên trên mỗi trường lab lên cần add hosts vào file host của server để server có thể phân rải được địa chỉ ip : 

<img src="/Checkmk/image/11.png">

- Sau đó chúng ta cần lên web UI để có thể thêm host clien vào máy chủ để có thể thực hiện theo dõi các service 

- Tại màn hình chính chúng ta vào phần setting sau đó chọn hosts 

<img src="/Checkmk/image/12.png">

- Sau đó chúng ta thực hiện add host

<img src="/Checkmk/image/13.png">

Tại đây chúng ta thực hiện cấu hình 
- Đầu tiên chúng ta cần nhập hostname vào để server có thể look up được địa chỉ host
- Sau đó chọn địa chỉ network 
- Tiếp đến chúng ta cần chọn phương thức xác thực để xác nhận checkmk agent 
- Và chọn 1 số các service khác có như SNMP ,….

<img src="/Checkmk/image/14.png">

- Sau đó chúng ta ấn vào Save & go to connection test để có thể test xem server có tìm ra địa chỉ host chưa và có xác nhận được check_mk agent , cũng như các service khác được chưa .

<img src="/Checkmk/image/15.png">

-   chúng ta ấn Save & go to host properties
- Nhấn Save & go to service configuration 
- Tại đây màn hình sẽ hiển thị ra các thông số máy client cũng như các service mà máy client đang chạy

<img src="/Checkmk/image/16.png">

- Bây giờ chúng ta có thể quay lại màn hình Main Dashboard để có thể theo dõi địa chỉ host chúng ta vừa add xong 

<img src="/Checkmk/image/17.png">

- Đây là khi chúng ra đã add thành công và đại chỉ host vẫn đang được hoạt động 1 cách bình thường 
- Còn sau khi địa chỉ host của chúng ta bị down thì màn hình sẽ hiển thị như sau 
- Địa chỉ host đã bị down đồng thời các service cũng đã stop và bên bảng Host problem sẽ hiện ra hostname đã bị down . 

<img src="/Checkmk/image/18.png">



