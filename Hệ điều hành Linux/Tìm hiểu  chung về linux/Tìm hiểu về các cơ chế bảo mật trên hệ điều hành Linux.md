# Cơ chế bảo mật trên Linux 
## Tiến trình độc lập
- Linux được cho là nền tảng bảo mật hơn các hệ điều hành khác bởi các tiến trình luôn chạy độc lập với nhau . Một tiến trình không thể truy cập vào tài nguyên của người khác kể cả nó đang chạy với cùng 1 phiên bản của người dùng . Các cơ chế bảo mật bổ sung đã được giới thiệu để giảm thiểu rủi ro xảy ra . 
  - Control group : Cho phép người dùng quản trị hệ phân nhóm các tiến trình và cấp tài nguyên hữu hạn cho mỗi nhóm 
  - Linux Containers : cho phép chạy nhiều phiên bản Linux trên cùng 1 hệ thống 
  - Virtualization : Phần cứng tách biệt với các tiến trình đồng thời tách biệt với phần cứng mà các máy ảo sử dụng trên cùng 1 host vật lí
- MÃ hóa mật khẩu 
  - Hầu hết các phiên bản của LInux đều sử dụng các cư chế mã hóa mật khẩu bằng thuật toán `SHA-512`
  - SHA-512 được sử dụng rộng rãi nhất để bảo vệ các ứng dụng và giao thức như TLS, SSL ,PHP, S/MINE và IPsec .

- Vòng đời password
  - Pasword là 1 phương pháp để nhức nhờ người dùng tạo 1 mật khẩu mới sau 1 khoảng thời gian dài sửu dụng nhằm nâng cao tính bảo mật  
  - Sử dụng lệnh `change -1 <user> `để xem thông tin mật khẩu người dùng muốn xem .

- Xác thực với Public /Private key 
  - Sử dụng Emcript key để xác thwucj mật khẩu 
  - Khi đã xác thực được mật khẩu  Public key /private key được thiết lập trên máy chủ , ta có thể vô hiệu hóa các thwucj mật khẩu , có nghĩa là không có ủy quyền truy cập . 
