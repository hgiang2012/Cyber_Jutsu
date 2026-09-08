# FILE UPLOAD VULNERABILITIES #

## LAB 



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


    



