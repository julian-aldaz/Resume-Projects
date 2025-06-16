# Splunk Lab: Resume project to show basic proficiency in Splunk Cloud

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


