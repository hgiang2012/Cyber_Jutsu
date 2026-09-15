## COMMAND INJECTION ##

# LAB #

# 1. 
Sử dụng `;` để nối chuỗi
<img width="433" height="233" alt="image" src="https://github.com/user-attachments/assets/d6389772-aeea-4f92-a519-c41362771582" />

<img width="370" height="155" alt="image" src="https://github.com/user-attachments/assets/6daf353b-6739-49b1-942a-9e724e31c0ea" />
--> Command after `;` can excute
<img width="464" height="442" alt="image" src="https://github.com/user-attachments/assets/00f5cdff-e318-47d9-bc2c-d233f54c9bb9" />

<img width="463" height="277" alt="image" src="https://github.com/user-attachments/assets/4a497502-ea83-428e-a56f-e117c70fc6c2" />

CBJS{Basic_Command_Injection_0b4df8ed64f424432facd35e16883402}

# 2. 
<img width="515" height="107" alt="image" src="https://github.com/user-attachments/assets/328179f0-1204-4efe-8857-d7100b5debfb" />
Cant use `;` anymore but wat if we use `||`. This syntax is only executed when the first command fails

<img width="473" height="266" alt="image" src="https://github.com/user-attachments/assets/7125ff5a-30c2-45b2-bf66-e3f4274b7fc9" />

<img width="400" height="220" alt="image" src="https://github.com/user-attachments/assets/63be0053-8417-4bc3-ade5-5c3c18190e63" />

<img width="448" height="344" alt="image" src="https://github.com/user-attachments/assets/8c2a115f-9ae9-4ace-ada8-c8e7ee0db184" />

<img width="458" height="268" alt="image" src="https://github.com/user-attachments/assets/9f962a59-c76d-4fec-8457-cfb3b9d90c4f" />

CBJS{Command_Injection_Dont_need_semicolon_763d036657127a4f21c670530e319b52}


# 3. 

<img width="590" height="356" alt="image" src="https://github.com/user-attachments/assets/ffe89aae-42fe-41c6-943b-00cd6985bcb5" />

Nhưng ngoại trừ những kí tự trên, ta còn có thể sử dụng newliine

<img width="775" height="223" alt="image" src="https://github.com/user-attachments/assets/7d536ae9-9d17-4dda-9591-a77fd7d2181b" />

Chuyển newline sang dạng hex

<img width="721" height="312" alt="image" src="https://github.com/user-attachments/assets/b632e311-32d2-4e8f-8b3f-0928a6b9d63e" />

<img width="701" height="212" alt="image" src="https://github.com/user-attachments/assets/615228fe-84b6-4fa9-8550-c07117657e63" />

CBJS{Not_only_;&|_but_there_are_mor_520c298589c33766dc2688b3866c95cb}

- Cách khác sử dụng commmand sub

<img width="597" height="138" alt="image" src="https://github.com/user-attachments/assets/c10aae76-e21a-4644-b05f-7367e18ade66" />

<img width="717" height="220" alt="image" src="https://github.com/user-attachments/assets/26d474d6-c01a-4121-9807-585b5780cbcc" />

<img width="710" height="149" alt="image" src="https://github.com/user-attachments/assets/8a3365d1-ac70-4dba-8e21-6768d7565e51" />

'CBJS{Not_only_;&|_but_there_are_mor_520c298589c33766dc2688b3866c95cb}' is not a legal name (label too long)

# 4.

<img width="698" height="469" alt="image" src="https://github.com/user-attachments/assets/edb03662-6cdf-4a8b-9dc0-b35502951ca1" />

Chỉ có thể sử dụng chức năng backup

`$_POST['target']` có thể là điểm inject vì được gán thẳng vào `$result = shell_exec("timeout 3 zip /tmp/$target -r /var/www/html/index.php 2>&1");`

Chương trình lấy file `/var/www/html/index.php` nén thành zip và lưu tại /tmp/$target

Lưu ý là chương trình ko có flter kí 

Đọc flag xong sẽ dùng lệnh `curl` để bắn nội dung flag ra bên ngoài sv ( webhook )

CÁC BƯỚC TRONG BÀI LAB NÀY
1. Cần 1 host HTTP ở ngoài internet để bắt lấy gói tin chứa flag
2. Exploit OS Command Injection, ghi output của command ra /tmp/pwned.txt
3. Vẫn dùng OS Command Injection để gửi /tmp/pwned.txt bằng CURL tới địa chỉ webhook.site
4. Nhận được flag từ webhook

<img width="489" height="279" alt="image" src="https://github.com/user-attachments/assets/f45e187c-599b-4607-a734-be7212c56772" />


<img width="959" height="431" alt="image" src="https://github.com/user-attachments/assets/73df4b67-9718-4e62-9f6c-51b89eba4dab" />

<img width="479" height="265" alt="image" src="https://github.com/user-attachments/assets/ad5c8672-1661-4f33-a425-f2302ebb45dc" />

<img width="959" height="356" alt="image" src="https://github.com/user-attachments/assets/f338c4dc-f9e5-45cf-9087-ae672872e9ca" />

<img width="469" height="242" alt="image" src="https://github.com/user-attachments/assets/2a416ee1-38d3-4e8a-8fd1-68ccea68e04e" />


CBJS{Blind_Command_Injection_a3183b33bb4885bbd0c9ddfe20c35ab8}

# 5

<img width="508" height="149" alt="image" src="https://github.com/user-attachments/assets/e25aceca-227c-4ed0-a360-077fda8343a2" />

Ở level này, ta không gửi gói tin ra ngoài được nữa
Cần kiểm tra xem ta có thể ghi file vào /var/www/html không? Thư mục có quyền ghi không
Có 2 cách:
C1: Write shell vào DocumentRoot rồi bla bla
C2: Write FLAG vào DocumentRoot rồi đọc từ http://../flag.

<img width="426" height="197" alt="image" src="https://github.com/user-attachments/assets/af64e6ea-0aa2-4e56-addd-3de86427b37c" />

<img width="386" height="62" alt="image" src="https://github.com/user-attachments/assets/8974ac9c-9035-4572-ae19-aa17e29b13e4" />

<img width="959" height="344" alt="image" src="https://github.com/user-attachments/assets/79a61a64-186b-4748-9bff-fa004620db1a" />

<img width="959" height="314" alt="image" src="https://github.com/user-attachments/assets/5c1501d5-6990-4134-a234-e803a0ed05d4" />

CBJS{n0_1nternet_command_injection_dbf02a0e608f8b08d5a23591a47ff36b}

# 6

<img width="455" height="126" alt="image" src="https://github.com/user-attachments/assets/aae6a701-2c73-40df-9651-607a2543dcef" />

Đến level này ta không còn có thể ghi đè vào DocumentRoot nữa





# NOTE #
Tài liệu

https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_03_03.html 

https://tldp.org/LDP/abs/html/special-chars.html 

https://www.gnu.org/software/bash/manual/html_node/Lists.html 

https://www.gnu.org/software/bash/manual/html_node/index.html#SEC_Contents 

https://www.gnu.org/software/bash/manual/html_node/Command-Substitution.html 


