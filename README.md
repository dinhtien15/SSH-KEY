# SSH-KEY
Hướng dẫn cấu hình SSH Key trên Ubuntu 20.04

Bước 1: Tạo SSH Key trên máy của bạn
```
ssh-keygen 
```

Bước 2: Copy SSH Public Key cho Server của bạn
```
cat ~/.ssh/id_rsa.pub
```

Bây giờ, bạn sẽ cần copy toàn bộ nội dung của id_rsa.pub Vào file authorized_keys.
```
~/.ssh/authorized_keys
```

Bước 3: Tắt xác thực bằng mật khẩu trên Server
```
sudo nano /etc/ssh/sshd_config
```
Tìm tới mục PasswordAuthentication và để giá trị của nó thành no.
Lưu lại và khởi động lại service:
```
sudo systemctl restart ssh
```
