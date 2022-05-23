# I . Tìm hiểu về giao thức ARP
## 1. Giao thức ARP là gì ? 
1. Khái niệm 
- ARP ( Address Resolution Protocol ) là giao thức mạng dùng để tìm ra địa chỉ phần cứng ( địa chỉ MAC ) của 1 thiết bị từ 1 địa chỉ IP nguồn .
-  Nó được sử dụng khi một thiết bị gioa tiếp với các thiết bị khác dựa trên nền tảng Local Network .
2. Lịch sử và mục đích của ARP 
- ARP hình thành và phát triển những năm 1980
- Mục đích giúp một quản lí có thể quản lí các kết nối độc lập với những thiết bị vật lí cụ thể được gắn vào từng mạng . 
- Điều này cho phép giao thức Internet vận hành hiệu quả hơn so với việc nó phải tự quản lý địa chỉ của các thiết bị phần cứng và mạng vật lý.
3. Cơ chế hoạt động của ARP
- Quá trình hoạt động của ARP được bắt đầu khi một thiết bị nguồn trong một mạng IP có nhu cầu thực hiện gửi một gói tin IP. Trước hết thiết bị đó phải xác định được xem địa chỉ IP đích của gói tin có phải đang nằm cùng trong mạng nội bộ của mình hay không. Nếu đúng vậy thì thiết bị sẽ thực hiện gửi trực tiếp gói tin đến thiết bị đích. Nếu địa chỉ IP đích đang  nằm trên mạng khác, thì thiết bị sẽ gửi gói tin đến một trong các router nằm cùng ở trên mạng nội bộ để router này làm nhiệm vụ forward gói tin.

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức ARP/image/1.jpg">

- ARP về cơ bản là một quá trình có 2 chiều request/response giữa các thiết bị trong cùng mạng nội bộ. Thiết bị nguồn request bằng cách gửi một bản tin local broadcast  lên trên toàn mạng. Thiết bị đích response bằng một bản tin unicast để trả lại cho thiết bị nguồn.
4. Các loại bản tin ARP
- Có hai dạng bản tin cơ bản trong ARP :
  - Từ nguồn tới đích 
  - Từ đích tới nguồn 

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức ARP/image/2.jpg">

- Request: Khi hệ thống khởi tạo quá trình, gói tin được gửi từ máy nguồn tới thiết bị đích

- Reply: Khi quá trình đáp trả gói tin ARP request, được gửi từ thiết bị đích đến máy nguồn
**Có 4 loại địa chỉ nằm trong 1 bản tin ARP đó là**
- Sender Hardware Address: Đây là địa chỉ lớp hai của thiết bị gửi bản tin 
- Sender Protocol Address : Đây là địa chỉ ba lớp ( hay còn gọi là địa chỉ logic )
của các thiết bị bản tin 
- Target Hardware Address : Địa chỉ lớp 2 ( địa chỉ phần cứng ) của các thiết bị đích của bản tin 
- Target Protocol Address : địa chỉ lớp 3 ( hay còn gọi là địac chỉ logic ) của thiết bị bản tin .

<img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức ARP/image/cacloaidiachitrongmotbantinarp.png">

6. Các bước hoạt động của ARP
 **ARP là 1 quá trình hoạt động gồm 6 bước**
 1. Source Device Checks Cache: Trong bước này, thiết bị sẽ  thực hiện kiểm tra cache (bộ đệm) của mình. Nếu đã có địa chỉ IP đích tương ứng với MAC nào đó rồi thì lập tức hệ thống chuyển sang bước 9.

  2. Source Device Generates ARP Request Message:  Hệ thống bắt đầu khởi tạo gói tin ARP Request với các trường địa chỉ như trên.

  3. Source Device Broadcasts ARP Request Message: Thiết bị nguồn truyền gói tin ARP Request trên toàn mạng

  4. Local Devices Process ARP Request Message: Các thiết bị trong mạng đều sẽ nhận được gói tin ARP Request. Gói tin được xử lý bằng cách đưa thiết bị vào trường địa chỉ Target Protocol Address. Nếu trùng với địa chỉ của mình thì tiếp tục xử lý, nếu không thì hủy gói tin

  5. Destination Device Generates ARP Reply Message: Nếu Thiết bị với IP trùng với IP trong trường Target Protocol Address sẽ thực hiện quá trình khởi tạo gói tin ARP Reply. Đồng thời thiết bị sẽ lấy địa chỉ datalink của mình để tiến hành đưa vào trường Sender Hardware Address

  6. Destination Device Updates ARP Cache: Thiết bị đích cập nhật bảng ánh xạ địa chỉ IP và MAC của thiết bị nguồn vào bảng ARP cache của mình để giảm bớt thời gian xử lý cho những lần sau.

  <img src="/Tìm hiểu về các giao thức HTTP, DNS , FTP, SSh,DHCP,ARP,SNMP,SMTP/Giao thức ARP/image/cachhoatdongcuaarp.png">

  7. Destination Device Sends ARP Reply Message: Thiết bị đích sẽ bắt đầu gửi gói tin Reply đã được khởi tạo đến thiết bị nguồn. 

  8. Source Device Processes ARP Reply Message: Thiết bị nguồn nhận được gói tin reply và tiến hành xử lý bằng cách lưu trường Sender Hardware Address trong gói reply như những địa chỉ phần cứng của thiết bị đích

  9. Source Device Updates ARP Cache: Thiết bị nguồn update vào ARP cache giá trị tương ứng giữa địa chỉ network và cả địa chỉ datalink của thiết bị đích. Do đó, những lần tiếp theo sẽ không còn cần tới request.
7. Ưu nhược điểm của giao thức ARP 
- Ưu điểm : 
- Nhược điểm 