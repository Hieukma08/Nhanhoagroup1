# Apache
- Là chương trình máy chủ HTTP là một chương trình dành cho máy chủ ddooois thoiaj qua giao thức HTTP . Apache là phần mềm web server đưcọ sử dụng rộng rãi nhất và là 1 phần mềm nguồn mở miễn phí 
# Web server 
- Web server có nhiệm vụ là đưa website lên internet . Để thực hiện được điều đó , nó hoạt động như là 1 người đứng giữa server và client 

# Cách hoạt động của Apache web server

<img src="/Hệ điều hành Linux/image/18.png">

- Apache là một phần mềm chạy trên server, thiết lập kết nối giữa máy chủ và các trình duyệt của người dùng. Trao đổi file theo mô hình client-server.
- Khi người dùng truy cập vào 1 trang web, trình duyệt sẽ gửi request đó đến server. Sao đó, Apache sẽ trả kết quả đầy đủ các file trong website đó như nội dung, hình ảnh, video,... Server và client sẽ giao tiếp bằng giao thức HTTP. Lúc đó Apache sẽ đảm nhiệm về tiến trình này diễn ra mượt mà và bảo vệ 1 cách tối ưu nhất.
- Apache là 1 nền tảng module có độ tùy biến cao. Modules cho phép các quản trị viên server tắt hoặc thêm chức năng. Web server Apache có các mô-đun bổ sung nhiều chức năng hơn cho phần mềm của nó, chẳng hạn như MPM (để xử lý các chế độ đa xử lý) hoặc mod_ssl để bật hỗ trợ SSL v3 và TLS

# Ưu , nhược điểm của Apache 

## Ưu điểm 
- Hỗ trợ miễn phí
- Độ tin cậy và tính ổn định cao: được đánh giá là phần mềm đáng tin cậy và ổn định. Luôn được cập nhật thường xuyên và nâng cấp với nhiều bản vá lỗi bảo mật liên tục.
- Hoạt động đa nền tảng
## Nhược điểm 
- Chiếm khá nhiều bộ nhớ mỗi khi xử lý dữ liệu
- Gặp vấn đề về hiệu năng như kém linh hoạt, sử lý hơi chậm nếu các website có độ traffic cao
- Có nhiều lựa chọn thiết lập có thể gây ra điểm yếu về bảo mật