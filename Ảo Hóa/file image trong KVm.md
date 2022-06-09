# Tổng quan về file trong KVM
- file image hay còn gọi là CD/DVD chính là một dạng ổ đĩa có định dạng theo các chuẩn tạo file ảnh . 
- File image là một file đóng gói hết tất cả các nội dung của một đĩa CD/DVD vào trong nó.
- File còn lại là Storage thường được lưu dưới dạng file image tại thư mục /var/lib/libvirt/quemu.
- Định dạng thông dụng nhất của file image sử dụng trong KVM đó là iso và qcow2.
# Định sạng file image phổ biến trong KVM 
1. File iso 
- file iso là file ảnh của 1 ổ đĩa CD/DVD , nó chứa toàn bộ dữ liệu của đĩa CD/DVD đó. File iso thường đưcọ sử dụng để cài đặt hệ điều hành của VM , người dùng có thể import trực tiếp hoặc tải về từ internet.
- Boot từ file iso cũng là một trong số những tùy chọn mà người dùng có thể sửu dụng khi tạo máy ảo.
2. File raw
- Là định dạng file image phi cấu trúc 
- Khi người dùng tạo 1 máy ảo mới có disk format là raw thì dung lượng file disk sẽ đúng bằng dung lượng của ổ đĩa máy ảo của bạn đã tạo 
- Mặt khác khi tạo máy ảo mới với virt-manager hoặc ko khai báo khi tạo VM bằng virt-manager hoặc không khai báo khi tạo VM bằng virt-install thì định dạng ổ đĩa sẽ là raw. hay nói cách khác , raw chính là định dạng mặc định ủa QEMU.
