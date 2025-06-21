# Basic Network Packet Analysis Using Wireshark

### Setup:
1. Use Kali Linux in a VM to run Wireshark
2. Use Wireshark to capture and analyze packets coming from this unsecure website: http://testphp.vulnweb.com/login.php
3. Utilizing sample TCP/HTTP data from the Google Professional Cybersecurity Certificate program to practice analyzing attacks.
---
### Part 1: Capturing Login Info Over HTTP 
In the VM I started up Wireshark to start capturing data and entered the unsecure website, it was a login page in which I typed in the username: admin, and the password: password123. I stopped Wireshark and began to analyze and filter the data.

Due to this website being an unencrypted HTTP website, the username and password I entered in earlier would be able to be seen in plaintext within Wireshark. To get the packet with this information I entered in the following command and followed the HTTP stream.
```sql
http.request.method == "POST"
```

![06879](https://github.com/user-attachments/assets/03d5d595-8143-42cd-b158-91ac65fdbf82)

Some other miscellaneous filters I could use to find other useful traffic are domain, IP source, or port by using the following commands
```sql
dns, ip.src == x.x.x.x, tcp.port == 80
```
---
### Part 2: Analyzing Google Sample Logs

### Overview:
By looking at the logs we can identify a TCP SYN flood DoS attack occurring. We can conclude it's not a DDoS as there are no other IPs besides the one causing the attack. Starting at log 57 we can see that the IP 203.0.113.0 initiates a TCP handshake by sending a SYN packet. However, this three way handshake is never finished. The same IP continues to send more SYN packets in rapid succession in order to overload the server causing it to crash. We see it succeeded in doing this at the 77th log in which it says "HTTP/1.1 504 Gateway Time-out (text/html)" from another IP trying to access the website.

![97678](https://github.com/user-attachments/assets/a26f672e-e212-4767-ab67-082738a73c2e)

---
### Summary:
This project helped me understand how to use Wireshark to analyze real world traffic. I learned how login data can be exposed on unsecure sites and how to spot an attack like SYN flood DoS. These are some of the basic yet important skills needed when working in cybersecurity.
