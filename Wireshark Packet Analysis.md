# Basic Network Packet Analysis Using Wireshark

### Setup:
1. Use Kali Linux in a VM to use Wireshark
2. Use Wireshark to analyze packets coming from this unsecure website: http://testphp.vulnweb.com/login.php
3. Utilizing sample TCP/HTTP data from the Google Professional Cybersecurity Certificate program to report findings.
---
### Overview: 
In the VM I started up Wireshark to start capturing data and entered the unsecure website, it was a login page in which I enter the username: admin, and the password: password123. I stopped Wireshark and began to analyze and filter the data.

Due to this website being an unecrypted HTTP website, the username and password I entered in earlier would be able to be seen in plaintext within Wireshark. To get the packet with this information I entered in the following command and followed the HTTP stream.
```sql
http.request.method == "POST"
```

![06879](https://github.com/user-attachments/assets/03d5d595-8143-42cd-b158-91ac65fdbf82)

I could also filter by other factors such as domain, IP source, or port using the following commands
```sql
dns, ip.src == x.x.x.x, tcp.port == 80
```
---
### Sample Log Analysis From Google Certificate:

![97678](https://github.com/user-attachments/assets/a26f672e-e212-4767-ab67-082738a73c2e)
