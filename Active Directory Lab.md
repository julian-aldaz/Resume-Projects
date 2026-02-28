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

---
### Scenarios

Scenario 1: Adam forgot his password and attempted too many password attempts and locked himself out, unlock his account using AD.

<img width="1013" height="760" alt="ad lab 17" src="https://github.com/user-attachments/assets/61853aa6-f295-4f90-92b7-f13af631e210" />

<img width="425" height="533" alt="ad lab 18" src="https://github.com/user-attachments/assets/81ea8362-2447-4e6a-9f93-243d9444913c" />

Scenario 2: Nathan Botello is a new employee in the HR department who needs to be added to AD. Add him and show a successful login.

<img width="1013" height="756" alt="ad lab 22" src="https://github.com/user-attachments/assets/f4ab680b-365a-4028-9286-1570a45a98c0" />
<img width="1014" height="816" alt="ad lab 24" src="https://github.com/user-attachments/assets/d4e4bee5-5d98-4cbc-8798-8db4300e3523" />

Sceanrio 3: Employee is being offboarded, we need to disable the account, not delete yet.

<img width="1017" height="760" alt="ad lab 27" src="https://github.com/user-attachments/assets/c014242e-d78a-4911-928d-8c80d9b5ae84" />
<img width="1022" height="767" alt="ad lab 28" src="https://github.com/user-attachments/assets/8170e5e9-182a-49ae-9b6b-572000be5577" />

Scenario 4: Create and share a folder for the IT admins to view but deny access to everyone else.
<img width="1018" height="770" alt="ad lab 32" src="https://github.com/user-attachments/assets/dce6b853-f830-403b-ac64-6d923e222f99" />

The IT folder is able to be viewed by everyone on the network.
<img width="1015" height="771" alt="ad lab 29" src="https://github.com/user-attachments/assets/7e1a89e6-f468-4a32-b443-aa92e55f7168" />

When someone from HR tries to open the folder they are denied access.
<img width="1028" height="727" alt="ad lab 30" src="https://github.com/user-attachments/assets/4836d5a2-b625-42c8-bb5b-e7022a1b324c" />

When someone from IT admins group is signed in they are able to see the contents inside the folder.
<img width="799" height="586" alt="ad lab 31" src="https://github.com/user-attachments/assets/54c0cba5-0177-4c7d-950e-83fb5fd634d2" />
