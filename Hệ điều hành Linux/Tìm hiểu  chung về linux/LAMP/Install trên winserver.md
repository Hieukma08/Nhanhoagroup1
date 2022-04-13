# cài đặt website bằng iiS trên winserver 2012
## Các bước cài đặt IIS trên winserver 2012
**Cài đặt IIS**
1. Ở Server MAanager 
- Chon Add Role and Features rồi install 

<img src="/Hệ điều hành Linux/Tìm hiểu  chung về linux/LAMP/IIS/1.png">

- Sau khi cài đặt xong ở manager sẽ hiển thị như sau 

<img src="/Hệ điều hành Linux/Tìm hiểu  chung về linux/LAMP/IIS/2.png">

- Vào ổ C mở inetpub nên và tạo 1 trang html 

<img src="/Hệ điều hành Linux/Tìm hiểu  chung về linux/LAMP/IIS/3.png">

- Vào file hosts chỉnh sửa và thêm vào địa chỉ trang web

- Cuối cùng vào trình duyệt và nhập địa chỉ websitw vừa tạo ta được kết quả sau :

<img src="/Hệ điều hành Linux/Tìm hiểu  chung về linux/LAMP/IIS/4.png">

- Dowload PHP theo link: https://windows.php.net/download/
- Dowload Wincache theo link: https://sourceforge.net/projects/wincache/files/
- Giải nén PHP vừa tạo vào đường dẫn : C:\PHP\
- Giải nén Wincache vào đường dẫn C:\PHP\ext\