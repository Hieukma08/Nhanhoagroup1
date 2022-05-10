# Tìm hiểu chung và APF và cách cài đặt 
## Giới thiệu về APF 
- APF là tên viết tắt của Advance Policy Firewall
- Đây là 1 loại tường lửa do 1 nhóm phét triển và xây dựng dựa trên các rule của iptable 
- Không giống như tường lửa CFS , APF có tính linh hoạt hơn và gần như không cần phải thực hiện các bước để có thể sử dụng ngay lập tức 
## Cài đặt APF 
- Bước 1 ; Dowload phiên bản mới nhất về mà unzip 
> wget http://www.rfxn.com/downloads/apf-current.tar.gz
> tar -xvf apf-current.tar.gz
- Vào thư mục , chạy file cài đặt 
> cd apf-1.7.6/
> sh./install.sh
- Chỉnh sửa file config: 
> nano /etc/apf/conf/apf
> DEVEL_MODE="1" -> Thư nghiệm hay chính thức chạy ? 1 có 0 không
> IFACE_IN="eth0" and IFACE_OUT="eth0" -> Tên card mạng mà bạn chạy trong máy chủ . Với máy chủ vật lí hoặc công nghệ xen thì là eth0 còn với OpenVZ thì thường là venet0
> 
