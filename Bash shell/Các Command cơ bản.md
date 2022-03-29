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
<img src="/Bash shell/image/1.png.html">
- Thực hiện chạy script với cú pháp `.hello.sh` . Output mong đợi sẽ là : `Hello world `

