# Splunk Lab: Resume project to show basic proficiency in Splunk Cloud

### Setup:
1. Using Splunk Cloud to analyize HTTP logs
2. Using this json file that has HTTP sample logs: https://raw.githubusercontent.com/0xrajneesh/30-Days-SOC-Challenge-Beginner/refs/heads/main/http_logs.json
3. Adding the data to Splunk Cloud and create new index: http_project
---
Using Splunk Queries Tasks:

### Task 1: Sort log data to find the endpoints generating the most traffic:
```sql
index="http_project" | stats count by "id.orig_h"
```
