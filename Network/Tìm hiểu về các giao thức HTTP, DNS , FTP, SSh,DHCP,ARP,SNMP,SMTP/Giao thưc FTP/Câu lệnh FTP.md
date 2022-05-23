1. Các lệnh về thư mục

- cd [folder name] : chuyển thư mục
- cd .. : chuyển ra thư mục ngoài
- lcd [local folder] : đặt lại thư mục làm việc trên Client
- dir : liệt kê nội dung thư mục hiện tại trên Server và mổ tả quyền sử dụng
- ls : giống như dir nhưng không mô tả quyền sử dụng
- mkdir [folder name] : tạo thư mục trên Server
- rmdir [folder name} : xóa thư mục
- del [file name] : xóa file trên Server
- mdel/mdelete [files name] : xóa nhiều file trên Server
- pwd : hiện thông tin thư mục hiện tại
- rename [from] [to] : đổi tên file hoặc thư mục [from] thành [to]
2.  Các lệnh về tập tin

- bin / binary : chuyển sang chế độ truyền file theo định dạng nhị phân
- ascii : chuyển sang chế độ truyền file theo định dạng văn bản
- get [file name] : download file trên máy chủ (với file hình ảnh, dùng lệnh bin trước khi dùng lệnh get).Sau khi download, file sẽ lưu tại thư mục hiện tại trên Client
- mget [files name] : download nhiều files
- put [file name] : Upload file lên Server. put [local file] [new file] : Upload và đổi tên là new file
- mput [files name] : Uploa nhiều files lên Server.Trước khi dùng put hoặc mput upload files lên Server, ta nên nén các file thực thi .exe .com để tránh trường hợp không upload được

3. Các lệnh khác

- help [command] / ? / ? tênLệnh: xem hướng dẫn về lệnh
- bell : mở tắt tiếng chuông khi hoàn tất lệnh
- status : xem tình trạng phiên làm việc hiện tại
- system : xem hệ điều hành của Server
- send [LocalFileName] [ServerFileName] : gởi LocalFileName từ Client lên Server với tên mới là ServerFileName
- recv [ServerFileName] [LocalFileName] : nhận ServerFileName trên Server vào lưu vào Client với tên mới là LocalFileName
- close / disconnect : ngắt kết nối
- quit : thoát chương trình FTP
- bye : ngắt và thoát chương trình FTP
- ! : thoát khỏi shell FTP
- open [Hostname] [port number] : kết nối đến Server với tên host là Hostname và ở cổng chỉ định