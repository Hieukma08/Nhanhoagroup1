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
    - ./hello-world.sh
    - bin/bash hello-world.sh
    - bash hello-worl.sh

3. Sử dụng các biến trong Linux

- Tạo 1 file mới gọi tên hello.sh với nội dung bến dưới và cấp quyền thực thi `chmod+x hello.sh`

- Thực hiện chạy script với cú pháp `.hello.sh` . Output mong đợi sẽ là : `Hello world `

- Nội dùng script như sau 

  - `#!/usr/bin/env bash`
  - `who_variable` = "word"
  - `print"Hello, %\n" "$s\n" "$who_variable"
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
    - #!/usr/bin/env bash
    - echo "Xin chao, ban ten la gi?"
    - read name
    - echo "Xin chao, $name."
  - Khi script chạy tới dòng thứ 2 , câu lệnh `read` sec được đọc dữ liệu truyền từ người dùng , sau đó gán dữ liệu đó vào biến `name`.
  - kết quả như sau : 
    - Xin chao, ban ten la gi?
    - Manh
    - Xin chao, Manh.
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

        echo 'Xin chao, ban ten la gi?'
        Xin chao, ban ten la gi?
        read name
        Manh
        echo 'Xin chao, Manh.'
        Xin chao, Manh.



