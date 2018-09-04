# GIAO THỨC SSH
## Mục lục
[1. SSH là gì?](#ssh-kn)

[2. SSH hoạt động như thế nào?](#ssh-hd)

## <a name = "cach-kn"></a> 1. SSH là gì?

*  Là một giao thức mạng dùng để thiết lập kết nối mạng một cách bảo mật. SSH hoạt động ở lớp trên trong mô hình phân lớp TCP/IP
* Là một giao thức mạng được sử dụng để đăng nhập vào một máy tính từ xa
* Dịch vụ được tạo ra nhằm thay thế cho trình Telnet vốn không có mã hóa và sử dụng kỹ thuật cryptographic để đảm bảo tất cả giao tiếp gửi tới và gửi từ server từ xa diễn ra trong tình trạng mã hóa
* Các dữ liệu mà bạn gửi đi hoặc nhận thông qua giao thức SSH sẽ đều được mã hóa lại để bảo mật thông tin an toàn hơn

## <a name = "ssh-hd"></a> 2. SSH hoạt động như thế nào?

*  Nếu bạn đang sử dụng Linux hoặc Mac, sử dụng SSH rất đơn giản. Nếu bạn sử dụng Windows, bạn chỉ cần sử dụng những SSH client để mở kết nối SSH. Những trình SSH client phổ biến là Putty
* Đối với người dùng xài MAC và Linux, hãy mở terminal và làm theo hướng dẫn sau:
 
 * Lệnh SSH có 3 phần:
    * `ssh {user}@{host}`
         * SSH key command cho hệ thống biết là bạn muốn mở một kết nối được mã hóa Secure Shell Connection.
         * `{user}` đại diện cho tài khoản người dùng bạn muốn dùng để truy cập.
         * `{host}` đại diện cho máy tính bạn muốn dùng để truy cập. Nó có thể là một địa chỉ IP (ví dụ 244.235.23.19) hoặc một tên miền (ví dụ, www.xyzdomain.com).
* Khi bạn nhấn enter, nó sẽ hỏi bạn nhập mật khẩu tương ứng cho tài khoản. Khi bạn gõ, bạn sẽ không thấy bất kỳ dấu hiệu nào trên màn hình, nhưng nếu bạn gõ đúng mật khẩu và nhấn enter, bạn sẽ vào được hệ thống và nhận thông báo đăng nhập thành công
* [Một số lệnh của SSH](https://www.hostinger.vn/huong-dan/lenh-ssh-co-ban/)

 



