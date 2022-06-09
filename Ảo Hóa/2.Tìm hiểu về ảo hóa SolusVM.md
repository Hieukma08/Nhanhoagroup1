# Tìm hiểu chung về ảo hóa SolusVM
- Solus VM ( Solus Virtual Manager ) là một hệ thống quản lí VPS bằng WebUI hỗ trợ đầy đủ OPenVZ , Linux VZ , Xen Paravirtualization , Xen HVM . Tựu chung đây là phần mềm quản lí ảo hóa như Virtulation , SolusVM cho phép bạn và khách hàng của bạn quản lí cùng 1 cụng VPS một cách an toàn và dễ dàng . 


- Yêu cầu hệ thống 
  - SolusVM master phải được cài đặt trên 1 máy chủ nguyên sạch : máy chủ mới được cài đặt và được cập nhật lên phiên bản mới nhất với lệnh `yum update`
  - SolusVM Master chỉ hỗ trợ ảo hóa OPenVZ . Còn Xen và KVM chạy trên đó và có thể nhập chúng vào hệ thống SolusVM  Slave.
  - không được cài SolusVm lên phần mềm tương tự như Vitualizor . \
  - Nên sử dụng hệ điều hành dựa trên RHEL 7 
  