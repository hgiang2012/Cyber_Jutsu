# PATH TRAVERSAL VULNERABILITIES #
# 1. LAB

## Level 1:
 <img width="401" height="250" alt="image" src="https://github.com/user-attachments/assets/9e9b6ac5-85d2-4ec6-a699-82f2834989e0" />


<img width="639" height="361" alt="image" src="https://github.com/user-attachments/assets/94276ac6-e506-410e-a2b9-3e5b5b096edb" />

## Level 2:

<img width="343" height="185" alt="image" src="https://github.com/user-attachments/assets/73b35c17-34dc-4cd0-8003-1cce8daa7bef" />

Chương trình chặn sử dụng `..` nên ta sẽ dùng absolute path thay vì relative path 

<img width="738" height="179" alt="image" src="https://github.com/user-attachments/assets/fadcb6c2-7c84-4d1e-a3f0-9c26ec80a33d" />

CBJS{read_file_with_absolute_path}


## Level 3:


<img width="568" height="404" alt="image" src="https://github.com/user-attachments/assets/074c41be-3dad-4769-91cf-94d5afbd0507" />


Ở đây, chương trình sẽ tạo store place cho mỗi use `/var/www/html/upload/' . bin2hex(random_bytes(16)`

```
   for ($i = 0; $i < $count; $i++) {
                
                $newFile = $album . "/" . $files["name"][$i];

                move_uploaded_file($files["tmp_name"][$i], $newFile);
            }
```
Cho phép user upload tập tin vào thư mục `$album` 

<img width="545" height="313" alt="image" src="https://github.com/user-attachments/assets/3905c489-0b2a-4823-92bb-9ad7cbb3ad77" />

Chống thực thi mod-php ở `/var/www/html/upload`

<img width="772" height="112" alt="image" src="https://github.com/user-attachments/assets/5e8db94e-8edb-4018-80fe-4acf88e9bfa9" />

<img width="872" height="65" alt="image" src="https://github.com/user-attachments/assets/989736bc-97c8-4acc-8a4e-6bc73794b9ab" />

Khi ta upload 1 album mới thì được đường dẫn như sau 

`https://pathtraversal.cyberjutsu-lab.tech:8093/upload/b3fea9167412197dcbc4be454a06f03a/12345687/Screenshot%202026-06-19%20175710.png`

<img width="348" height="122" alt="image" src="https://github.com/user-attachments/assets/9afcc4bf-2270-4933-a4f0-e238ef2ea4aa" />

`12345687` được lấy từ giá trị `$_POST['album'] ` khi người dùng nhập vào 
Thử `..` --> ở trang chủ không hiện tên file `..`
Lý do: đường dẫn gốc `var/www/html/upload/b3fea9167412197dcbc4be454a06f03a/12345687`
Sau khi thay bằng `..` thì đã thoát ra khỏi album mà hệ thống tạo cho người dùng và nhảy vào `upload`
mà hệ thống chỉ chống thực thi mod-php ở `/var/www/html/upload`
Vậy nên ta cần upload file php lên `/var/www/html` mà thư mục trang web hiện tại đã trỏ vào `html`

<img width="215" height="148" alt="image" src="https://github.com/user-attachments/assets/caf18f1b-5b6c-40a7-b60a-19765e04dcef" />

<img width="433" height="106" alt="image" src="https://github.com/user-attachments/assets/bc2238dd-348e-4ad5-93fd-63cba1950602" />


<img width="299" height="136" alt="image" src="https://github.com/user-attachments/assets/d69bb76b-7120-41db-82dd-eac62159ab44" />

<img width="652" height="313" alt="image" src="https://github.com/user-attachments/assets/349618ee-073c-42e7-ad48-576f2d6c939a" />
CBJS{file_write_lead_to_RCE_so_simple}

## Level 4:


<img width="630" height="117" alt="image" src="https://github.com/user-attachments/assets/5be43f24-d4b1-45c4-ba1d-9d7d31ddd04f" />

Bất kể file nào thì hệ thống cũng sẽ lưu thành `avatar.jpg`

<img width="959" height="251" alt="image" src="https://github.com/user-attachments/assets/27c86a6a-13b8-4a14-97df-acb5894ef826" />
Test thử request game
<img width="564" height="361" alt="image" src="https://github.com/user-attachments/assets/f8412bec-17fb-4916-8f59-998f66f54d2c" />
Vậy ta có file avatar sẽ lưu ở `var/www/html/upload/{tên user}/avatar.jpg
Và game nằm tại `/var/www/html/game.php`
Vậy ta sẽ có 

<img width="655" height="162" alt="image" src="https://github.com/user-attachments/assets/38de28af-ce75-4b8b-80eb-b76da57d9002" />

<img width="956" height="161" alt="image" src="https://github.com/user-attachments/assets/b13c9b82-b66d-402f-ba63-7b19c429d68e" />

CBJS{LFI+FileUpload=Bomb}

## Level 5:

<img width="467" height="163" alt="image" src="https://github.com/user-attachments/assets/753b74bc-5c62-49c6-9056-7b47e05e2ffd" />

Thử test những file này xem có đọc được không

<img width="959" height="320" alt="image" src="https://github.com/user-attachments/assets/e99a7afc-6963-42ed-b3b3-a8c3df42e91f" />



<img width="959" height="371" alt="image" src="https://github.com/user-attachments/assets/e20a8f07-0dac-4368-a6a8-a67ec50fbe62" />

Ta cần xác 

```
10.10.0.250
[14/Sep/2026:02:06:44 +0000]
"GET /static/img/background_game.jpg HTTP/1.1"
200
38136 "https://pathtraversal.cyberjutsu-lab.tech:8095/?game=fatty-bird-1.html" --> referer 
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/151.0.0.0 Safari/537.36" --> user-agent header
```
--> 1 dòng log như vậy thì mình kiểm soát được bao nhiêu phần, phần nào ?

Dòng 3: có thể kiểm soát

Dòng 6: vì đến từ Referer header của http request 

Dòng 7: dc

--> Request line, Referer header, User-Agent header

<img width="416" height="398" alt="image" src="https://github.com/user-attachments/assets/406027fd-38d8-4a19-8fb6-27e2e8d4ecc0" />

- Dòng 3 có untrusted data là biến `$_GET['game']`
- Dòng 21 biến`$game` được cộng chuỗi với một đường dẫn và đi vào hàm `include`

- `include` sau khi copy nội dung file của file khác vào file hiện tại, sẽ thực thi luôn code php trong đó
--> file `index.php` hiển thị giao diện dựa vào giá trị của tham số GET `game`
--> Cần đưa untrusted data rơi vào trong nội dung của một file có sẵn trên server và ở những điểm có thể inject

  <img width="203" height="219" alt="image" src="https://github.com/user-attachments/assets/b5f1f0fa-a66e-43ce-a675-59eca8ae2a7b" />

- Biến `$game` đã bị prefix bởi `./views/` , để đọc được một file khác trong thư mục, cần sử dụng `../`

<img width="927" height="302" alt="image" src="https://github.com/user-attachments/assets/cef37d0a-fde1-49e3-ae45-7e6e368ded2b" />

- Như đã nói ở trên, `include` sau khi copy nội dung file, nó sẽ thực thi luôn nếu có code PHP trong đó
- Nhưng trang web không có chức năng upload nên cần tìm một file có chức năng ghi lại, và ta có tính năng log

  
- Giá trị mặc định của `${APACHE_LOG_DIR}` là `/var/log/apache2/`
../../../../var/log/apache2/access.log
  <img width="805" height="361" alt="image" src="https://github.com/user-attachments/assets/94dfb897-ff16-4dcf-af77-a659e534780f" />

Gửi  GET request có User-Agent là `<? phpinfo() ?>`
<img width="959" height="467" alt="image" src="https://github.com/user-attachments/assets/fb9f21a6-1545-4ad6-9082-5d0757014cc5" />
- Sau đó, thay `phpinfo()` thành ` system($_GET['cmd'])` và truyền câu lệnh muốn thực thi vào tham số `cmd`
<img width="861" height="316" alt="image" src="https://github.com/user-attachments/assets/a29c38e0-b8b5-445e-a9af-5738b24df952" />



# 2. NOTE

<img width="509" height="170" alt="image" src="https://github.com/user-attachments/assets/8c9e2ac2-d189-446e-a7f9-e7271b74e2e2" />

<img width="388" height="55" alt="image" src="https://github.com/user-attachments/assets/5dac9be1-fe7e-4f97-b41e-c3b6c6b21474" />
- Có 7 thư mục

<img width="248" height="135" alt="image" src="https://github.com/user-attachments/assets/fda4345a-1dd5-470f-a86d-b584776543ee" />
- Về thư mục C:/


<img width="316" height="125" alt="image" src="https://github.com/user-attachments/assets/8364cf3e-320b-4e10-af0d-8be066fbeb70" />


<img width="313" height="174" alt="image" src="https://github.com/user-attachments/assets/229aab1d-b17f-4e55-af62-5cd90d1110d6" />


<img width="296" height="150" alt="image" src="https://github.com/user-attachments/assets/3e9d4ab6-15d6-4172-90ac-83523cee31e4" />

- `readfile($file_path);` là hàm có độ nguy hiểm cao vì nó cho phép đọc toàn bộ nội dung file của tham số đường dẫn được đưa vào


- Untrusted data

<img width="362" height="162" alt="image" src="https://github.com/user-attachments/assets/2fff7019-5406-4334-8d75-188677780b32" />

## Tổng kết lại các lỗi trong bài lab 


