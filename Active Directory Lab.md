# Active Directory Lab

### Setup:
1. Create two VMs, one being Windows 2022 to host AD and the other being Windows 11 Enterprise to host Workstation01.
2. Promote the server to a domain controller, root domain name is "corp.local".
3. Creating OUs for IT, HR, and Finance departments as well as a workstations OU.
4. Create some users to add to each OU.
<img width="1018" height="793" alt="ad lab 03" src="https://github.com/user-attachments/assets/e9564d62-e4c7-44c4-a64b-999607951122" />
<img width="1026" height="783" alt="ad lab 04" src="https://github.com/user-attachments/assets/ee2762df-2dcd-46f8-acd8-a0dc5d529a6c" />

---
### Creating Group Policies to improve security

Password Policies: To increase security I will create password polices that will set a minimum password length, a maximum password age, and how many password attempts until the account is locked out.

<img width="420" height="505" alt="ad lab 08" src="https://github.com/user-attachments/assets/4225bd44-6dd4-486e-8e4a-9e8c7cfd73bc" />
<img width="413" height="497" alt="ad lab 10" src="https://github.com/user-attachments/assets/9bcc7ec7-a93a-4538-98b6-c2db96e41605" />
<img width="412" height="508" alt="ad lab 26" src="https://github.com/user-attachments/assets/3c979f15-0e00-41e9-b721-27f206cbc421" />

Lock Screen Policy: If a workstation is inactive for 15 minutes, the machine will lock out.

<img width="413" height="505" alt="ad lab 13" src="https://github.com/user-attachments/assets/f3263ac8-3bed-45fd-ade4-ae3bce630f18" />

Disable USB storage: Deny access when a USB is connected.

<img width="527" height="179" alt="ad lab 14" src="https://github.com/user-attachments/assets/df35b39d-3165-4cd5-9e64-a25223b3bdb0" />

