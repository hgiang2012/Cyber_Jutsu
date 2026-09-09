# FILE UPLOAD VULNERABILITIES #

## LAB 

# 1.

<img width="330" height="83" alt="image" src="https://github.com/user-attachments/assets/4b0d7855-a75e-4466-9021-cd1d05ef4c29" />

<img width="326" height="89" alt="image" src="https://github.com/user-attachments/assets/04103377-5311-4622-a3f1-de63ee0a05ca" />

Vẫn thành công

<img width="716" height="206" alt="image" src="https://github.com/user-attachments/assets/691ba06a-eb9a-42ac-8e64-8ab25127b2f7" />

<img width="700" height="71" alt="image" src="https://github.com/user-attachments/assets/6c648907-2e4b-40e8-b2a2-b28e84cfc337" />
 Code được thực thi thành công

<img width="323" height="95" alt="image" src="https://github.com/user-attachments/assets/67120847-4779-4bcd-8d03-88f262a450ad" />

<img width="475" height="344" alt="image" src="https://github.com/user-attachments/assets/84a44dde-e826-41aa-aac1-4de4b96a487a" />

<img width="340" height="91" alt="image" src="https://github.com/user-attachments/assets/6aaaa1f4-e22e-4056-876d-681e6550a0ab" />

<img width="203" height="36" alt="image" src="https://github.com/user-attachments/assets/9748f473-1b81-49b2-9a68-3f4dc8b3c548" />

CBJS{why-php-run-what?}

# 2.

<img width="605" height="281" alt="image" src="https://github.com/user-attachments/assets/89570840-4fc4-4223-b15c-747d2735b396" />

$extension = explode(".", $filename)[1];
Ở đây, code sẽ xác định file extension ở mảng 1 ngăn cách bởi dấu '.'
Ví dụ 1:
'abc.txt' txt sẽ là mảng 1
Ví dụ 2
'abc.php.jpg' 
mảng 0: abc
mảng 1: php
mảng 2: jpg
--> extension ở đây là php

<img width="482" height="192" alt="image" src="https://github.com/user-attachments/assets/ca9ecebd-47ca-4e6f-9ce2-854b79114267" />

<img width="338" height="86" alt="image" src="https://github.com/user-attachments/assets/061c6fbf-5b1f-4c40-9385-3021e3fb2503" />

<img width="181" height="50" alt="image" src="https://github.com/user-attachments/assets/3701f067-1a8c-40ea-9f40-8ab0492731f9" />

Dù chương trình nhận định đuôi file là txt nhưng đuôi file cuối là php -> vẫn chạy chương trình php
<img width="181" height="50" alt="image" src="https://github.com/user-attachments/assets/b7c7ae53-f4d6-452e-8362-9fe7c3fefc24" />

<img width="317" height="81" alt="image" src="https://github.com/user-attachments/assets/56b23d1b-e259-4510-a89c-27c55cdc1b21" />
<img width="512" height="360" alt="image" src="https://github.com/user-attachments/assets/925d48eb-1951-4b5b-8da4-a2e9a69810c1" />
<img width="320" height="101" alt="image" src="https://github.com/user-attachments/assets/790cf957-f1e4-4cf8-b635-78a8a98af220" />
<img width="321" height="62" alt="image" src="https://github.com/user-attachments/assets/3ecc5c2f-b5bc-4126-a01a-d5c480d7c412" />
CBJS{wr0nGlY_ImplEm3nt}

# 3

<img width="614" height="285" alt="image" src="https://github.com/user-attachments/assets/2426a733-dd34-4be4-ab33-f4a1297543e4" />

Chương trình xét phần tử cuối cùng sau ".", kết thúc bằng php thì chương trình end


<img width="554" height="182" alt="image" src="https://github.com/user-attachments/assets/f66f0cf3-a653-480b-b301-ee3f13e594ac" />

<img width="288" height="185" alt="image" src="https://github.com/user-attachments/assets/994976bc-f4c5-4a8c-b65c-e8754671e6ab" />

<FilesMatch ".+\.ph(ar|p|tml)$">
    SetHandler application/x-httpd-php
</FilesMatch>

Apache sẽ dùng PHP handler để xử lý những file có tên kết thúc bằng .phar, .php, hoặc .phtml

DirectoryIndex disabled
DirectoryIndex index.php index.html

Đây là cấu hình khi up thư mục mà không ghi tên file, Apache sẽ quyết định mở thư mục nào trong đó
Nhưng ở đây tồn tại 2 cấu hình trái ngược nhau
DirectoryIndex disabled --> tắt
DirectoryIndex index.php index.html --> bật
Nhưng vì DirectoryIndex index.php index.html được set up sau, nên đây sẽ là cấu hình được khởi 

<LocationMatch ^/upload/$>
    Order deny,allow
    Deny from all
</LocationMatch>

Cấu hình deny all truy cập vào /upload/
nhưng ví dụ /upload/test.jpg thì vẫn được

Mà ta để ý rằng, ngoại trừ đuôi .php thì ở đây: .phar và .phtml vẫn được php xử lý nhưng code chỉ detect đuôi .php để chặn
<img width="340" height="72" alt="image" src="https://github.com/user-attachments/assets/13637171-787f-412d-b77f-5628280a5ded" />

<img width="200" height="67" alt="image" src="https://github.com/user-attachments/assets/ac13a86a-a0b5-4acf-872f-ef8a6f1fbb07" />
<img width="556" height="385" alt="image" src="https://github.com/user-attachments/assets/df057c5d-762d-4557-80ee-9a6ba39f4a25" />
<img width="157" height="44" alt="image" src="https://github.com/user-attachments/assets/f90af69d-7c55-4dd1-94c1-46a1e5bde8fd" />
CBJS{bl4ck_list?}

# 4
<img width="612" height="286" alt="image" src="https://github.com/user-attachments/assets/f2935a1f-f8c4-4e40-b726-993b2b40a8e8" />
Ở đây, dev đã fix lại lỗi ở lab 3 và chặn cả 3 đuôi file là .phar, .php, .phtml

# APACHE CONFIG 

```
<Directory />
        Options FollowSymLinks
        AllowOverride None
        Require all denied
</Directory>
```
--> Mặc định Apache deny toàn bộ file system

```<Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
</Directory>
```
`AllowOverride All` --> cho phép `.htaccess` ghi đè

```<FilesMatch "^\.ht">
        Require all denied
</FilesMatch>
```
Tên file bắt đầu bằng `.ht` sẽ bị từ chối truy cập qua HTTP


#
# The following directives define some format nicknames for use with
# a CustomLog directive.
ErrorLog ${APACHE_LOG_DIR}/error.log
LogLevel warn

LogFormat "%v:%p %h %l %u %t \"%r\" %>s %O \"%{Referer}i\" \"%{User-Agent}i\"" vhost_combined
LogFormat "%h %l %u %t \"%r\" %>s %O \"%{Referer}i\" \"%{User-Agent}i\"" combined
LogFormat "%h %l %u %t \"%r\" %>s %O" common
LogFormat "%{Referer}i -> %U" referer
LogFormat "%{User-agent}i" agent

# Include generic snippets of statements
IncludeOptional conf-enabled/*.conf

# Include the virtual host configurations:
IncludeOptional sites-enabled/*.conf
 ```
 

## NOTE



<img width="570" height="250" alt="image" src="https://github.com/user-attachments/assets/75521519-7606-4525-9ab0-801b83c8d517" />

Dòng 3: tạo tag input với kiểu file, cho phép ng dùng chọn file
Dòng 4: tạo tag submit
Bọc bởi tag form, định nghĩa dữ liệu nên được gửi lên sv theo cấu trúc 

<img width="650" height="313" alt="image" src="https://github.com/user-attachments/assets/239d2880-05d3-4732-bceb-df529b005063" />

Kiểu dữ liệu được gửi ở đây là multipart, có thêm tham số boundary=...
Tạo ra ranh giới giữa các trường dữ liệu


Docker là ctrinh tạo  môi trường ảo để chạy process ảo


<img width="686" height="170" alt="image" src="https://github.com/user-attachments/assets/7091b8a5-1604-4369-bf00-0ffb0e179135" />

Hàm var_dump($_FILES) sẽ in ra giá trị biến và kiểu dữ liệu của 
<img width="466" height="310" alt="image" src="https://github.com/user-attachments/assets/9f7563e6-ec01-4238-baa7-f3608db63a02" />

Muốn xóa file vừa upload

<img width="777" height="76" alt="image" src="https://github.com/user-attachments/assets/96a90788-4f83-4195-b1c6-6525977d3bc5" />

Kiểm tra các container đang chạy

<img width="593" height="74" alt="image" src="https://github.com/user-attachments/assets/78ae95be-7dce-4dad-804d-819e1350b64f" />


<img width="667" height="256" alt="image" src="https://github.com/user-attachments/assets/4a235fdc-db0a-4f96-9fdb-2457719919d4" />

Cấu trúc $_FILES
```$_FILES
└── file
    ├── name: tên file
    ├── full_path
    ├── type: MIME type
    ├── tmp_name: đường dẫn tạm thời mà PHP lưu file upload trên server 
    ├── error: mã trạng thái upload
    └── size: kích thước file
```

<img width="322" height="16" alt="image" src="https://github.com/user-attachments/assets/8908b113-1976-4868-bbff-0ae98792e89b" />

```/tmp/phpABC123
       │
       │ move_uploaded_file()
       ↓
upload/test.jpg
```

- Config của Apache2 dùng để cấu hình cho các hành vi và chức năng của nó như
+ DocumentRoot
+ FileHandler
+ Encryption
+ Error Messages....

- Các config được lưu ở
+ /etc/apache2/
+ /etc/apache2/sites-available/
+ /etc/apache2/sites-enabled/
+ /etc/apache2/mods-available/
+ /etc/apache2/conf-available/

+ 


    



