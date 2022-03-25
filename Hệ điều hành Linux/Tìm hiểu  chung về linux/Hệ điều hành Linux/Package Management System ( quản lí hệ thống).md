## Package Mangement System ( Hệ thống quản lí package)
- Các phần cốt lõi của các bản phân phối Linux và hầu hết các phần mềm của nó có được cài thông  qua `packet management System` . Mỗi gói chứa các tệp và các hướng dẫn khác cần thiết để làm cho một thành phần mềm hoạt động trên hệ thống . Các gói phụ thuộc lẫn nhau .
- Có hai lựa chọn quản lí gói : `dpkg` và `rpm` . Hai hệ thống không tương thích nhưng cung cấp cho các tính năng giống nhau ở mức độ rộng rãi .


| High Level Tool | Low Level tool | Family |
| :---------------| :---------     |:-------|
|     zyper       | rpm            | SUSE   |
| yum             | rmp            | Red Hat|

- Cả hai hệ thống quản lí đều cung cấp gói cung cấp 2 mức công cụ : 
  - công cụ cấp thấp , sẽ chăm sóc các chi tiết của giải nén gói cá nhân , chạy các kịch bản , nhận được các phần mềm được cài đặt một cách chính xác .
  - Một công cụ cấp cao hoạt động với các nhóm , tải gói từ nhà cung cấp và tìm ra các phụ thuộc .
- Cài đặt một gói duy nhất có thể dẫn đến hàng chục thậm chí hàng trăm gói phụ thuộc được cài đặt . 



|       Operation          |      RPM        |     DEbian         |
|Cài đặt packet            | rpm -i foo.rpm  | dpkg --install foo.|
|Cài đặt 1 packet từ repository |   yum install foo  | apt -get install foo | 



