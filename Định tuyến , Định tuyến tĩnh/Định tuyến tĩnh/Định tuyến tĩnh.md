# Khái niệm 
- Định tuyến tĩnh là phương pháp định tuyến theo phương thức người quản trị khai báo thông tin định tuyến thông qua phương thức thủ công .
# Ưu điểm, Nhược điểm 
- Ưu điểm 
  - Sử dụng ít băng thông hơn so với các phương thức định tuyến khác 
  - Không tiêu tốn tài nguyên để tính toán và phân tíc gói tin định tuyến 
  - Dễ dàng triển khai , cấu hình 
  - Có tính bảo mật tốt hơn 
- Nhược điểm   
  - Không có khả năng cập nhật đường đi 
  - Phải cấu hình thủ công khi mạng có sự thay đổi 
  - Khả năng mở rộng kém , phù hợp với mô hình mạng nhỏ 
- Những trường hợp triển khai định tuyến 
  - Đường truyền có băng thông thấp 
  - Người quản trị cần kiểm tra tất cả các kết nối trong hệ thống 
  - hệ thống có các tuyến kết nối ít 
  - Kết nối dùng định tuyến là đường dự phòng cho đường kết nối dùng giao thức định tuyến động 

- Phương thức triển khai định tuyến tĩnh : next hop or Exit interface 
  - Next hop : Thông tin sẽ chuyển đến router kế tiếp nào trước khi đến đích 
  - Exit Interface : Thông tin sẽ được chuyển đưa ra cổng nào trước khi đến đích  