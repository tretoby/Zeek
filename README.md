# Zeek Analysis Project

## Objective

This project utilizes Zeek to analyze DNS tunneling traffic, identify anomalies, and filter log files for actionable insights. The objectives include:  
1. Confirming a DNS tunneling alert as a true positive.  
2. Investigating connection logs to find the longest connection.  
3. Extracting and analyzing unique DNS queries to uncover potential security risks.

---

## Skills Learned

- **PCAP Analysis**: Interpreting and extracting meaningful data from packet capture files.  
- **Log Investigation**: Navigating, filtering, and analyzing Zeek-generated log files.  
- **Command-Line Proficiency**: Utilizing commands to process large datasets efficiently.  
- **DNS Record Analysis**: Identifying DNS anomalies and understanding query patterns.  
- **Data Filtering and Sorting**: Using tools like `uniq`, `sort`, and `awk` to refine data.  
- **Problem-Solving**: Isolating critical information from complex logs.  
- **Reporting**: Drawing conclusions from log analysis and presenting findings clearly.

---

## Analysis Steps

### Objective 1.1 - Confirm DNS Tunneling Alert as True Positive

**Steps:**  

1. Investigate the `dns-tunneling.pcap` file and the `dns.log` file to find the number of DNS records linked to the IPv6 address.  
2. Change the directory to `Exercise-files`.  
   ![image](https://github.com/user-attachments/assets/eab8220f-0e1f-48e7-b36e-e5723d1d7ef2)  

3. Navigate to the `anomalous-dns` directory.  
   ![image](https://github.com/user-attachments/assets/05f1a153-7f11-480a-8b7f-1eafa44df369)  

4. Identify the `dns-tunneling.pcap` file.  
   ![image](https://github.com/user-attachments/assets/83045ff9-5115-444a-863d-8546ff0a3b1f)  

5. Analyze the packet with Zeek, which generates log files.  
   ![image](https://github.com/user-attachments/assets/7f56d16b-5b31-41e3-86e0-74cb6f60be63)  
   ![image](https://github.com/user-attachments/assets/4eff8c76-2845-44e5-a7d1-d84c8c94e80d)  

6. Extract the first 10 lines of the `dns.log` file to inspect.  
   ![image](https://github.com/user-attachments/assets/332e1421-e9bf-4a96-a291-0b9bb02bad92)  

7. Narrow down the field information from `qtype_name`.  
   ![image](https://github.com/user-attachments/assets/8219f3e8-8ae8-4c21-a70f-0b7b082f594e)  

8. Further refine results, revealing 320 `AAAA` records associated with the IPv6 address.  
   ![image](https://github.com/user-attachments/assets/344d8f96-9984-4ba1-bf51-fa80832dce5b)  

---

### Objective 1.2 - Investigate Connection Logs for Longest Connection

**Steps:**  

1. Examine the `conn.log` file.  
   ![image](https://github.com/user-attachments/assets/a4470117-6911-4695-bb37-cdb7e3cdac53)  

2. Filter for service duration and identify the longest connection at 9.420791 seconds.  
   ![image](https://github.com/user-attachments/assets/7befdddf-3d86-42c2-9fd4-5c6a9fda3d47)  

---

### Objective 1.3 - Extract and Analyze Unique DNS Queries

**Steps:**  

1. Extract the first 10 lines of the `dns.log` file.  
   ![image](https://github.com/user-attachments/assets/38701ace-93b1-474f-8501-c8570ada80ad)  

2. Filter for DNS query domains.  
   ![image](https://github.com/user-attachments/assets/1e8a707d-c9ef-4b52-b860-51b9eb96e2a6)  

3. Narrow the results by focusing on Cisco-update-related queries.  
   ![image](https://github.com/user-attachments/assets/b73441e3-1ae2-4056-a728-ab3854d483e2)  

4. Further refine to extract unique domain names, revealing six different queries.  
   ![image](https://github.com/user-attachments/assets/918f60ff-d14f-45d3-ba95-8797fb65fe7f)  

---

## Conclusion

This project demonstrates the power of Zeek in network analysis by confirming a DNS tunneling alert, uncovering the longest connection from logs, and analyzing unique DNS queries. These findings highlight the effectiveness of Zeek in identifying network anomalies and processing large datasets. Through detailed analysis and filtering, critical information was extracted to provide actionable insights into potential security risks. This exercise emphasizes the importance of tools like Zeek in cybersecurity workflows, equipping analysts to detect and respond to threats efficiently.













































