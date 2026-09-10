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
`AllowOverride All` --> cho phép `.htaccess` ghi đè, tự 

```<FilesMatch "^\.ht">
        Require all denied
</FilesMatch>
```
Tên file bắt đầu bằng `.ht` sẽ bị từ chối truy cập qua HTTP

Nhìn lại 3 lab trước, ứng với mỗi config của code thì có 1 hướng đi khác 
--> có thể tự thay đổi config của apache ?
--> tự upload `.htaccess` 
Ta sẽ Upload file `.htaccess` giả lên để tạo ra config cho mod-php với đuôi file tùy 
<img width="854" height="106" alt="image" src="https://github.com/user-attachments/assets/14bcb548-7a3e-4c31-acf0-2c250b1882e5" />
- Up thành công, file này sẽ config những file có đuôi là `.pha`, `.phb`, `.phc` sẽ chạy được 

<img width="344" height="80" alt="image" src="https://github.com/user-attachments/assets/043a18fa-59d7-425a-9b6c-d8bd075dd458" />

<img width="683" height="69" alt="image" src="https://github.com/user-attachments/assets/533f782a-93fd-455e-9037-ac6291036fa6" />


<img width="310" height="89" alt="image" src="https://github.com/user-attachments/assets/05064706-61bb-473c-8c2e-d6c01ef335c9" />


<img width="644" height="344" alt="image" src="https://github.com/user-attachments/assets/489bc094-8a59-4bc0-b75a-dd0357ab8a79" />


<img width="333" height="83" alt="image" src="https://github.com/user-attachments/assets/3a2ce175-c262-44b5-ae4e-ac288685f426" />


<img width="383" height="56" alt="image" src="https://github.com/user-attachments/assets/bac178a9-4f4c-46e4-b50a-3b7439761252" />

CBJS{so_magic_I_wondeR_what_about_other_system?}

# CÁCH TIẾP CẬN KHÁC VỚI LỖI XSS


<img width="329" height="100" alt="image" src="https://github.com/user-attachments/assets/9d40d70d-a23a-4247-a457-5f73dff8df68" />


<img width="108" height="60" alt="image" src="https://github.com/user-attachments/assets/a7d90435-ad74-4b00-9ebc-406d2b759329" />


<img width="267" height="101" alt="image" src="https://github.com/user-attachments/assets/87818ec8-2aa7-4823-a0ad-df9cdca9dca3" />


<img width="745" height="196" alt="image" src="https://github.com/user-attachments/assets/0a85b9da-3390-45c0-9dee-9437e3b7d59f" />

---> lợi dụng để cướp cookie nạn nạn nhân


<img width="482" height="314" alt="image" src="https://github.com/user-attachments/assets/1b7c9dc7-6d8f-4d7c-be2a-61e4b3bcb3d2" />

<img width="331" height="251" alt="image" src="https://github.com/user-attachments/assets/1f03477f-7d7f-4aa3-85e0-b8fb73b54b35" />




# 5


<img width="482" height="221" alt="image" src="https://github.com/user-attachments/assets/e45e8bd7-bb47-4921-a76d-510889b3b37b" />

<img width="621" height="345" alt="image" src="https://github.com/user-attachments/assets/3d1cbe80-597d-43bc-867e-9de54dc062db" />
Chỉ được up ảnh

<img width="448" height="228" alt="image" src="https://github.com/user-attachments/assets/a4ce24c7-68b4-4970-b126-24eab7ad23cc" />

Thử đổi file name và nội dung

<img width="358" height="92" alt="image" src="https://github.com/user-attachments/assets/3651176b-debb-489a-a615-2cc1b7f842ae" />

<img width="73" height="41" alt="image" src="https://github.com/user-attachments/assets/c7a84483-7d9b-48a1-8356-54e2a9ee5983" />


<img width="333" height="82" alt="image" src="https://github.com/user-attachments/assets/2795ba7e-c8d8-4756-8a2f-3371eeca55b4" />

<img width="195" height="55" alt="image" src="https://github.com/user-attachments/assets/28eaa02a-3759-422a-a0a4-26a379228aa1" />


<img width="350" height="77" alt="image" src="https://github.com/user-attachments/assets/a3d62ce6-ed2f-4d61-8e6f-9e9aba59bb14" />

<img width="521" height="338" alt="image" src="https://github.com/user-attachments/assets/62d42729-dec8-4e0e-9ca9-1adead2b9f12" />


<img width="402" height="99" alt="image" src="https://github.com/user-attachments/assets/6d1be40d-677d-475b-9829-8f1cbcd21b3f" />


<img width="314" height="93" alt="image" src="https://github.com/user-attachments/assets/939ff1a9-b35a-418b-b5f9-b26869ef1b28" />

CBJS{why_you_check_with_useR_input}

# 6


<img width="598" height="362" alt="image" src="https://github.com/user-attachments/assets/710700a7-a1e2-4ace-b0f5-5f84cbaa5b65" />

Code giờ không chỉ check content type mà còn check cả nội dung 



<img width="470" height="214" alt="image" src="https://github.com/user-attachments/assets/65ff0adc-bbe2-49e0-b9f4-c8ee651acbbc" />
 Để nguyên nội dung file và đổi tên file --> hệ thống vẫn nhận



<img width="446" height="292" alt="image" src="https://github.com/user-attachments/assets/1f61a4f5-d844-43ee-aa28-f9765d3a29f1" />

Check lại các signature của các file mà hệ thống cho phép và test thử từng trường hợp 

<img width="604" height="190" alt="image" src="https://github.com/user-attachments/assets/bfa86801-8fb5-4dcc-9f31-e4d39c043563" />


<img width="578" height="83" alt="image" src="https://github.com/user-attachments/assets/0b3c69dd-588b-483f-a6c3-7ebc5ae8234b" />


<img width="610" height="86" alt="image" src="https://github.com/user-attachments/assets/94df02db-2723-40eb-90c8-2b5e223b1b08" />


<img width="401" height="134" alt="image" src="https://github.com/user-attachments/assets/12a3a3b8-4a69-4a93-8f08-06d0862feafc" />

Thành công

<img width="145" height="57" alt="image" src="https://github.com/user-attachments/assets/606566c0-0fa8-4042-bbaf-7b6ce3db9088" />



<img width="416" height="353" alt="image" src="https://github.com/user-attachments/assets/fde0be21-783d-4997-ab7d-59453cbf7447" />



<img width="232" height="72" alt="image" src="https://github.com/user-attachments/assets/46c0f959-a675-47eb-8446-2065b04312e4" />


CBJS{ch3ck_mag1c_bite_iz_tragic}














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

-  Các file config của Apache
+ File config chính
<img width="205" height="119" alt="image" src="https://github.com/user-attachments/assets/358701c2-6de7-450d-832f-7978600aaa1e" />
+ File `.htaccess`
  <img width="223" height="104" alt="image" src="https://github.com/user-attachments/assets/0ef6e5d1-ed17-4708-89fc-d4f2c04aa79c" />
Cho phép cấu hình Apache ngay tại từng thư mục 
 <img width="292" height="208" alt="image" src="https://github.com/user-attachments/assets/bdab20e2-a08b-40f6-b8b7-ca36de5445ba" />



    



