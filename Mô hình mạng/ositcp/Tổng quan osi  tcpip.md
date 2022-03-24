# I.Tìm hiểu hai mô hình mạng OSI và mô hình TCP/IP

# 1.1 Mô hình OSI

•	Mô hình mạng OSI là 1 mô hình mô phỏng hoạt động của 1 hệ thống mạng gồm có 7 tầng làm việc với các chức năng khác nhau 

•	Application Layer : Giao tiếp người và môi trường mạng .

•	Presentation Layer : Chuyển đổi cú pháp dữ liệu để đáp ứng yêu cầu truyền thông của các ứng dụng 

•	Sesion Layer : Quản lí duy trì liên lạc giữa các thực thể bằng cách thiết lập duy trì , đồng bộ hóa và hủy bỏ các phiên truyền thông giữa các ứng dụng .

•	Trensport Layer : Vận chuyển thông tin giữa các máy chủ(end to end ) . Kiểm soát lôi và luồng dữ liệu.

•	Network Layer : Thực hiện chọn đường và đảm bảo vận chuyển thông tin 1 cách thích hợp 

•	Datalink Layer : Kiểm soát luồng dữ liệu và kiểm soát lỗi 

•	Physical Layer : Đảm bảo yêu cầu truyền nhận các chuỗi bit qua các phương tiện vật lí 

# 1.2 Mô hình TCP/IP

•	Mô hình TCP/IP cũng là một mô hình mô phỏng hại hoạt động của 1 hệ thống mạng và chức năng của từng tầng trong giao thức .

•	Khác với mô hình TCP/IP được chia làm 4 tầng nhưng chức năng cũng giống như mô hình OSI .

•	Các tầng mô hình TCP/IP 

•	Application Layer : Giúp các máy tính giao tiếp dữ liệu thông qua các dịch vụ mạng khác nhau , đồng thời cũng giúp xác định được đường đi đúng cho 1 gói tin .


•	Transport layer : xử lý vấn đề giao tiếp giữa các máy chủ trong cùng một mạng hoặc khác mạng được kết nối với nhau thông qua bộ định tuyến. Tại đây dữ liệu sẽ được phân đoạn, mỗi đoạn sẽ không bằng nhau nhưng kích thước phải nhỏ hơn 64KB. Cấu trúc đầy đủ của một Segment lúc này là Header chứa thông tin điều khiển và sau đó là dữ liệu..

•	Network Layer : Giúp giao thức truyển tải dữ liệu 1 cách logic đồng thời đóng gói dữ liệu.


•	Physic Layer : Giúp giao tiếp dữ liệu giữa các máy tính bằng đường vật lí.


