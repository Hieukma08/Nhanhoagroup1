








# 1. Tìm hiểu về Swap memory trên Linux 

##  1.1 Swap là gì ?

- Swap hay còn được gọi là RAM ảo được sử dụng để hỗ trợ lưu trữ dữ liệu khi bộ nhớ vật lý (RAm) đầy . Đôi khi SWAP cũng được dùng song song để làm tăng dung lượng bộ nhớp đệm . SWAP thường dùng trên các hệ điều hành Linux , Unbuntu hoặc CENTOS .
- Swap sẽ làm nhiệm vụ thay thế RAm khi bộ nhớ vậy lí đầy nhưng sẽ có tốc độ xử lí rất chậm .
## 1.2 Khi nào cần dùng Swap memory 
- Tối ưu hóa hheej thống bộ nhớ : Hệ thống sẽ di chuyển các tài nguyên và dữ liệu không sử dụng bộ nhớ Ram đêbs Swap , điều này giúp hệ thống phục vụ vho các mục đích khác tốt hơn 
- Linux swap có 2 dạng : Phân vùng và file : Để xem nso ở đâu dùng câu lệnh `swapon`

<img src="/Hệ điều hành Linux/image/13.png">

## 1.3 Tạo file swap 
- Tạo file Swap 
    `dd if=/dev/zero of=/swapfile bs=1024 count=1048576`

> Trong đó `bs`  là kích thước của file Swap file ,`count` là tốc độ 
- Phân quyền cho `swapfile` . CHỉ có root với có thể có quyền truy cập `chmod 6000  / swapfile`
- Sử dụng `mkswap` để thiết lập file là file swap `mkswap/swapfile `
- Khởi động swap file  `swap/sưapfile`
- Mở file `/etc/fstab` và thêm vào dòng cuối cùng 

`$ sudo echo '/swapfile swap swap defaults 0 0' | sudo tee -a /etc/fstab`

- Kiểm tra phân vùng  Swap : `swapon `
- Giá trị của Swapiness 
  - Giá trị của swapiness từ 0 -> 100 . Chỉ số này càng thấp thì máy linux sẽ tranhs ử dụng swap file này , càng coa thì càng ưu tiên sử dụng nó . Ta có thể thay đổi giá trị file này tại : `/proc/sys/vm/swappiness`
- Xóa swap file 
  - Để có thể xóa swapfile , có thể deactive swap file : `swapoff -v /swapfile`
  - Xóa dòng khai báo swap tại file /etc/fstab
  - Cuối cùng để xóa ta dùng lệnh rm `rm -rf /swapfile`
# 1.4. Dung lượng cần thiết của bộ nhớ SWAP
- Nếu RAM ít hơn hoặc bằng 1Gb, thì nên sử dụng Swap có kích thước tối thiểu là bằng với lượng RAM
- Đối với RAM trên 1Gb, thì kích thước tối đa thường là gấp đôi lượng RAM. Nếu thiết lập kích thước của Swap quá lớn chính là đang lãng phí dung lượng ổ đĩa mặc dù Swap không được sử dụng
- Thời gian truy cập trên Swap sẽ chậm hơn so với trên RAM


