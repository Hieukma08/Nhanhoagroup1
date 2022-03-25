# 1. Các lệnh cơ bản trên hệ điều hành linux
- `#exit` hoặc `#logout` : Thoát ra khỏi trạng thái đăng nhập 
- `#reboot`: Khởi động lại hệ thống 
- `#ps` : Liệt kê các tiến trình đang hiện hành và PID của tiến trình đó 

<img src="/Hệ điều hành Linux/image/3.png">

- `#sleep < thoi_gian>` : Cho phép hệ thống ngừng hoạt động trong 1 khoảng thời gian ( thời gian tính bằng giây ) . ví dụ : `#sleep` , thì máy chủ sẽ tạm thời ngừng hoạt động trong 6 giây . 
- `#useradd <ten_user> : `: Thêm 1 user vào hệ thống 
- `#passwd<ten_user>`: Cập nhật mật khẩu cho user đã tạo 

> Sau khi tạo xong user cho hệ thống ta kiểm tra xem user đã được thêm hay chưa
- `who` : CHo biết user nào đang sử dụng hệ thống 
- `whoami` : Cho biết user nào đang đăng nhập hệ thống . 

<img src="/Hệ điều hành Linux/image/4.png">

- `top` : hiển thị các tiến trình đang chạy trên hệ thống . Tương tự như task manager của windowns .
- `usermod -aG wheel <username>: cho phép user sử dụng quyền sudo .
- `su -<username >: đăng nhập bằng user khác .

<img src="/Hệ điều hành Linux/image/5.png">

- Nhấn tổ hợp phím " Ctrl + l " hoặc `#clear` để làm sạch commaind
- Nhấn `ifconfig` để xem cấu hình mạng 

<img src="/Hệ điều hành Linux/image/6.png">

- `history` : để xem lịch sử đã đưucọ thực thi bởi user hiện tại 
- `pwd` : Hiển thị đường dẫn tại nơi hiện hành 
- `date` : Kiểm tra ngày giờ trên máy 
- `free` : kiểm tra RAM của máy 
  - -b : Hiển thị dưới dạng byte 
  - -k : Hiển thị dưới dạng KB 
  - -m : Hiển thị dưới dạng MB 
  - -g : Hiển thị dưới dạng GB 

<img src="/Hệ điều hành Linux/image/7.png">

<img src="/Hệ điều hành Linux/image/8.png">

- `hostnamectl` : Xem thông tin của hostname hiện tại .
- `uname` : Kiểm tra hệ điều hành đang sử dụng 
- `yum` : Cập nhật hệ thống 
- `init 0` : Tắt máy
- `nit 6` : Khởi động lại máy 
- `w` : Kiểm tra các phiên bản SSH 
- `df -h` : Hiển thị dung  lượng ổ cứng của máy ( dung lượng sẵn sàng và dung lượng đã được sử dụng )
- `df -i` : Hiển thị thông tin Inodes của các máy( Tổng số file còn có thể tạo ra , số file đã được tạo ra )

<img src="/Hệ điều hành Linux/image/10.png">

<img src="/Hệ điều hành Linux/image/11.png">

# 2. Thao tác với tập tin 
- `ls` : Xem danh sách các file và thư mục hiện hành 
- `ll` : xem danh sách các file và thư mục hiện hành chi tiết 
- Chuyển thư mục ( Change directory ) : `cd`
  - cd/etc/selinux : CHuyển tới thư mục /selinux/
  - cd: Chuyển về thư mục chính của người dùng 
  - cd A && ls  : chuyển tới thư mục A và hiển thị danh sách file và các danh sách thư mục của nó 
- Tọa 1 thư mục mới : `mkdir <tên thư mục >`
- Tạo 1 tập tin : `touch < tên tập tin>`
- tạo tập  tin dạng text : `echo "" >> ~/<tên tập tin>`
- Xóa tập tin : `m`
  - xóa 1 tập tin : `rm`
  - Xóa nhiều tập tin : `rm <tập tin 1><Tập tin 2>`
  - Xóa tập tin theo đường dẫn : `rm /a/b/c/<tập tin>`

- Xóa thư mục: `# rmdir`
- `# rmdir <ten_thu_muc>`: hoặc # rm -d: Xóa 1 thư mục rỗng
- `# rm -r <ten_thu_muc>`: Xóa thư mục chứa các thư mục con và tập tin (có xác nhận cho từng đối tượng)
- `# rm -rf <ten_thu_muc>`: Xóa thư mục chứa các thư mục con và tập tin (không xác nhận)
- Mở tập tin: `# cat <tap_tin>` hoặc` # tail <tap_tin>`
- Khởi động trình soạn thảo VI:
- Câu lệnh `# vi <ten_file>`
- Nếu file chưa tồn tại thì hệ thống sẽ tạo ra file đó
- Nhấn phía `"i" ` `(Insert)`: Để chỉnh sửa văn bản
- Nhấn phím` "ESC"` để thoát khoải trạng thái nhập
- Nhập :wq (Để lưu lại file sửa đổi) hoặc :q! (Để thoát mà không lưu)
- Nhập `: <so_dong>`: Để chuyển đến dòng muốn tới
- Nhập `/ <tu_muon_tim_kiem>`: Để tìm kiếm trong file file đó
- Copy file: `# cp`
- Copy file A thành file B tại thư mục hiện hành
 `cp A.txt B.txt `
- Copy nhiều file vào 1 thư mục khác. Ví dụ: Copy file A.txt, B.txt, C.txt, D.exe, E.exe vào thư mục tu vừa tạo
 `mkdir tu`
 `touch ./{A,B,C}.txt`
 `touch ./{D,E}.exe`
 `cp A.txt B.txt C.txt D.exe E.exe tu/`
- Copy file từ thư mục này sang thư mục khác. Ví dụ: - Copy file A.txt từ thư mục tu sang thư mục B
 `mkdir B`
 `cp /tu/A.txt B`
- Để xem thông tin copy ta thêm `-v`. Ví dụ
 `cp -v A.txt B.txt C.txt D.exe E.exe tu/`
 `"A.txt" -> "tu/A.txt"`
 `"B.txt" -> "tu/B.txt"`
 `"C.txt" -> "tu/C.txt"`
 `"D.exe" -> "tu/D.exe"`
 `"E.exe" -> "tu/E.exe"`
- Để giữ nguyên thuộc tính file khi copy ta thêm -p. - Các thuộc tính giữ nguyên là: access time, modification date, user ID, group ID, file flag, file mode, access control lists
 `cp -p /tu/A.txt B`
- Copy thư mục: tương tự file. Ta thêm -a hoặc -r
`-r`: Copy toàn bộ thư mục hoặc file con của thư mục được copy
`-a`: Bao gồm option -r và thực hiện duy trì các thuộc tính của file hoặc folder như file mode, ownership, timestamps...
- Copy không cho ghi đè: thêm `-n`
- Copy cho ghi đè không cần xác định `-f`
- So sánh 2 tệp tin hoặc 2 thư mục `diff`
