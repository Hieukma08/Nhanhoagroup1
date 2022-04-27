# Các bước thực hiện việc chặn mail cá nhân gửi mail đến server 
- Tạo file `postfix_reject_sender` theo đường dẫn 
```
/opt/zimbra/conf/posfix_reject_sender
```
- Sau đó đăng nhập vào user Zimbra để thực hiện lệnh sau 
```
su zimbra
zmprov ms mail.tnhydbg.xyz +zimbraMtaSmtpdSenderRestrictions "check_sender_access lmdb:/opt/zimbra/conf/postfix_reject_sender"
```
- Postmap với file đã tạo và khởi động lại Zimbra 

```
/opt/zimbra/common/sbin/postmap /opt/zimbra/conf/postfix_reject_sender
zmmtactl restart
```
- Đăng nhập vào uer1 để thực hiện gửi thư đến server và được kết quả 

<img src="/Mail server/Zimbra/image/10.png">