# Spam Filter 
- Để phát hiện và loại bỏ thư rác , Kerio Connect sử dụng các phương pháp sau 
  - `Spam Rating` : Kerio connect kiểm tra từng tin nhắn với tất cả các kiểm tra và bộ lọc đã bật . Dựa trên điểm số spam thu được , nó đánh dấu tin nhắn là spam .
  - `Kerio Anti Spam` : Bộ lọc nâng cao các tin nhắn spam bằng các dịch vụ quét trực tuyến của Bitdefender
  - `Blacklists` : Ta có thể tạo ra một danh sách địa chỉ ip và đưa vào BlackLists để chặn tất cả các thư từ địa chỉ đó 
  - `Custom Rules` : Trong Kerio connect , ta có thể tạo ra các quy tắc chống thư rác riêng của mình , Các quy tắc lọc tiêu đề emial hoặc nội dung email 
  -`Caller ID` and `SPF` : Phương pháp này có thể lọc các thư có địac hỉ gửi giả 
  -`Greylisting`   : giúp chỉ nhận tin nhắn từ những người đã biết 
  - `Spam Repellent` : Đặt SMTP greeting trì hoãn để ngăn việc gửi thư được gửi từ máy chủ thư rác
  