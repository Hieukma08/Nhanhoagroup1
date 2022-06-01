# Tìm hiểu chung về Load Balancing 
# Định nghĩa :
- Load Balanceing ( cân bằng tải ) được định nghĩa là phân phối lưu lượng truy cập mạng hoặc ứng dụng một cách có hiệu quả trên nhiều server trong 1 cụm server farm .
- Load balancing được phân phối đồng đều tài nguyên trên nhiều máy chủ . kĩ thuật này giúp ghiamr thời gian phản hồi cũng như giúp tăng tốc  độ truy xuất dữ liệu cho mỗi khách hàng . Bằng cách áp dụng giải pháp này , đem đến việc cân bằng lưu lượng truy cập được chia đều đến các server hoặc khi các server bị gặp sự cố , server còn lại sẽ ngya lập tức là phương án dự phòng . Tránh làm gián đoạn truy cập và hoạt động của doanh nghiệp . 

<img src="/Load Balancer/image/1.png">

## Load Balancer hoạt động như thế nào . 
- một load balancer sẽ thực hiện các chức năng chính sau đây:
- Phân phối lưu lượng đến các server khác nhau trong nhóm tài nguyên để đảm bảo rằng không có server nào bị quá tải. 
- Giảm thiểu thời gian phản hồi của server và tối đa hóa throughput. 
- Cung cấp hiệu suất và bảo mật cần thiết để duy trì các môi trường CNTT, cũng như các quy trình công việc phức tạp diễn ra trong chúng. 
- Khả năng mở rộng nhất để xử lý vô số yêu cầu từ quy trình làm việc đa ứng dụng, đa thiết bị hiện đại. 
- Cho phép truy cập liền mạch vào nhiều ứng dụng, tệp và máy tính để bản khác nhau trong không gian làm việc số ngày nay.

<img src="/Load Balancer/image/2.png">

## Một số loại load Balancer .

- L4 : Cân bằng tải Layer 4 (L4) hoạt động ở cấp độ vận chuyển. Điều đó có nghĩa là chúng có thể đưa ra các quyết định định tuyến dựa trên các cổng TCP hoặc UDP mà các gói sử dụng cùng với địa chỉ IP nguồn và đích của chúng. L4 load balancers thực hiện Network Address Translation nhưng không kiểm tra nội dung thực tế từng gói. 

- L7: Cân bằng tải Layer 7 (L7) hoạt động ở cấp ứng dụng, cao nhất trong mô hình OSI. Chúng có thể đánh giá phạm vi dữ liệu rộng hơn so với các đối tác L4, bao gồm các tiêu đề HTTP và ID phiên SSL, khi quyết định cách phân phối các yêu cầu trên toàn bộ cụm máy chủ. Load balancing chuyên sâu hơn về mặt tính toán tại L7 hơn so với L4 và nó cũng có thể hoạt động hiệu quả hơn ở L7, do cấu hình được thêm vào để hiểu và xử lý các yêu cầu của máy khách đến máy chủ

- GSLB: Ngoài load balancing L4 và L7 cơ bản, Global server load balancing (cân bằng tải máy chủ toàn cầu – GSLB) có thể mở rộng khả năng của một trong hai loại trên nhiều trung tâm dữ liệu để có thể phân phối lưu lượng lớn một cách hiệu quả.
