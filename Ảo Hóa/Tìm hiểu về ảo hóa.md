# Công nghệ ảo hóa
## Giới thiệu về ảo hóa
- Ngày nay, việc quản lí và sử dụng hạ tầng CNTT là điều rất cần thiết với bất kỳ một doanh nghiệp nào. Tuy nhiên vẫn còn những hạn chế trong việc quản lý và sử dụng tài nguyên theo phương pháp truyền thống:
- Mỗi máy chủ vật lý chỉ cài đặt tương ứng 1 hệ điều hành, từ đó chỉ thiết lập được 1 môi trường hoạt động, dẫn đến thiếu linh hoạt về các loại ứng dụng có thể cài đặt phục vụ cho mục đích doanh nghiệp
- Việc đầu từ nhiều máy chủ nhưng không sử dụng hết năng lực của máy chủ dẫn đến phí phạm tài nguyên và quản lý tài nguyên trở nên khó khăn
Các máy chủ vật lý được cài đặt trực tiếp hệ điều hành và ứng dụng gặp khó khăn trong việc sao lưu và phục hồi (backup và restore), một số máy chủ vật lý đang hoạt động có những cơ chế đặc thù riêng và gần như rất khó hoặc “không thể” thực hiện sao lưu và phục hồi
- Thời gian downtime của máy chủ vật lý thường rất lâu và dễ gặp trục trặc trong quá trình khởi động lại
Khó khăn trong việc quản trị và giám sát tập trung khi số lượng máy chủ vật lý tăng lên
- Vì vậy ảo hóa được đưa ra nhằm tối ưu hóa việc sử dụng và khai thác tài nguyên vật lý

- Công nghệ ảo hóa là một công nghệ được ra đời nhằm khai thác triệt để khả năng làm việc của một máy chủ vật lý. Ảo hóa cho phép vận hành nhiều máy chủ ảo trên cùng một máy chủ vật lý, dùng chung các tài nguyên của một máy chủ vật lý như CPU, Ram, ổ cứng... và các tài nguyên khác. Các máy ảo khác nhau có thể vận hành hệ điều hành và ứng dụng trên cùng một máy chủ vật lý
- Công nghệ ảo hóa cho phép hợp nhất và chạy nhiều khối lượng công việc như các máy ảo trên một máy tính duy nhất. Một máy ảo là một máy tính được tạo ra bởi phần mềm, giống như một máy tính vật lý, chạy một hệ điều hành và các ứng dụng. Mỗi máy ảo có phần cứng ảo riêng của nó, bao gồm một CPU, bộ nhớ, đĩa cứng và card mạng ảo, giống như phần cứng cho hệ điều hành và ứng dụng
## Chức năng của ảo hóa
- Phân chia: Với công nghệ ảo hóa, chúng ta có thể chạy nhiều máy ảo trên một máy thật với nhiều hệ điều hành khác nhau, nhờ thế mà ta cũng có thể tách từng dịch vụ ra để cài trên từng máy ảo
- Cô lập: Khi mỗi dịch vụ quan trọng được cài trên một máy ảo khác nhau thì nếu có sự cố, các dịch vụ khác cũng không bị ảnh hưởng gì
- Đóng gói: Với công nghệ ảo hóa, các máy ảo được đóng gói thành các file riêng biệt, nhờ vậy mà nó có thể dễ dàng được sao chép để backup và di chuyển sang hệ thống khác để chạy
## Lợi ích của ảo hóa
- Tiết kiệm chi phí trong khi đó lại tăng hiệu quả, hiệu năng và tính linh động cho hạ tầng hiện hữu
- Giảm số lượng máy chủ vật lý, giảm lượng điện năng tiêu thụ, tiết kiệm được chi phí cho việc bảo trì phần cứng, nâng cao hiệu quả công việc
- Dễ ràng mở rộng khi có nhu cầu
- Khai thác triệt để các tài nguyên của phần cứng vật lý bằng cách chạy nhiều hệ điều hành trên mạng một chủ vật lý
- Tăng tính linh hoạt của hệ thống, cho phép di chuyển máy chủ mà không gây ảnh hưởng đến các ứng dụng và dịch vụ đang chạy trên các máy chủ. Cung cấp các ứng dụng và tài nguyên nhanh hơn
##  Phân loại
- Trong ảo hóa, người ta có thể ảo hóa:

  - RAM virtualization
  - CPU virtualization
  - Network virtualization
  - Device I/O virtualization
- Ảo hóa có 2 loại chính đó là:

- Dedicated virtualization (Bare-Metal Hypervisor): Hypervisor tương tác trực tiếp với phần cứng của máy chủ để quản lý, phân phối và cấp phát tài nguyên. Loại ảo hóa này bao gồm các giải pháp như VMware ESXi, Microsoft Hyper-V, Xen Server, KVM
- Hosted Architecture: Đây là loại ảo hóa Hypervisor giao tiếp với phần cứng thông qua hệ điều hành. Hypervisor lúc này được xem như một ứng dụng của hệ điều hành và các phương thức quản lý, cấp phát tài nguyên đều phải thông qua hệ điều hành. Loại ảo hóa này bao gồm các giải pháp như: VMware WorkStation, Oracle VirtualBox, Microsoft Virtual PC...
- Ở loại thứ 1, Hypervisor tương tác trược tiếp với phần cứng nên việc quản lý và phân phối tài nguyên được tối ưu và hiệu quả hơn so với loại 2, vì vậy khi triển khai trong thực tế, ảo hóa loại 1 (Bare-Metal Hypervisor) được sử dụng trong các trường hợp thử nghiệm, hoặc mục đích học tập