# CÁC ỨNG DỤNG THEO CẤU TRÚC NGANG HÀNG 
- Ứng dụng Peer to peer 
  - Chia sẻ các tìa nguyên và dịch vụ phân trán : Các nút thành viên vừa đóng vài trò client vừa đóng vài trò server 
  - Không tập trung : Truyền thông các nút diễn ra trực tiếp , các nút bình đẳng với nhau , không ai chi phối ai 
  - Tự trị : Mỗi nút mạng tự quyết định khi nào tham gia vào mạng với mức độ đóng góp chia sẻ cho cộng đồng 
- Các ứng dụng P2P có thể phân loại theo 3 nhóm sau đây 
  - Nhắn tín tức thì ( instant messaging )
  - Chia sẻ file 
  - Tính toán mạng lưới 
##  1.1 Nhắn tin tức thì (Instant messaging _IM)
- Chức năng của IM
  - dịch vụ hiển thị thông tin ( Presense Service) : là dịch vụ quan trọng nhất trong trong hệ thống IM , xác định có thể liên lạc được với đối tượng hay không và trạng thái của đối tượng đó . Ngoài ra còn cung cấp cơ chế bảo đảm tính riêng tư 
  - Dịch vụ chuyển phát tin nhắn giữa những người sử dụng trên mạng IM 
  - Các dịch vụ bổ trợ ( liệt kê trong RFC2778 và RFC2779)
- Các thành phần của IM
  - IM server
  - Cung cấp các dịch vụ như hiển thị tông tin hay , cảnh báo , đăng kí tài khoản và nhắn tin 
  - Có thể gồm nhiều server cùng làm việc 
  - Truyền thông giữa các server thường trong suốt 
  - Im Client : Phần mềm client là điểm giao tiếp của người sử dụng với mạng IM. Sau khi cài đặt thì có thể kết nối và sử dụng các dịch vụ do bên IM server cung cấp
- Mô hình kết nối 
  - Client - Server : hay là kiểu tập trung : Tất cả các thông tin trao đổi đều đi qua server 
  - Peer to peer hay kiểu phân tán : Dữ liệu được trao đổi qua trực tiếp giwuax các Client ( Không đi qua server )
- Cấu hình Server: để tăng khả năng mở rộng , hệ thống IM có thể sử dụng 1 hay nhiều Server 
  -  Kiến trúc 1 Server : Mọi dịch vụ đều được thực hiện trên 1 server duy nhất . Kiến trúc này dễ dàng bảo trì , tăng cường khả năng bảo mật nhưng lại khó thể mở rộng hệ thống 
  - Kiến trúc nhiều Server : Server được chia thành hai loại đó là Nhân bản và dịch vụ phân tán 
     - Nhân bản : Mỗi server có thể thực hiện tất cả các dịch vụ của IM . Các server giống hệt nhau và được kết nối lại với nhau 
  - Dịch vụ phân tán : Các dịch vụ khác nhau đươc cài đăt trên các server khác nhau 
## 1.2 Kiến trúc hệ thống MSN
*Hệ thống IM được sử dụng rộng rãi nhất hiện nay là: AIM và MSN .*
**MSN Protocol(MNSP)**
- Server và Client trong mạng MSN trao đổi các lệnh theo chuẩn UTF_8 qua TCP socket 
- Có 3 kiểu server : Dispatch server ( DS ) , Notification server ( NS ) và Switchboard (SS)
  - Nhiệm vụ của DS : Thỏa thuận sử dụng phiên bản giao thức này với client , sau đó xác định server NS nào đó kiểm soát người dùng . Sau đó xác định địa chỉ NS được chuyển cho Client
  - Ns là thành phần quan trọng nhất của mạng IM : sau khi đăng nhập thành công , NS và client phải đồng bộ với nhau về trang thái cũng như trao đổi thông tin di bộ . Yê cầu làm việc với làm việc với SS.
  - SS là thành phần trợ giúp client tạo các phiên hội thoại , chuyển tin nhắn giữa các client .
## 1.3 Kiến thức chia sẻ file ngang hàng Gnutella
**Kiến trúc Gnutalla** : Gồm các nút ngang hàng nhau (peer ) , có thể đôi một kết nối với nhau 
- Các nút này gọi là servent , vì vừa đóng vài trò client( khi yêu cầu nút khác ) lẫn server( khi đáp ứng nút khác ) . Các nút có bản ghi khác ghi thông tin chỉ mục về toàn bộ ( hoặc 1 phần ) hệ thống 
- Muốn gia nhập mạng Gnutella , nút xác nhận địa chỉ một nút đã năm ftrong mạng Gnutella
**Khuân dạng thông điệp giao thức của Gnutella** :
- Ping : Phát hiện các nút trên mạng . Mỗi nút nhận được thông điệp Ping có thể trả lời bằng 1 hoặc nhiều thông điệp Pong
- Pong : Thông điệp trả lời cho Ping , chỉ chưa địa chỉ và các thông tin của nút 
- Query : Thông điệp phcu vụ mục đích tìm kiếm trên mạng . Nếu nhận được truy vẫn mà có dữ liệu đáp ứng được , nút gửi thông điệp Query trả lời 
- Query Hit : Thông điệp trả lờ Query . Cung cấp các thông tin cần thiết để phía tìm kiếm có thể tải file 
- Push : Được các nút đăng sau firewall sử dụng khi muốn truyền dữ liệu cho nút khác 
**Các thông tin tiêu đề**
1. Ping
  - Thông điệp không có dữ liệu 
2. Pong

Ping: Thông điệp Ping không có dữ liệu
Pong: pong
Dữ liệu trong thông điệp Pong có bốn phần. Thông điệp Pong được gửi để trả lời thông điệp Ping.

- Port: số hiệu cổng Host chấp nhận kết nối
- IP Address: địa chỉ IP của nút
- Files Shared: Số lượng file mà host chia sẻ
- Kilobytes Shared: Số lượng KB host đã chia sẻ
3. Query
Query

- Là thông điệp truy vấn, gồm hai phần: Minimum Speed và Search Criteria

- Minimum Speed: Tốc độ cực tiểu (đợn vị KB/s) mà nút có thể đáp ứng với thông điệp
- Search Criteria: tiêu chí tìm kiếm, độ dài của trường của này bị giới hạn bởi giá trị trường Payload - Length trong tiêu đề thông điệp
- Thông điệp QueryHit
- Trả lời thông điệp Query.Thông điệp này được nút có thể đáp ứng yêu cầu gửi cho nút có yêu cầu. Định danh thông điệp của Query tương ứng.

4. queryhit

- Number of Hits: số lượng các câu trả lời trong Result Set
- Port: Số hiệu cổng mà nút có thể chấp nhận các kết nối
- IP Address: địa chỉ IP của nút tương ứng
- Speed: tốc độ (KB/s) của nút
- Result Set: tập hợp các kết quả thoả mãn các câu truy vấn. Tập hợp này gồm các bản ghi liên tục nhau, mỗi bản ghi gồm tên file, kích thước file và đường dẫn đến file
- Servent Identifier: là chuỗi 16-byte xác định nút duy nhất trên mạng.
5. Push(0x40)


- Thông điệp Push được sử dụng bởi nút yêu cầu đề nghị nút có dữ liệu nhưng ở phía sau firewall khởi tạo kết nối trước.

- Servent Identifier: chuỗi 16-byte xác định nút được đề nghị chuyển file có đường dẫn đặt ở File_Index. Định danh này phải giống với định danh trong thông điệp QueryHit tương ứng
- File_Index: xác định file được đề nghị gửi
- Port: Số hiệu cổng mà nút có thể chấp nhận các kết nối
- IP Address: địa chỉ IP của nút tương ứng