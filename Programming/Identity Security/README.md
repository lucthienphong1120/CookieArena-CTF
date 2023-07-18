Đề bài:

```
Cookie Arena tổ chức cuộc thi CTF Season II thành công rực rỡ với hàng nghìn lượt đăng ký dự thi. Sau khi kết thúc, ngoài top 10 các bạn thí sinh đạt thành tích cao nhất và được giải chính thức của cuộc thi thì ban tổ chức quyết định sẽ trao tặng một số phần quà hiện vật nho nhỏ cho các bạn thí sinh đạt thành tích tốt, nhằm khích lệ tinh thần của các bạn trong các cuộc thi sau này do Cookie Arena tổ chức. Để công bố danh sách các thí sinh thì ban tổ chức quyết định dùng username để lên danh sách. Tuy nhiên, username trong hệ thống của Cookie Arena là email hoặc số điện thoại cá nhân của người dùng. Việc công khai các thông tin này là điều cấm kỵ, vì vậy bạn tổ chức quyết định che bớt một số ký tự, chỉ để lại một lượng nhỏ, vừa đủ để các thí sinh biết được rằng mình nằm trong danh sách có phần thưởng để liên hệ với ban tổ chức nhận quà.

Cụ thể, cách thức bảo mật danh tính của của thí sinh như sau:

Với thông tin số điện thoại thì chỉ hiển thị 2 chữ số đầu và 3 chữ số cuối, còn lại được che bằng ký tự hoa thị (*) với mỗi chữ số là một ký tự hoa thị tương ứng.
Với thông tin địa chỉ email thì chỉ giữ lại 2 ký tự đầu và 3 ký tự cuối của phần username, và tên miền (domain), các ký tự còn lại cũng được che tương tự như trên (trong trường hợp username quá ngắn, ít hơn hoặc bằng 7 ký tự thì chỉ giữ lại ký tự đầu và cuối của username). Biết rằng cấu trúc của một địa chỉ email luôn là username@domain.
Hãy giúp ban tổ chức một tay để bảo mật danh tính các thí sinh nào!

Đầu vào Dòng thứ nhất chứa một số nguyên duy nhất N là số lượng thông tin cần được che (1N1000) Tiếp theo là N dòng, mỗi dòng chứa 1 xâu chứa một trong 2 loại thông tin: Số điện thoại, là các chuỗi chữ số có độ dài 9, 10 hoặc 11 chữ số từ 0 đến 9. Địa chỉ email là các chuỗi ký tự bao gồm chữ cái hoa, thường trong bảng mã ASCII, dấu chấm, và 1 ký tự @ để phân chia username và tên miền (luôn đảm bảo email có 1 ký tự @). Độ dài của username của email tối thiểu 3 ký tự và tối đa 1000 ký tự.

Đầu ra N dòng tương ứng là các thông tin của các bạn sinh viên đã được giải tương ứng.
```

Ví dụ

Đầu vào
```
5
cookiearena@gmail.com
0123456789
deptrai@khongsai.com
a1Z@xyz.com
99999999977
```
Đầu ra
```
co******ena@gmail.com
01*****789
d*****i@khongsai.com
a*Z@xyz.com
99******977
```

Giải:

```python
user_input_number = int(input())


for i in range (0, user_input_number):
    string = input().strip()
    if "@" in string:
        username = string.split("@")[0]
        new_username = ""
        if len(username) <= 7:
            if (len(username) <= 2):
                new_username = username
            else:
                new_username = username[0] + "*" * (len(username)-2) + username[-1:]
        else:
            first_numbers = username[:2]
            last_numbers = username[-3:]
            new_username = first_numbers + "*" * (len(username) - 5) + last_numbers
        print (new_username + "@" + string.split("@")[1])
    else:
        first_numbers = string[:2]
        last_numbers = string[-3:]
        modified_string = first_numbers + "*" * (len(string) - 5) + last_numbers
        print (modified_string)
```

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/a2b3839b-b898-43b2-9a08-f9cc38428c20)

```CHH{1DeNt17Y_SecuriTy_b3d79a1397808e0ad1a58ffe79ff13b7}```
