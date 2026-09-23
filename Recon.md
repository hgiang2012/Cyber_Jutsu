# NOTE #

- Captive portal: bug trong các wifi open
- Baseband chip exploit
- Peer-to-peer feature

- Iphone attack surface
+ Malicious HTML page
+ Sending radio signal to compromise iphone
+ Sending documents via AirDrop
+ Sending a malicious gif image



<img width="440" height="220" alt="image" src="https://github.com/user-attachments/assets/e08cd4e5-807b-4918-9197-96ec42391ced" />



-  Tool
+ Amass owasp lấy thông tin từ các third party API: VirusTotal, Github,...
--> Có những third party cần API key, config trong `config.ini`
  `amass enum -d <target> -config config.ini`
- Tìm các param ẩn
- + Gospider đọc source --> ra endpoint có các request param
  + Bruteforce --> tool Arjun
  `arjun -u <target_url>


- Tại sao phải dùng quyền `root` khi chạy nmap
+ Vì nếu chạy normal users, khi dùg tcp connect scan, ứng dụng sẽ ko có quyền tạo raw packet --> không thể modify packet

- 
  
