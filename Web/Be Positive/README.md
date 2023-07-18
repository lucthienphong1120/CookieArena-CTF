Đề bài:

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/cafec502-7360-42af-ada0-b09c9338c3fd)

Tạm hiểu là có 2 username/password là `alice:alice` và `bob:bob`

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/ddfc231a-4699-49f3-a7f1-adc51a46451c)

Sau khi đăng nhập thì có 1 hệ thống charge coin thế này

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/5ba7e4e9-3c3d-4cbd-8f2d-4f503ad2ad42)

Chú ý có chức năng transfer (chuyền tiền)

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/3213c6cf-16e4-4071-b060-93cc4a7b8fb6)

Mình có 2 tài khoản, mỗi tài khoản có 1500$, nếu chuyển max vẫn chỉ 3000$, chưa đủ mua flag(3001$)

Suy nghĩ kĩ thì thấy sau khi chuyển tiền sẽ bị trừ số tiền gốc

```
money -= transfer_money
```

Vậy có thể chuyển số tiền âm thì sao

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/5d13ae9d-b387-4d4f-873d-427965b1d01e)

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/4e07e4d8-9953-4ca6-823c-c1be2323390c)

**CHH{ThiS_i5_Y0ur_FaKE_fLaG}**
