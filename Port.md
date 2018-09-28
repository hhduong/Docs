# Port
 - Port không phải là " cổng " để "chạy ra chạy vào" mà là một số hiệu ID cho 1 application nào đó.
 - Mỗi Application chỉ có thể chạy trên một/nhiều port và mang tính độc quyền, không có Application khác được " chạy ké ".
 - Chính vì tính độc quyền nên các Application có thể modify cho phép chạy một port khác với Port default. Ví dụ IIS/Apache làm web server có thể dùng 80 là default nhưng có thể đổi thành 81 82 83 v.v... tùy ý.
 - Port cũng có phân chia làm Internal và External .
 - Số hiệu từ 1->65535. 

### Một số cổng thông dụng trong internet:.
1. Cổng 80: Khi một người sử dụng địa chỉ IP hay HostName của các bạn trong bộ duyệt, bộ duyệt sẽ quan sát địa chỉ IP trên cổng 80 theo mặc định cho những trang Web.

2. Cổng 81: Khi một người sử dụng nhập địa chỉ IP hay HostName của các bạn trong bộ duyệt, bộ duyệt sẽ quan sát địa chỉ IP trên cổng 80. Nếu Cổng thì bị tắc nghẽn, Cổng 81 được sử dụng như một Cổng xen kẽ cho một website hosting nào đó.

3. Cổng 21: Khi người nào đó thử nối tới dịch vụ FTP của các bạn, khách hàng FTP sẽ cố gắng kết nối trên Cổng 21 theo mặc định. Thì cổng 21 mở cho những khách FTP đăng nhập và nối tới server của các bạn

4. Cổng 22: Nếu bạn chạy một SSH Secure Shell, cổng này được yêu cầu cho Khách hàng SSH để nối tới người phục vụ của các bạn.

5. Cổng 23 :Nếu bạn chạy một người phục vụ Telnet, cổng này được yêu cầu cho Khách hàng Telnet để nối tới người phục vụ của các bạn. Telnet có thể được sử dụng cho những cổng khác kiểm tra những công tác dịch vụ, nhưng để sử dụng telnet cho admin và đăng nhập từ xa thì cổng 23 phải mở.

6. Cổng 25: Khi người nào đó gửi một thư từ thông báo tới server SMTP của các bạn, thư từ sẽ cố gắng để đi vào tới server của các bạn trên Cổng 25. Đây là tiêu chuẩn SMTP (thủ tục vận chuyển Thư từ Đơn giản)

7. Cổng 2525: Khi người nào đó gửi một thư từ thông báo tới server SMTP của bạn, thư từ sẽ để đi vào tới server của các bạn trên Cổng 25. Cổng 2525 xen kẽ được dùng bởi TZO cho những công tác lưu trữ và truyền lại. Đây là một cổng không tiêu chuẩn, nhưng sẻ hữu ích nếu SMTP (thủ tục vận chuyển Thư từ Đơn giản) bị tắc nghẽn

8. Cổng 110: Khi bạn chạy một máy tính, những người sử dụng sẽ vào theo đường POP3 (Nghi thức cơ quan bưu điện) hay IMAP4 (giao thức truy nhập Thông báo Internet) khôi phục thư từ của họ. POP3 là nghi thức tốt nhất để truy nhập những hòm thư

9. Cổng 119: Khi bạn chạy một server Tin tức, điển hình những khách hàng Tin tức muốn nối tới người phục vụ Tin tức của các bạn sẽ nối trên cổng 119. Cái này chuyển những nhu cầu để mở để chạy server tin tức của mình.

10. Cổng 3389: Chuyển 3389 Là Máy để bàn Từ xa được sử dụng cho Windows. Nếu bạn muốn từ xa kết nối tới máy tính của các bạn để điều khiển từ xa, việc sử dụng máy để bàn Từ xa freeXP yêu cầu cổng 3389 để mở.

11. Cổng 389 : LDAP hay giao thức truy nhập Thư mục Lightweight đang trở nên phổ biến chúng cho sự Truy nhập Thư mục, hay Tên, điện thoại Gửi những Thư mục. Chẳng hạn
LDAP: // LDAP.Bigfoot. Com là một người phục vụ thư mục LDAP.

12. Cổng 143 : IMAP4 hay giao thức truy nhập Thông báo Internet đang trở nên phổ biến hơn và được sử dụng khôi phục Thư từ Internet từ một server từ xa. từ đó tất cả các thông báo đều được cất giữ trên server, Nó dễ dàng trực tuyến, ngoại tuyến và sự sử dụng offline

13. Cổng 443 : Khi bạn chạy một người phục vụ an toàn, những Clients SSL muốn nối tới những server An toàn ,các bạn nối trên cổng 443. Những cổng này được cần để mở để chạy …..

14. Cổng 1503 & 1720 :MS NetMeeting và VOIP cho phép bạn tới host Internet hay gọi là VideoConference. NetMeeting là một sản phẩm tự do mà có thể là được tìm thấy trên Website Microsoft Tại địa chỉ http: // www.microsoft.com /

15. Cổng 5590: Khi bạn chạy một Server VNC để từ xa kiểm soát PC của các bạn, nó sử dụng cổng 5900. VNC sẻ hữu ích nếu bạn muốn từ xa kiểm soát server của các bạn../

16. Cổng 5631: Khi một người phục vụ PCAnywhere được thiết lập nhận được những yêu cầu từ xa, nó tiếp tục nghe TCP cổng 5631. Hostand được cho phép bạn để chạy một PCAnywhere, PCAnywhere này sử dụng Internet để nối với nhau và từ xa kiểm soát PC của các bạn.

Ngoài ra còn có 1 số port như :

- Warcraft 3 là 6112

- Age of Empire 2 : 2300-2400, 47624

- Võ lâm truyền kỳ 1 : 5622 , 6xxx

- AOL Messenger : 5190

- ICQ 2000 : 5190

- MSN Messenger : 1863

- Port 37: Time

- Port 43: Whois:50::17:
