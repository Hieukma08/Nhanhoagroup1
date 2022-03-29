# Tìm hiểu chung 
# Tổng quan về ngôn ngữ Bash Shell 
1. Khái niệm 
- Bash là một Unix shell và là nghôn ngữ dòng lệnh được viêt bởi Brain Fox cho sự án DNU nhưu một phần mềm thay thế miễn phó cho Boume shell . Được phát hành năm đầu tiền vào năm 1989 nó đã được phần phối rộng rãi như Login shell mặc định cho hầu hết các bản phối Linux và MAcOS .
  - Thể loại : Unix shell , ngôn ngữ dòng lệnh 
  - Hệ điều hành :Tương tự Unix , MacOS
  - Reponsitory : git.savannah.gnu.org/cgit/hash.git
  - Nền tảng : GNU 
- Lịch sử : Brain Fox đã bắt đầu lập trình Bash từ ngày 10/1/1988 sau khi Richard Stallman trở nên không hài lòng với sự tiến bộ của nhà phát triển trước đó . 
- Stallman và Free Software Foundation (FSF) xem một shell miễn phí có thể chạy các shell script hiện có nên mang tính chiến lược đối với một hệ thống hoàn toàn tự do được xây dựng từ mã BSD và GNU, đây là một trong số ít các dự án mà họ tự tài trợ, với Fox đảm nhận công việc của một nhân viên của FSF.[6][21] Fox phát hành bản beta của Bash, phiên bản.99 ngày 8/6/1989[8] và vẫn là người duy trì chính cho đến khoảng giữa năm 1992[22] and mid-1994,[23] khi ông ấy bị sa thải khỏi FSF[24] và trách nhiệm của ông đã được chuyển sang một người đóng góp sớm khác, Chet Ramey.[25][26][27]

- Từ đó, Bash trở thành shell phổ biến nhất trong cộng đồng Linux, trở thành shell tương tác mặc định trên các bản phân phối khác nhau của hệ đièu hành này (mặc dù Almquist shell có thể là scripting shell mặc định) và trên macOS của Apple.[28][29][30] Bash cũng được port đến Microsoft Windows được phân phối cùng Cygwin và MinGW, tới DOS bởi dự án DJGPP, đến Novell NetWare và tới Android thông qua các ứng dụng mô phỏng thiết bị đầu cuối khác nhau.

- Tháng 9/2014, Stéphane Chazelas, một chuyên gia về Unix/Linux,[31] phát hiện một lỗi bảo mật trong chương trình. Lỗi này, lần đầu tiên được tiết lộ vào ngày 24 tháng 9, được đặt tên là Shellshock và gán các số CVE-2014-6271, CVE-2014-6277[32] và CVE-2014-7169. Lỗi này được coi là nghiêm trọng, vì các tập lệnh CGI sử dụng Bash có thể dễ bị tấn công, cho phép thực thi mã tùy ý. Lỗi này có liên quan đến cách Bash định nghĩa hàm cho các lớp con thông qua các biến môi trường.[33]