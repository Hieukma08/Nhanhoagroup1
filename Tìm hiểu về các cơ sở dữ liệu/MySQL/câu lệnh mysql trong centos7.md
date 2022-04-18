# Các câu lệnh mysql trong centos 7 
- Tạo cơ sở dữ liệu 
> CREATE DATABASE hieutn;

- Show cơ sở dữ liệu vừa tạo : 

> show databases;

- Chọn database để sử dụng

> use itfromzero;

- Tạo table

> CREATE TABLE hieutn(
    -> id Int(3),
    -> first_name Varchar (15),
    -> email Varchar (20)
    -> );
)

- Kiểm tra bảng vừa tạo 
> show table;
- Xem các cột bằng câu lệnh 

> show columns from member;

- Thêm cột vào database 

> ALTER TABLE member ADD last_name varchar (20) AFTER first-name;

- Insert các giá trị vào các trường dữ liệu 

> INSERT INTO member VALUES ('1' ,'Hieu' , 'BG' , hieutn@gmail.com' ,'VN' );

- Xóa bảng vừa member thành viên có ID =3 

> DELETE FROM member WHERE id = 3;

- Chỉnh sửa thông tin trong cột có id bằng 3

> UPDATE member SET id=3  WHERE first_name = 'itfromzero';

- Xóa cột 

> ALTER TABLE member drop country;

- Đổi tên bảng 

> RENAME TABLE member TO member_tb1;

- Liệt kê bảng 

> show table ;

- Xóa database

> drop database;
