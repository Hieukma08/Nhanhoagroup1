# Backup data , Sao chép dữ liệu 
- Lệnh `rsync` được sử dụng để đồng bộ hóa cây thư mục , ngoài ra `rsync` kiểm tra xem tập tin đã được sao lưu hay chưa . Nếu tồn tại hoặc không thay đổi về kich thước hay thời gian sửa đổi , `rsync` sẽ tránh 1 bản sao mà không cần thiết và tiết kiệm thời gian . `rsync` chỉ sao chép các phần của tệp đã thay đổi nên nó rất nhanh 
- rsync : hiệu quả khi đệ quy sao chép một cây thư mục qua mạng , vì nó chỉ truyền đi sự thay đổi trong thư mục 
- Người ta thuowfg đồng bộ hóa cây thư mục đích với gốc , sử dụng option `rsync -r` để đẹ quy xuống cây thư mục sao chép tất cả các tệp bên trong tệp được liệt kê dưới dạng nguồn 


## Cài đặt rsync 
- Trên Red Hat? CenOS
  - `yum insstall rsync`
- Trên Debian / Ubuntu 
  - .apt -get install rsync 
  