# Process 
 - Mỗi lệnh trên Linux khi thực hiện sẽ `run` một process hoặc `  group các process
## 1. Tổng quan
- Tất cả các chương trình trong Linux thực chất là các process . Process chính là đơn vị cấu thành trên Linux .
## 2. Kiểm tra tất cả các process đang chạy trên hệ thống 
- Sử dụng lện `ps` và show thêm cá thuộc tính `opid, ppid,user,rss,comand` của process 

<img src="/Hệ điều hành Linux/image/15.png">

> Ta có thể thấy mỗi process có một process ID khác nhau và thuộc về một process ID cha nào đó 
## 3. Kiểm tra live các process đang chạy 

- `top`

 <img src="/Hệ điều hành Linux/image/16.png">

 -Thông tin được hiên thị 

- Dòng 1 : 
  - Thời gian 
  - Máy tính đã chạy được bao lâu rồi 
  - Số lượng người dùng 
  - Trung bình tải 
  - Trung bìn tarihieenr thị thời gian load hệ thống trong 1,5 và 15 phút cuối 
- Dòng 2 
  - tổng số nhiệm vụ 
  - Tổng số tác vụ đang chạy 
  - Số lượng tác vụ đang trong trang thái ngủ 
  - Số  lượng tác vụ zombie 
- Dong 3: 
  - Mức sử dụng CPU bởi người dùng theo tỉ lệ phần trăm 
  - Mức sử dụng CPU bởi hệ thống sử dụng tỉ lệ phần trăm 
  - Mức sử dụng CPU  bởi các mức tiến trình có mức ưu tiên thấp  theo tỉ lệ phần trăm 
  - Mức sử dụng CPU  tạo bởi io wait theo tỉ lệ phần trăm 
  - Mức sử dụng CPU bởi việc ngắt phần cứng theo tỉ lên phần trăm 
  - Mức sử dụng CPU bởi việc ngắt phần mềm thoe tỉ lệ phần trăm 
  - Mức sử dụng CPU sở steal time theo tỉ lệ phần trăm 
- Dòng 4 :
  - Tổng bộ nhớ hệ thống 
  - Bộ nhớ trống 
  - Bộ nhớ đã sử dụng 
  - Bộ nhớ đệm bufer cache 
 - Dòng 5 
   - Tổng swap có sẵn 
   - Tổng swap còn trống \
   - Tổng swap đã sử dụng 
   - Bộ nhớ khả dụng 
- bảng chính 
  - ID tiến trình 
  - Người dùng 
  - Mức độ ưu tiên 
  - Mức độ nice 
  - Bộ nhớ ảo đã được sử dụng bởi tiế trình 
  - Bộ nhớ có thể chia sẻ 
  - CPU được sử dụng  bới tiến trình theo tỉ lệ phần trăm 
  - Bộ nhớ được sử dụng bởi tiến trình theo tỉ lệ phần trăm 
  - Thời gian tiến trình đã chạy đc
  - Lệnh 
## 4 . Sơ đò pstree
- Lệnh `pstree` hiển thị các quy trình đang chạy trên hệ thống dưới dạng sơ đồ cây thể hiện mối quan hệ giữa một quy trình và quy trình mẹ của nó và bất kỳ quy trình nào khác mà nó tạo ra

<img src="/Hệ điều hành Linux/image/17.png">