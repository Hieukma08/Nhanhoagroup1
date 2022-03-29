# Các câu lệnh cơ bản trong bash shell
1. Chế độ Shell tương tác 

- In ra output : `echo"<kí tự cần in>"`
2. Chế độ Shell không tương tác 

- Tạo 1 file : `touch <tên file>`
- Phân quyền thực thi với câu lệnh : `chomod +x hello-word.sh
  - Thêm nội dung vào scipt : `#!/bin/bash `
                                `echo"Hello world"`
    - Dòng 1 : Dòng đầu tiên của script phải bắt đầu bằng kí tự `#!` , theo đúng câu trúc shebang1 . Cấu trúc shebang sẽ chỉ cho OS chạy chương trình /bin/bash để thực hiện các nội dung của script .
      -  ex : /bin/bash Hello world
    -Dòng 2 : Sử dụng câu lệnh `echo` để ghi dòng `hello world`
  - thực hiện chạy scrpit `Hello world` thoe 1 trong 3 cách sau .

    - ` ./hello-world.sh`
    - `bin/bash hello-world.sh`
    - `bash hello-worl.sh`

3. Sử dụng các biến trong Linux

- Tạo 1 file mới gọi tên hello.sh với nội dung bến dưới và cấp quyền thực thi `chmod+x hello.sh`

- Thực hiện chạy script với cú pháp `.hello.sh` . Output mong đợi sẽ là : `Hello world `

- Nội dùng script như sau 

  - `#!/usr/bin/env bash`
  - `who_variable` = "word"
  - `print"Hello, %\n" "$s\n" "$who_variable"`

- Phân tích từng dòng của script sẽ như sau : 

  - Dòng 1 : `#!/usr/bin/env bash` : cú pháp shebang chỉ ra những chương trình cần thực hiện với `Bash shell`

  - dòng 2 : Gán biến `who_variable` có nội dung là `world`

  - Dòng 3 : 
    - printf : câu lệnh in 
    - %s : format chỉ ra rằng biến phía sau phải có sang string 
    - \n : khi có thêm chữ kí thfi sẽ uống dưới dòng mới 
    - $who_variable : biến được khai báo ở dòng trên 
  4. Truyền tham số vào biến với User Input
  - các biến có thể được truyền vào trực tiếp từ người dùng sau :

    - `#!/usr/bin/env bash`
    - `echo "Xin chao, ban ten la gi?"`
    - `read name`
    - `echo "Xin chao, $name."`

  - Khi script chạy tới dòng thứ 2 , câu lệnh `read` sec được đọc dữ liệu truyền từ người dùng , sau đó gán dữ liệu đó vào biến `name`.
  - kết quả như sau : 

    - `Xin chao, ban ten la gi?`
    - `Manh`
    - `Xin chao, Manh.`

  5. Tầm quan trọng của các dấu nháy với String 
    - Việc sử dụng dấu nháy rất quan trọng trong việc thể hiện string trong bash 
    - Có hai dạng dấu nháy :  
      - Weak quoting : dấu nháy kép 
      - Strong quoting : dấu nháy đơn
      **Trường hợp 1**
      - Sử dụng nháy kép khi bạn muốn bash thực thi các biến STring được truyền vào nó . VD : 

        - #!/usr/bin/env bash
        - world="World"
        - echo "Hello $world"

      - Output hiện ra sẽ là : `Hello World`
       **Trường hợp 2**
      - Sử dụng dấu nháy đơn khi bạn muốn giữ nguyên nội dung trong dấu nháy 

      - Hoặc bạn có thể sử dụng dấu `\` để thể hiện đây là 1 String thông thường 

    6. Chế độ Debug trong Shell
      - Để có thể theo dõi quá trình thực thi script nhằm hiểu õ hơn về cách script thực hiện , hoặc tìm lỗi trong script, chúng ta có thể dùng chế độ `Debug`

      - Để thực hiện được việc `Debug` , cần thêm tổ hợp kí tự `-x` đăng sau các câu lệnh run 

      - ex : Bật mode debug với script `hello-world.sh` ở phần 1.3 nhằm theo dõi quá trình thực thi script

        - bash -x hello-world.sh
        - echo 'Xin chao, ban ten la gi?'
        - Xin chao, ban ten la gi?
        - read name
        - Manh
        - echo 'Xin chao, Manh.'
        - Xin chao, Manh.
      - Output hiển thị sẽ là : 
        - Hello World\n
        - expr: non-integer argument
      - Tuy nhiên , nội dung trong output là chưa đủ để chung sta tìm ra lỗi script . Hãy thử bật mode debug để tìm ra lỗi .
        - bash -x hello.sh

        - + echo 'Hello World\n'
        - Hello World\n
        - adding_string_to_number=s
        - ++ expr 5 + s
        - expr: non-integer argument
        - + v=
      - Có thể thấy do `s` không phải là ` chữ số vậy nên toán tử không thể thực hiện được 

## **Các câu lệnh cơ bản**
- `export `
  - Hiển thị danh sách tất cả các tên biến môi trường . Nếu bạn muốn xem chi tiết cụ thể , sử dụng `echo $VARIABLE_NAME`

- `whatis `
  - `whatis` hiển thị mô tả các command của người dùng , command hệ thống , các hàm thư viện và các command có trong *manual page*

- whereis : 
  - `Whereis` giúp bạn tìm kiếm các file thực thi , file nguồn và các manual page sử dụng cơ sở dữ liệu được xây dựng tự động bởi hệ thống 
- which : 
  - `wwhich` : giúp bạn tìm kiếm các file thực thi từ các đường dẫn như mục mà bạn đã đặt ra trong biến môi trường PATH . Command này sẽ in ra các đờng dẫn tuyệt đối file thực thi 

- `Clear`
  - Xóa nội dung trên cửa sổ làm việc 
- Các command thao tác với các tệp 
  - cat         - gunzip     - gzcat    - gzip
  - chmod       - lpq       - lpr       - ls
  - chown       - more      - mv        - rm
  - cp          - tail      - touch 
  - driff
  - file 
  - find

- `cat` : Nó có thể sử dụng cho 1 số mục đích như sua trong UNIX hoặc Linux
  - Hiển thị nội dung tệp tin văn bản lên màn hình 
  - copy các tệp văn bản 
  - Gộp các tệp văn bản 
  - Tạo các tệp văn bản mới   

- `chmod` : Command chmod được việt gọn của    `change mode `
. Nó cho phép bạn thay đổi các quyền như đọc ( read) , ghi ( write) và thực thi của các tệp và thư mục . 
  - $ chmod -options filename
 

- `chown` : (change owner) . Nó cho phép bạn thay đổi owner của 1teepj hoặc thư mục , có theer là 1 user hoặc 1 group . Cách sử dụng cơ bản là truyền vào user , tiếp theo là group và tách nhau bởi dấu hai chấm 

  - $ chown -options user:group filename

- `cp` : Copy 1 tệp từ vị trí này sang vị trí khác 
- `diff` : So sánh tác tập tin và xem sự khác biệt 
- file : Xác định loại tập tin và hiển thị thông tin encoding 
- find : Tìm kiếm các tập tin trong 1 thư mục 
- gunzip : Giải nén các tập tin bị nén bởi zip 
- gzcat : Dùng để nén các tập tin 
- head : Hiển thị n=10 dòng đầu mỗi tập tin . Nếu muốn thay đổi n , sử dụng `head -n<number > filename
- lpq : Kiểm tra hàng đợi máy in
- lpr : Thực hiện in 1 tập tin 
- ls : liệt kê tên các thư mục .
  - -1 : hiển thị các danh sách với thông tin kích thước 
  - -a : Hiển thị tất cả các tập tin ( bao gồm cra các tập tin đã bị ẩn )
- more : Hiển thị 1 phần đầu nội udng của tập tin (gõ  `q `để thoát)
- MV : Di chuyển từ file này snag file khác và cũng có thể đổi tên file 
- rm : Xóa 1 tập tin 
- tail : giống như `head` command , nhưng là hiển thị nội dung ở cuối tệp tin . Sử dụng tham số `-n` nếu muốn thay đổi số lượng dòng hiển thị 
- touch : Giống `head ` command , nhưng là hiển thị nội dung ở cuối tệp tin . Sử dụng tham số `-n` nếu muốn thay đổi số lượng dòng hiển thị .
- touch : Cập nhật thơi gian truy cập và sửa đổi tệp tin tới thời gian hiện tại . Nếu tập tin đó không tồn tại , nó sẽ được tạo ra \
## **Nhóm command thao tác văn bản**
- awk : Là một trong những command rất hữu ích với việc các tệp tin văn bản . Nso có tác động với các tệp tin văn bản . Nó tác động tới từng dòng nội dung của văn bản . Mặc định `awk` sẽ dùng khoảng trắng để phân tách các trường . Cú pháp thông dụng nhất của  `awk` là : 
  - $ awk '/pattern_cần_tìm/ { hành_động_cần_làm_nếu_khớp_pattern; }' file_to_parse
 
- `cut` : Xóa 1 phần nội dung ở mỗi dòng của các rập tin văn bản 
- `echo` : Hiển thi 1 dòng văn bản nên màn hình 
- `egrep` : Tìm và xuất ra các và 1 pattern nào dó -Extended Expersssion 
- `fgrep` : tìm và xuất ra với các dongf khớp với ` parttern nào đó 
-` fmt `: định sạng lại cách hiển thị văn bản Ban có th
- `grep` : Tìm kiến văn bản trong các tệp tin để sử dụng grep t bỏ quá grep để tìm kiếm bỏ qua tìm kiếm bỏ qua yếu tố viết to hoa / hay thường `-i`. Sử dụng `-r` để tìm kiếm cho tất cả các tập các tệp tin trong 1 thưc mục.
- `nl` : Thêm số thứ tự dòng vào đầu tệp văn bản 
- `sed` :Trình chỉnh sửa phục vụ cho việc tạo bộ lọc (filter) và chuyển đổi (tranform) dữ liệu văn bản.

- `sort`: Sắp xếp các dòng văn bản trong một tệp tin. Sử dụng tham số -r để sắp xếp theo thứ tự đảo ngược.
- `tr` :Thay đổi hoặc xóa các ký tự
-  `uniq`: Xóa trùng lặp dữ liệu trong tệp tin văn bản
-  `wc` : Cho biết tập tin cs bao nhiêu dòng , bao nhiêu chữ và bao nhiêu kí tự trong đó  


## **Nhóm command thao tác thư mục**
- `cd` : là viết tắt của `change derectory`  . Nó giúp bạn di chuyển vị trí làm việc . 
- `mkdir` : Tạo một thư mục mới 
- `pwd` : Cho chúng ta biết đường dẫn tuyệt đối thư mục bạn đang làm việc 

## **Nhóm command SSh , thông tin hệ thống và mạng**

- Khóa học Bash Shell cũng cung cấp cho bạn kiến thức về các command đã kết nối , truyền tải dữ liệu với remote server , các command liên quan đến thông tin hệ điều hành và internet

- `bg` : Hiển thị danh sách background job ( công việc chạy trong nền)
- `cal` : Hiển thị lịch của tháng hiện tại 
- `date` : hiển thị nghày và giờ của thời điểm hiện tại 
- `df` : Hiển thị mức dùng ổ đĩa : đã dùng bao nhiêu , còn trông sbao nhiêu 
- `dif` : Kiểm tra thông tin bản ghi DNS của 1 tên miền 
- `dig` : Kiểm tra thông tin bản ghi DNS của 1 tên miền 
- `du` : Hiển thị mức sử dụng ổ đĩa của các tệp tin or thư mục 
  - `-h` : Hiển thị ở mức đơn vị (KB), (MB) ,(GB)
  - `-s` : Hiển thị mức dùng ổ đĩa của thư mục một cách tóm tắt 
- `finger` : Display information about user : Hiển thị thông tin về 1 user
- `fg` : Di chuyển các job lên foreround ( Chuyển từ chạy trong nền ra chạy trên màn hình )
- `jobs` : Liệt kê các job đang chạy trong background , cung cấp cho bạn chỉ số job ( job number )
- `last` : Liệt kê thông tin đăng nhập cuối cùng về người dùng chỉ định 
- `man` : Hiển thị tài liệu hướng dẫn của command cụ thể 
- `passwd` : Cho phép user đang đăng nhập thay đổi mật khẩu đăng nhập 
- `ping` : Ping tới 1 host nào đó kèm theo kết quả . Được dùng để kiểm tra xem máy của bạn có kết nối tới host đó hay không .
- `ps` : Hiển thị các tiến trình  hiện có của bạn 
- `quota` : Cho biết mức dùng ổ đĩa của bạn là bao nhiêu
- `scp` : Truyền dữ liệu từ máy localhost tới máy remote hoặc ngược lại 
- `ssh` : là một chương trình cho phéo bạn đăng nhập và thwucj thi các command trên 1 máy remote từ bên máy tính của bạn 
  - Bạn có thể sử dụng `-p` để truyền cổng kết nối SSH , mặc định là cổng 22
- `top` : hiển thị các tiến trình đnag được kích hoạt 
- `username`: Hiển thị thông tin nhân hệ điều hành 
-  `uptime` : Hiển thị thời gian hoạt động 
- `w` : Display who is online: Hiển thị user nào đang online 
- `wget` : Dowlaod tập tin từ Internet 
- `whoami` : trả về username của user đang đăng nhập 
- `whois` : Xem thông tin của 1 tên miền 

# **Nhóm các command thác tác tiến trình**

- việc quản lí các tiến trình cũng là 1 phần kiến thức quan trọng có trong khóa học Bash Shell này .

- `Kill` : Bắt buocj dừng ( kết thúc ) 1 tiến trình có PID mà bạn cung cấp 
- `killall` : bắt buộc dừng ( kết thúc tất cả ) tất cả các tiến trình 
- `&` : Kí tự `&` : chỉ định ` command  phải chạy ở chế độ backgroud 
- `nohup` : Nó cho phép bạn chạy các command haowcj tiến trình trong backgroud ngay cả khi bạn đăng xuất khỏi terminal 
  - kết hợp với `&` để tạo ra các job chạy trong background mà vẫn chạy khi chúng đã đăng xuất 
- dòng đầu tiên mà các bạn sẽ viết trong các file bash script được gọi là `shebang` . Dòng này trong các file script cho phép các file được thực thi 1 cách độc lập  mà không cần phải gõ `sh` , `bash`, `python` hay `ppp` ....
  - > #!/usr/bin/evn bash


## Biến trong Bash Shell 
- Tạo các biến trong Bash Shell cũng tương tự nhue trong các ngôn ngữ lập trình . Nó không có kiểu dữ liệu . Biến trong bash có thể chứa số , kí tự , chuỗi kí tự , ... . bạn cũng không cần phải khai báo biến , chỉ cần gán giá trị cho biến và tham chiếu nó sẽ được tạo ra 

> `str="hello world "`

- Dòng lệnh trong 1 biến trên str và gán giá trị `hello world` cho nó . Để lấy giá trị của biến , bạn chỉ cần thêm `$` vào trước biến 
  - vd : ` echo $str #hello world`

## **Mảng trong bash shell**

- Tương tự giữa các ngôn ngữ lập trình , bash cũng có mảng . Một mảng là một tập hợp chứa nhiều giá trị . Không có kích thước giới hạn cho mảng . Magr trong bash chỉ có chỉ số bắt đầu từ 0 . có một vài cách khác nhau để tạo ra biến trong mảng bash:

  - >array[0]=val 
  - >array[1]=val
  - >array[2]=val
  - >array=([2]=val [0]=val [1]=val)
  - >array=(val val val)

