# WRITE UP

## 1. GET at /register.php with param name


![image](https://github.com/user-attachments/assets/7ccf1c26-46d6-4cd7-a5d8-8bed3f7aff2a)

![image](https://github.com/user-attachments/assets/2b9ab924-9bed-4df9-a769-ee846cb1db95)





## 2 Untrusted Referer
 Đăng nhập xong bấm đăng nhập lại
  
![image](https://github.com/user-attachments/assets/f0270007-2a9f-47f9-a75b-8dcb2f8987df)


## 3 POST at /profile.php with param bio
![image](https://github.com/user-attachments/assets/d929765e-89af-4911-b5a8-60f02242ed12)

![image](https://github.com/user-attachments/assets/82d7dec6-2986-469e-ad0c-55a2a9a31456)


## 4 POST at /sign-up.php with param username
Username: test
Password: '--
![image](https://github.com/user-attachments/assets/fea5159c-0036-4d6c-ade2-927cf9ffc3be)


## 5 POST at /sign-in.php with param username

![image](https://github.com/user-attachments/assets/24880429-cf4c-4f70-b34a-2232ea178b91)


## 6 POST at /sign-in.php with param password
Username: '--
Password: test


![image](https://github.com/user-attachments/assets/587313e3-df7f-4b8d-88c2-23b04bfb4d11)



## 7  GET at /register.php with param email
test
test
![image](https://github.com/user-attachments/assets/da699744-40db-4016-a8b3-7ebbbe7ab31a)

![image](https://github.com/user-attachments/assets/dc2dd183-a7b4-48d0-8a53-92dbbe085b63)


## 8  Hidden feature /premium.php
Dò /track.php?id= để mở feature ẩ

![image](https://github.com/user-attachments/assets/997cf0d1-e3ee-4fd5-819f-f93c023bc894)



![image](https://github.com/user-attachments/assets/527be554-054c-4152-b9b5-b9cdd373dd40)

![image](https://github.com/user-attachments/assets/561cda5c-0f8b-4a39-a800-b0d2a4f6cc4f)

![image](https://github.com/user-attachments/assets/c3fb99b2-fc0b-44c5-afe4-4ed5d0f96271)

![image](https://github.com/user-attachments/assets/ce703108-c128-4d36-a9ee-a050aa2b98a1)



## 9 POST at /sign-up.php with param password
test test

![image](https://github.com/user-attachments/assets/93b91528-3c07-4c08-89f2-603ea473699c)



## 10  POST at /sign-in.php with param username

test
tab tab 

![image](https://github.com/user-attachments/assets/716e3711-4134-42d5-9b1c-cbd2c440e3f4)


## 11 Hidden Path /test.php

test.

![image](https://github.com/user-attachments/assets/126d51bb-555e-4df1-935a-61db4322a713)

## 12 Untrusted File Content 

![image](https://github.com/user-attachments/assets/b500ff73-f1d0-4736-a4db-ff7d98cef76d)


## 13  Untrusted File Name +  14 Untrusted File Content
Upload file test.js

![image](https://github.com/user-attachments/assets/152ffbb3-644c-4938-8631-234919246543)

## 15 Untrusted User-Agent

![image](https://github.com/user-attachments/assets/0610f7ce-672b-46e1-bae6-b2d9d312dc8c)



## 16  Hidden POST param

![image](https://github.com/user-attachments/assets/ce28ffbe-dacc-47e9-9894-5841afcdc110)



## 17 Untrusted File Name
![image](https://github.com/user-attachments/assets/6e282d48-9b57-42e3-a2c0-1826eb90b206)


## 18 File Content Type
![image](https://github.com/user-attachments/assets/a81a6b8a-2fe6-4e82-b7e9-096aea3192c3)


## 19 Cookie 
![image](https://github.com/user-attachments/assets/62ae62cd-8f25-44de-b828-f09bf03e1869)



## 20  Hidden GET param
![image](https://github.com/user-attachments/assets/365ef94b-356b-4971-bbbe-1f68688bae06)




# NOTE 
## 1. Nơi đầu tiên Untrusted Data xuất hiện 
![image](https://github.com/user-attachments/assets/a3b15a59-b6c6-4eb7-b2c6-7aaea6ae3160)

Mảng chứa tham số GET param

## 2 Có bao nhiêu Untrusted Data ở 

<img width="416" height="356" alt="image" src="https://github.com/user-attachments/assets/95841528-7689-4263-b527-3b330a78f2e9" />

3 trường POST và biến cookie

## Tổng kết những untrusted data có trong bài lab trên 
1. GET tại /register.php với param name
2. GET tại /register.php với param email
3. POST tại /sign-up.php với param username
4. POST tại /sign-up.php với param password
5. 
6. Untrusted referer
Header referer có thể bị modify:
`Referer: http://192.168.49.128:12000/register.php?name=test&email=test%40gmail.com`
7. POST tại /profile.php với param tên người dùng
8. POST tại /profile.php với param mật khẩu
9. Modify cookie
10. GET tại register.php với username
11. Hidden feature tại /premium.php
Ta dò tham số /track.php để mở ra feature ẩn
12. POST tại /sign-in.php với param username
13. POST tại /sign-in.php với param password
14. Hidden path
15. Untrusted file content
16. Untrusted file name
17. Modify giá trị user-agent
18. Modifile content trong method POST
19. Modify file name trong repeater
20. Modify file content trong repeater

## Đâu là untrusted data
1. Gói tin HTTP request bởi nội dung có thể bị thay đổi
2. Dữ liệu người dùng
3. Dữ liệu từ máy chủ khác vì dữ liệu có thể bị thay đổi hoặc chưa được xử lý an toàn trước khi được gửi
