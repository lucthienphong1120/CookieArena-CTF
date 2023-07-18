Chúng ta kiểm tra ảnh được tải về với tool [Aperisolve](https://www.aperisolve.com/) thì thấy được 2 password, có thể sẽ dùng trong thời gian tới (vì hiện tại chưa biết dùng làm gì)

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/e4751a01-983b-43bc-91bf-1ea251ec7859)

Tôi dùng exiftool (được tích hợp ở Aperisolve) thì có một dòng warning là có data nào đó ở sau PNG IEND chunk

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/6e8754ff-6e34-47f9-9c1a-fe0ad950c740)

Điều này chứng tỏ, ảnh này chính là một file zip chứa thông tin, tôi đổi phần mở rộng của file thành zip và extract, được 2 file khác

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/a260161b-aee0-4745-af17-46a423899736)

Mở thử file y0u_4r3_cl0s3.rar thì được thông báo lỗi không thể mở do bị hỏng, vậy nên tôi thử xem mã hex của nó bằng Hxd

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/cc9dc1dc-5dcb-4a3c-9475-752efe895026)

Nhìn thấy signature của file bị sai (định dạng đúng phải là ```52 61 72 21 == Rar!```) nên tôi sửa và lưu lại file, mở ra và thấy có 1 file cần mật khẩu 

Thử dùng mật khẩu ban đầu mà mình tìm được ```cookiehanhoan và sp3ctrum_1s_y0ur_fr13nd``` thì thấy được ```sp3ctrum_1s_y0ur_fr13nd``` là mật khẩu đúng, mở file và lấy được flag được mã hóa base64 => giải mã và ta có được flag

```CHH{f0r3n51cs_ma5t3r}```
