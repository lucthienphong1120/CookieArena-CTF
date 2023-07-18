Đây là 1 file pcap dữ liệu TFTP, ta sử dụng các lệnh với tool tshark để kiểm tra gói tin

`tshark -qz io,phs -r TrivialFTP.pcapng`

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/c80e77f7-063f-430d-8f69-122eff5581cd)

Nhận thấy lưu lượng gói tin được chuyển đi ở TFTP là khá lớn, vậy nên tôi sử dụng lệnh để lấy gói tin đấy ra 

`tshark -r TrivialFTP.pcapng --export-objects "tftp,object" -2 > /dev/null`

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/99b79903-3b63-467e-baf5-cade3a652ee8)

Mở thử file pdf thì thấy không được, có thể file bị lỗi gì đó, kiểm tra lại file pcap thì thấy rằng file pdf này được chuyển đi với mã hóa netascii => cần phải sửa các byte dạng _\x0d\x0a_ thành _\x0a_ và _\x0d\x00_ thành _\x0d_ (thông tin lấy từ [wiki](https://en.wikipedia.org/wiki/Trivial_File_Transfer_Protocol))

> Netascii is a modified form of ASCII, defined in RFC 764. It consists of an 8-bit extension of the 7-bit ASCII character space from 0x20 to 0x7F (the printable characters and the space) and eight of the control characters. The allowed control characters include the null (0x00), the line feed (LF, 0x0A), and the carriage return (CR, 0x0D). Netascii also requires that the end of line marker on a host be translated to the character pair CR LF for transmission, and that any CR must be followed by either a LF or the null.

Sử dụng Hxd để Replace các byte

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/fd690dc7-8589-4471-be5d-08fb8893d19a)

Lưu file, mở lại file pdf và nhận được flag 

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/4d8afccd-89b3-45c6-861e-c5759275827c)

```CHH{FTP_4nd_TFTP_4r3_b0th_un$af3}```
