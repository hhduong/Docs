# GIAO THỨC SSH
## Mục lục
[1. SSH là gì?](#ssh-kn)

[2. SSH hoạt động như thế nào?](#ssh-hd)

[3. Hiểu về nhiều kỹ thuật mã hóa khác nhau](#ssh-mh)
 
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
* SSH làm việc thông qua 3 bước đơn giản:
    * Định danh host - xác định định danh của hệ thống tham gia phiên làm việc SSH
    * Mã hoá - thiết lập kênh làm việc mã hoá
    * Chứng thực - xác thực người sử dụng có quyền đăng nhập hệ thống

### Định danh host (được hiểu là máy khách - máy tính điều khiển)
* Việc định danh host được thực hiện qua việc trao đổi khoá. Mỗi máy tính điều khiển SSH có một khoá định danh duy nhất
* Khoá này gồm hai thành phần: khoá riêng tư và khoá công cộng
    *  Khoá công cộng được sử dụng khi cần trao đổi giữa các máy chủ với nhau trong phiên làm việc SSH, dữ liệu sẽ được mã hoá bằng khoá công khai và chỉ có thể giải mã bằng khoá riêng
*  Khi có sự thay đổi về cấu hình trên máy chủ: thay đổi chương trình SSH, thay đổi cơ bản trong hệ điều hành, khoá định danh cũng sẽ thay đổi. Khi đó mọi người sử dụng SSH để đăng nhập vào máy chủ này đều được cảnh báo về sự thay đổi này. 
*  Khi hai hệ thống bắt đầu một phiên làm việc SSH, máy chủ sẽ gửi khoá công cộng của nó cho máy khách. Máy khách sinh ra một khoá phiên ngẫu nhiên và mã hoá khoá này bằng khoá công cộng của máy chủ, sau đó gửi lại cho máy chủ
* Máy chủ sẽ giải mã khoá phiên này bằng khoá riêng của mình và nhận được khoá phiên. Khoá phiên này sẽ là khoá sử dụng để trao đổi dữ liệu giữa hai máy

### Mã hoá dữ liệu
* Sau khi hoàn tất việc thiết lập phiên làm việc bảo mật (trao đổi khoá, định danh), quá trình trao đổi dữ liệu diễn ra thông qua một bước trung gian đó là mã hoá/giải mã.
* Việc lựa chọn cơ chế mã hoá thường do máy khách quyết định. Các cơ chế mã hoá thường được chọn bao gồm: 3DES, IDEA, và Blowfish
* Khi cơ chế mã hoá được lựa chọn, máy chủ và máy khách trao đổi khoá mã hoá cho nhau. Việc trao đổi này cũng được bảo mật dựa trên đinh danh bí mật của các máy
* Các thuật toán mã hoá khác nhau và các ưu, nhược điểm của từng loại:

   * 3DES (cũng được biết như Triple-DES) -- phương pháp mã hoá mặc định cho SSH.
   * IDEA—Nhanh hơn 3DES, nhưng chậm hơn Arcfour và Blowfish.
   * Arcfour—Nhanh, nhưng các vấn đề bảo mật đã được phát hiện.
   * Blowfish—Nhanh và bảo mật, nhưng các phương pháp mã hoá đang được cải tiến.

### Chứng thực và giải mã
* Việc chứng thực là bước cuối cùng trong ba bước, và là bước đa dạng nhất.Tại thời điểm này, kênh trao đổi bản thân nó đã được bảo mật.
* Mỗi định danh và truy nhập của người sử dụng có thể được cung cấp theo rất nhiều cách khác nhau.
* Việc chứng thực mật khẩu là một cách rất thông dụng để định danh người sử dụng, nhưng ngoài ra cũng có các cách khác: chứng thực RSA, sử dụng ssh-keygen và ssh-agent để chứng thực các cặp khoá.

## <a name = "ssh-mh"></a> 3.Hiểu về nhiều kỹ thuật mã hóa khác nhau.
* Có 3 cách khác nhau để mã hóa qua SSH:
    1. Symmetrical encryption
    2. Asymmetrical encryption
    3. Hashing
### Symmetric Encryption
* Symmetric encryption là một dạng mã hóa sử dụng secret key ở cả 2 chiều mã hóa và giải mã tin nhắnb bởi cả host và client.
![Imgur](https://i.imgur.com/YKMVPSx.jpg")
* Symmetric keys được sử dụng để mã hóa toàn bộ liên lạc trong phiên giao dịch SSH. Cả client và server tạo chung một key bí mật như là một phương thức thỏa thuận, và key đó không được tiết lộ cho bên thứ ba. Quá trình tạo symmetric key được thực hiện bởi key exchange algorithm.

* Điều khiến cho thuật toán an toàn là vì key không được truyền giữa client và host. Thay vào đó, cả 2 máy tính chia sẽ thông tin chung và sau đó sử dụng chúng để tính ra khóa bí mật.Kể cả có máy khác bắt được thông tin chung, nó cũng không thể tính ra key bí mật vì không biết được thuật toán tạo key.

### Asymmetrical encryption
* Không giống với symmetrical encryption, asymmetrical encryption sử dụng 2 khóa khác nhau để mã hóa và giải mã. 2 khóa này được gọi là public key và private key. Cả 2 hình thành nên một cặp khóa là public-private key pair
![Imgur](https://i.imgur.com/aId3jMz.jpg")
* Khóa public, như tên gọi của nó sẽ được công khai cho tất cả các bên liên quan.
* private key không thể được tính toán ra từ một public key
* Thư được mã hóa bởi public key của một máy, và chỉ có thể được giải mã bởi private key của chính máy đó
* public key không thể giải mã chính thư của nó, hoặc không thể giải mã bất kỳ thứ gì được mã hóa bằng private key
* Private key phải luôn luôn được đảm bảo an toàn
* Sức mạnh của cả chu trình kết nối phụ thuộc vào việc private key có bị tiết lộ hay không, vì chỉ có nó mới có khả năng giải mã thư được truyền đi mà được mã hóa bởi public key

### Hashing
* Hashing một chiều là một dạng mã hóa khác sử dụng trong Secure Shell Connections. 
* Hash một chiều khác với cả 2 phương thức mã hóa trên ở chỗ nó không được sinh ra để giải mã. Chúng tạo ra một giá trị duy nhất với độ dài nhất định cho mỗi lần nhập liệu mà không có hướng nào khác để khai thác. Điều này khiến nó dường như không thể quay ngược lại giải mã.
![Imgur](https://i.imgur.com/vamaLmx.jpg")
* SSH sử dụng hashes để xác nhận tính xác thực của tin nhắn. Nó được thực hiện bởi HMACs, hoặc Hash-based Message Authentication Codes. Việc này đảm bảo lệnh không bị giả mạo bởi bất kỳ phương thức nào.
* Mỗi tin nhắn được truyền đi phải chứa MAC, được tính bởi symmetric key, packet sequence number, và nội dung tin nhắn. Nó truyền ra ngoài một gói dữ liệu được mã hóa symmetric như là một phần của communication packet.

 



