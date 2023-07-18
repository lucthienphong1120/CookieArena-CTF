Đề bài:

```
Tab vốn là một học sinh rất giỏi toán, nên sau khi tham gia khoá học “Xoá mù bảo mật” của Cookie Hân Hoan, cậu liên muốn áp dụng các kỹ thuật toán học để nhằm mã hoá các mật khẩu của mình. Mật khẩu là một chuỗi ký tự S có độ dài n (thứ tự các ký tự từ trái qua phải lần lượt là từ 1 đến n), cách thức mã hoá là thực hiện theo quy trình sau:

Lặp đi lặp lại với lần lượt các ước số nguyên của n theo thứ tự giảm dần từ n tới 1.
Với ước số d của n, sẽ đảo ngược chuỗi con S[1…d] (tức là chuỗi con gồm d ký tự đầu tiên) Sau khi thực hiện quy trình trên, Tab sẽ nhận được 1 mật khẩu đã được mã hoá.
Ví dụ: Với mật khẩu là chuỗi cookiearenactf có độ dài 14. Với n = 14 có 4 ước số lần lượt là 14, 7, 2, 1.

Với d = 14, ta sẽ đảo 14 ký tự đầu tiên, cookiearenactf → ftcaneraeikooc
Với d = 7, ta sẽ đảo 7 ký tự đầu tiên, ftcaneraeikooc → renactfaeikooc
Với d = 2, ta đảo 2 ký tự đầu tiên, renactfaeikooc → ernactfaeikooc
Với d =1, ta đảo 1 ký tự đầu tiên, dĩ nhiên là không thay đổi gì, và nhận được mật khẩu đã được mã hoá là ernactfaeikooc
Và giờ Tab lưu lại mật khẩu đã được mã hoá của mình. Đến giờ cần đăng nhập, hãy giúp Tab tìm lại đúng mật khẩu của mình nào.

Đầu vào Dòng đầu tiên là một số nguyên n (1≤n≤1000), là độ dài của mật khẩu. Dòng thứ hai là một xâu ký tự có độ dài n bao gồm các chữ cái latin viết thường [a-z], chính là mật khẩu đã được mã hoá.

Đầu ra In ra xâu ký tự có độ dài n, chính là mật khẩu ban đầu trước khi được mã hoá. Lưu ý: luôn đảm bảo tồn tại mật khẩu chính xác và duy nhất.
```

Ví dụ

Đầu vào
```
14
ernactfaeikooc
```
Đầu ra
```
cookiearenactf
```
Đầu vào
```
16
plmaetwoxesisiht
```
Đầu ra
```
thisisexampletwo
```
Đầu vào
```
1
c
```
Đầu ra
```
c
```

Hỏi ChatGPT và có đáp án

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/314fac13-93df-4889-a73a-631d3bc54b2b)

```python
n = int(input())
encoded_password = input()

decoded_password = list(encoded_password)

for d in range(1, n+1):
    if n % d == 0:
        decoded_password[:d] = decoded_password[:d][::-1]

decoded_password = "".join(decoded_password)
print(decoded_password)
```

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/a3298d89-3088-4539-83cc-41f987a507bd)

```CHH{pro9R4mmINg_D3CRYPT_669444ee035e88d87ca18640b456b9fd}```
