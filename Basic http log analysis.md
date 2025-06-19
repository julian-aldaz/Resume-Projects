# Resume Project: Basic Proficiency in Splunk Cloud

### Setup:
1. Using Splunk Cloud to analyize HTTP logs
2. Using this json file that has HTTP sample logs: https://raw.githubusercontent.com/0xrajneesh/30-Days-SOC-Challenge-Beginner/refs/heads/main/http_logs.json
3. Adding the data to Splunk Cloud and create new index: http_project
---
### Using Splunk Queries Tasks:

### Task 1: Sort log data to find the endpoints generating the most traffic:
```sql
index="http_project" | stats count by "id.orig_h" | sort -count
```
Output:

![task 1](https://github.com/user-attachments/assets/4092414f-9d6e-4cff-a3dd-9664a00b8677)

### Task 2: Find all failed HTTP requests from users with Windows based browsers:
```sql
index="http_project" status_code>="400" AND user_agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64)"
```
Output: 

![98755](https://github.com/user-attachments/assets/40703948-ea24-4568-b60e-a5d9cf9f5512)

### Task 3: Search by user-agents possibly associated with scripted attacks:
```sql
index="http_project" user_agent IN ("sqlmap/1.5.1", "curl/7.68.0", "python-requests/2.25.1", "botnet-checker/1.0") | stats count by user_agent
```
Output:

![05576](https://github.com/user-attachments/assets/13341932-8e0f-4ad2-9ee4-40ed35760f91)

### Task 4: Find all file transfers greater than 500KB
```sql
index="http_project" resp_body_len>500000 | table "ts" "id.orig_h" "id.resp_h" "uri" "resp_body_len" | sort -resp_body_len
```
Output:

![96556](https://github.com/user-attachments/assets/68204e69-3e5e-4f94-a3ae-d73263cf9e8e)

---
### Quick Dashboard to show all queries together:

![http_project_2025-06-16 at 12 05 05-0700_Splunk](https://github.com/user-attachments/assets/d0e23482-5afc-4ccc-a538-080fad877c51)

---
### Summary:

In this project, I used Splunk Cloud to practice analyzing HTTP log data and ran a few basic security focused searches. First, I created a custom index and loaded in sample JSON logs. Then I wrote SPL queries to dig into the data and find things that could matter in a real world scenario. Task 1 helped me see which IP addresses (id_orig_h) were generating the most traffic, which could point to scanners or just really active users. Task 2 filtered out failed HTTP requests (status code 400 and above) from Windows based browsers. This could help spot misconfigured clients or even early signs of automated attacks. Task 3 looked for user-agents linked to tools like sqlmap or curl, which are often used in scripted or malicious activity. Task 4 showed all the large file transfers over 500KB. That’s useful for finding possible data exfiltration or big file downloads. Overall, this project gave me hands-on experience using Splunk’s search language (SPL), creating indexes, and looking at logs from a security analyst’s point of view. It was a good intro to log analysis and threat detection using Splunk Cloud.
