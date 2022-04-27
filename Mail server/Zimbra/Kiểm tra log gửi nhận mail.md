# Kiểm tra log gửi nhận mail 
- Việc kiểm tra log gửi nhận của email server zimbra là cần thiết , giúp xác định được 1 email đã được gửi /nhận thành công hay chưa và nếu chưa thì bị dừng lại ở bước nào và báo lỗi ra sao 
  - Đường dẫn file Log `var/log/maillog`
  - Chu trình gửi mail -> Connect tới email server -> MTA kiểm tra địa chỉ người nhận -> Kiểm tra các rule filter đánh giá spam , virus -> Xếp vào quêu -> Gửi thư -> Xóa khỏi quêu -> Thông báo tới `Message accepted for  delivery `

  - Chu trình nhận: Chấp nhận kết nối từ mail server gửi tới -> Kiểm tra các rule filter , đánh giá spam, virus-> xếp vào queue -> Nhận thư và xóa khỏi queue -> Thông báo thư nhận `250 2.1.5 Delivery Ok`
  