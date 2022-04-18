# Hệ cơ sở dữ liệu Mysql 
## Tổng quan
1. Khái niệm

- myysql là chương trình để quản lí hệ thống cơ sở dữ liệu , trong đó CSDL là một hệ thống lưu trữ thông tin được sắp xếp rõ ràng , phân lớp ngăn nắp những thông tin mà mình lưu trữ .
- Tại sao nên sử dụng mySQL 

  - Khả năng mở rộng và tính linh hoạt 
  - Hiệu năng cao 
  - Tính sẵn sàng cao 
  - Điểm mạnh của web và Data Warehouse 
  - Bảo vệ dữ liệu mạnh mẽ 
  - Phát triển ứng dụng toàn diện 
  - Quản lí dễ dàng 
  - Mã nguồn mở tự do và hỗ trợ 24/7
  - Chi phí sở hữu thấp nhất 

2. Các câu lệnh trong hệ quản trị cơ sở dữ liệu mysql 

- Câu lệnh truy vấn : `Select *`
- Câu lệnh lọc dữ liệu : `Distinct`
- Câu lệnh tìm kiếm nhằm giới hạn phạm vi tìm kiểm : `Wherw`
- Câu lệnh điều kiện : `Or` hoặc `and`
- Câu lệnh tìm kiếm dữ liệu theo giá trị tìm kiếm : `in`
- Câu lệnh điều kiện : `Between`
.......
- SQL Like : ( Giống với)
- SQL Order By ( Sắp xếp bởi )
- SQL Group By ( Nhóm bởi )
- SQL Having : Là 1 câu lệnh điều kiện của group by 
- Cấu lệnh chèn dữ liệu : Insert :
- Câu lệnh xóa dữ liệu : Delete
- C âu lệnh đếm sối dùng : SQL count 
- Câu lệnh tính tổng : SQL SUM 
- Câu lệnh tính trung bình trên cột : AVG
- Câu lệnh tìm giá trị nhỏ nhất, lớn nhất  : MIn , MAX


## Cách cài đặt cơ sở dữ liệu mysql trên hệ điều hành Linux ( Centos 7 )
 1. Bước 1 : 
 **Thực hiện tải các bản yum mới nhất từ trên mạng về phục vụ cho việc cài sql**
 - `yum update `: 
 
 <img src="/Tìm hiểu về các cơ sở dữ liệu/MySQL/image/1.png">

**Tải yum sql từ trên mạng về máy tính**

- `wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm`

<img src="/Tìm hiểu về các cơ sở dữ liệu/MySQL/image/2.png">

**Tiếp tục tiến hành cài đặt mysql server**

- `yum install mysql-server`

- Hiển thị như sau là thành công 

<img src="/Tìm hiểu về các cơ sở dữ liệu/MySQL/image/3.png">

- **Sau khi ta cài đặt cho root xong muốn truy cập từ xa thì ta cần mở port 3306 trong bảng iptable 
  - `iptables -I INPUT -p tcp -m tcp --dport 3306 -j ACCEPT`
- Sau khi cài đặt xong mysql ta cần tạo ra user để có thể đăng nhập được mysql . Để tạo được user thì ra có thể thêm vào cuối mỗi câu lệnh cần có dấu `;` hoặc `/g`
  - create user 'user-name'@'IP' identified by 'password';
- Trong đó 
  - username : Tên của user ;
  - Ip : Máy có thể truy cập user này muốn tất cả các user đều đăng nhập được ta đều đăng nhập được ta để `%`;
  - password : Mật khẩu đăng nhập

- Để kiểm tra phiên bản sql đã cài ta dùng lệnh `SELECT version`

<img src="/Tìm hiểu về các cơ sở dữ liệu/MySQL/image/4.png">

- Đăng nhập vào database bằng user : 

<img src="/Tìm hiểu về các cơ sở dữ liệu/MySQL/image/5.png">
