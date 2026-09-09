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
$_FILES
└── file
    ├── name: tên file
    ├── full_path
    ├── type: MIME type
    ├── tmp_name: đường dẫn tạm thời mà PHP lưu file upload trên server 
    ├── error: mã trạng thái upload
    └── size: kích thước file

<img width="322" height="16" alt="image" src="https://github.com/user-attachments/assets/8908b113-1976-4868-bbff-0ae98792e89b" />

/tmp/phpABC123
       │
       │ move_uploaded_file()
       ↓
upload/test.jpg


    



