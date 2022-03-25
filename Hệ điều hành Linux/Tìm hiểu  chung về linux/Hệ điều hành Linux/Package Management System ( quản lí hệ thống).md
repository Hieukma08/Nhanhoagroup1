## Package Mangement System ( Hệ thống quản lí package)
- Các phần cốt lõi của các bản phân phối Linux và hầu hết các phần mềm của nó có được cài thông  qua `packet management System` . Mỗi gói chứa các tệp và các hướng dẫn khác cần thiết để làm cho một thành phần mềm hoạt động trên hệ thống . Các gói phụ thuộc lẫn nhau .
- Có hai lựa chọn quản lí gói : `dpkg` và `rpm` . Hai hệ thống không tương thích nhưng cung cấp cho các tính năng giống nhau ở mức độ rộng rãi .


| High Level Tool | Low Level tool | Family |
| :---------------| :---------     |:-------|
|     zyper       | rpm            | SUSE   |
| yum             | rmp            | Red Hat|

- Cả hai hệ thống quản lí đều cung cấp gói cung cấp 2 mức công cụ : 
  - công cụ cấp thấp , sẽ chăm sóc các chi tiết của giải nén gói cá nhân , chạy các kịch bản , nhận được các phần mềm được cài đặt một cách chính xác .
  - Một công cụ cấp cao hoạt động với các nhóm , tải gói từ nhà cung cấp và tìm ra các phụ thuộc .
- Cài đặt một gói duy nhất có thể dẫn đến hàng chục thậm chí hàng trăm gói phụ thuộc được cài đặt . 



|       Operation                                                    |      RPM                       |     DEbian                      |
|:-----------------------------------------------------------------  | :----------------------------- | :------------------------------ |
|Cài đặt packet                                                      | rpm -i foo.rpm                 | dpkg --install foo.             |
|Cài đặt 1 packet từ repository                                      |   yum install foo              | apt -get install foo            | 
| Xóa 1 packet                                                       |   rpm –e foo.rpm	dpkg          |      --remove foo.deb           |
| Xóa 1 packet lấy từ reponsitory                                    |  yum remove foo 	              |        apt-get remove foo       |
|Update một package tới phiên bản mới hơn	                         |rpm –U foo.rpm	              |dpkg --install foo.deb           |
|Update 1 package sử dụng repository và resolving dependencies       |yum update foo	              |apt-get upgrade foo              |
|Update toàn bộ hệ thống	                                         |yum update                      |	apt-get dist-upgrade            |
|Hiển thị tất cả các package đã cài đặt                              |	yum list installed            |	dpkg --list                     |
|Nhận thông tin về các package được cài đặt bao gồm các file         |	rpm –qil foo                  |	dpkg --listfiles foo            |
|Hiển thị các package có sẵn với "foo" trong tên                     |	yum list foo                  |	apt-cache search foo            |
|Hiển thị tất cả các package có sẵn                                  |	yum list                      |	apt-cache dumpavail             |
|Hiển thị package có chứa "file"	                                 | rpm –qf file                   |	 dpkg --search file             |



