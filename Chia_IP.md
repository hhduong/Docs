#Cách chia IP

### 1. Phân lớp địa chỉ IP
  - Có 5 lớp: A, B, C, D ,E. Hai lớp D, E bỏ qua
![Imgur](https://i.imgur.com/WIYSZQm.jpg")
  - Subnet Mask (SM)
![Imgur](https://i.imgur.com/yQsXXdy.jpg")
Chú ý: lớp D, E không dùng subnet mask

### 2. Hướng dẫn chia IP
   * Quy tắc:
-  2^n > = số đường mạng
- Trong đó n là số bit mượn để chia IP.
- Subnet mask mới = subnet mask mặc định của lớp + số bit mượn.
- Bước nhảy = 2^m.
- Trong đó m là số bit còn lại sau khi mượn. m = 32 - Số bit host mới.

VD: Chia IP192.168.1.0 cho 6 mạng
Ta có: 2^n>=6 nên n=3

=> SM mới: 255.255.255.128 ó /27
IP đầu: 192.168.1.0/27
Bước nhảy: m=32-27=5 => 2^5=32
Các IP sau lần lượt:

172.168.1.32/27

172.168.1.64/27

172.168.1.96/27

172.168.1.128/27

172.168.1.160/27



