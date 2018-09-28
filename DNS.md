# DNS
## I. DNS là gì?
- DNS là Hệ thống phân giải tên miền, viết tắt của Domain Name Servers, nó "dịch" tên miền Internet và tên máy chủ sang địa chỉ IP (giúp các máy chủ và thiết bị mạng có thể hiểu được) và ngược lại.

## II. DNS hoạt động như thế nào?
- Cơ chế làm việc của DNS là phân phối, truyền tải các thông tin, dữ liệu có chứa thông tin trùng khớp với tên miền tới địa chỉ IP tương ứng của website.
- Các domain và sub-domain còn được gọi dưới tên alias.
- Server lưu trữ thông tin về địa chỉ và các alias khác nhau được gọi là Name Server.
- Có 2 loại server chính phục vụ cho Domain Name System:
  - Root Server: chứa thông tin về TLD (phần đuôi domain).
  - Server khác xử lý thông tin chính vể domain, sub-domain.

## III. Cơ chế làm việc của DNS Lookup
- Thiết bị router, modem... của bạn sẽ liên lạc với dịch vụ DNS để tiến hành phân giải DNS tương ứng. 
- Dịch vụ DNS sẽ tiếp tục liên lạc tới Root Server và yêu cầu địa chỉ IP của server đang chứa phần đuôi (VD: *.com, *.vn, ...), ví dụ ở đây đặt là *.com, phần địa chỉ này sẽ được gửi ngược trở lại về dịch vụ DNS.
-  Dịch vụ DNS này sẽ tiếp tục tìm trong Name Server có chứa tất cả các địa chỉ domain *.com và tìm địa chỉ IP của web đó. 
- Sau khi lấy được địa chỉ IP tương ứng của web, dịch vụ DNS sẽ trả địa chỉ IP về máy tính, đó là lúc nội dung, ảnh, text trên website hiển thị trên trình duyệt.
