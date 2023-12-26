# **Network Intrusion Detection System**

## **Business Objective**

With the enormous growth of computer networks usage and the huge increase in the number of applications running on top of it, network security is becoming increasingly more important. All the computer systems suffer from security vulnerabilities which are both technically difficult and economically costly to be solved by the manufacturers. Therefore, the role of Intrusion Detection Systems (IDSs), as special-purpose devices to detect anomalies and attacks in the network, is becoming more important.

The research in the intrusion detection field has been mostly focused on anomaly-based and misuse-based detection techniques for a long time. While misuse-based detection is generally favored in commercial products due to its predictability and high accuracy, in academic research anomaly detection is typically conceived as a more powerful method due to its theoretical potential for addressing novel attacks.

As part of this project, we will build a network intrusion detection system to detect anomalies and attacks in the network.

## **Problems**

1. **Binomial Classification:** Detect anomalies by predicting Activity is normal or attack.
2. **Multinomial Classification:** Detecting the type of activity by predicting Activity is Normal or Back or Buffer Overflow or FTP Write or Guess Password or Neptune or N-Map or Port Sweep or Root Kit or Satan or Smurf.

## Available Data

The organization captured data over time for different types of attacks and provided the data in different files for different types of activities along with normal.

### Tables

There are 10 tables for different types of attacks with the same columns:

- Data_of_Attack_Back_Normal
- Data_of_Attack_Back
- Data_of_Attack_Back_BufferOverflow
- Data_of_Attack_Back_FTPWrite
- Data_of_Attack_Back_GuessPassword
- Data_of_Attack_Back_Neptune
- Data_of_Attack_Back_NMap
- Data_of_Attack_Back_PortSweep
- Data_of_Attack_Back_RootKit
- Data_of_Attack_Back_Satan
- Data_of_Attack_Back_Smurf

### Basic Features of Each Network Connection Vector

1. **Duration:** Length of the time duration of the connection
2. **Protocol_type:** Protocol used in the connection
3. **Service:** Destination network service used
4. **Flag:** Status of the connection –Normal or Error
5. **Src_bytes:** Number of data bytes transferred from source to destination in a single connection
6. **Dst_bytes:** Number of data bytes transferred from destination to source in a single connection
7. **Land:** If source and destination IP addresses and port numbers are equal then, this variable takes value 1 else 0
8. **Wrong_fragment:** Total number of wrong fragments in this connection
9. **Urgent:** Number of urgent packets in this connection. Urgent packets are packets with the urgent bit activated

### Content Related Features of Each Network Connection Vector

10. **Hot:** Number of "hot" indicators in the content such as: entering a system directory, creating programs, and executing programs
11. **Num_failed_logins:** Count of failed login attempts
12. **Logged_in Login Status:** 1 if successfully logged in; 0 otherwise
13. **Num_compromised:** Number of "compromised" conditions
14. **Root_shell:** 1 if root shell is obtained; 0 otherwise
15. **Su_attempted:** 1 if "su root" command attempted or used; 0 otherwise
16. **Num_root:** Number of "root" accesses or number of operations performed as a root in the connection
17. **Num_file_creations:** Number of file creation operations in the connection
18. **Num_shells:** Number of shell prompts
19. **Num_access_files:** Number of operations on access control files
20. **Num_outbound_cmds:** Number of outbound commands in an FTP session
21. **Is_hot_login:** 1 if the login belongs to the "hot" list i.e., root or admin; else 0
22. **Is_guest_login:** 1 if the login is a "guest" login; 0 otherwise

### Time Related Traffic Features of Each Network Connection Vector

23. **Count:** Number of connections to the same destination host as the current connection in the past two seconds
24. **Srv_count:** Number of connections to the same service (port number) as the current connection in the past two seconds
25. **Serror_rate:** The percentage of connections that have activated the flag (4) s0, s1, s2, or s3, among the connections aggregated in count (23)
26. **Srv_serror_rate:** The percentage of connections that have activated the flag (4) s0, s1, s2, or s3, among the connections aggregated in srv_count (24)
27. **Rerror_rate:** The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in count (23)
28. **Srv_rerror_rate:** The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in srv_count (24)
29. **Same_srv_rate:** The percentage of connections that were to the same service, among the connections aggregated in count (23)
30. **Diff_srv_rate:** The percentage of connections that were to different services, among the connections aggregated in count (23)
31. **Srv_diff_host_rate:** The percentage of connections that were to different destination machines among the connections aggregated in srv_count (24)

### Host-Based Traffic Features in a Network Connection Vector

32. **Dst_host_count:** Number of connections having the same destination host IP address
33. **Dst_host_srv_count:** Number of connections having the same port number
34. **Dst_host_same_srv_rate:** The percentage of connections that were to the same service, among the connections aggregated in dst_host_count (32)
35. **Dst_host_diff_srv_rate:** The percentage of connections that were to different services, among the connections aggregated in dst_host_count (32)
36. **Dst_host_same_src_port_rate:** The percentage of connections that were to the same source port, among the connections aggregated in dst_host_srv_count (33)
37. **Dst_host_srv_diff_host_rate:** The percentage of connections that were to different destination machines, among the connections aggregated in dst_host_srv_count (33)
38. **Dst_host_serror_rate:** The percentage of connections that have activated the flag (4) s0, s1, s2, or s3, among the connections aggregated in dst_host_count (32)
39. **Dst_host_srv_serror_rate:** The percent of connections that have activated the flag (4) s0, s1, s2, or s3, among the connections aggregated in dst_host_srv_count (33)
40. **Dst_host_rerror_rate:** The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in dst_host_count (32)
41. **Dst_host_srv_rerror_rate:** The percentage of connections that have activated the flag (4) REJ, among the connections aggregated in dst_host_srv_count (33)

### Type Features

- **Nominal:** Protocol_type(2), Service(3), Flag(4)
- **Binary:** Land(7), logged_in(12), root_shell(14), su_attempted(15), is_host_login(21), is_guest_login(22)
- **Numeric:** Duration(1), src_bytes(5), dst_bytes(6), wrong_fragment(8), urgent(9), hot(10), num_failed_logins(11), num_compromised(13), num_root(16), num_file_creations(17), num_shells(18), num_access_files(19), num_outbound_cmds(20), count(23), srv_count(24), error_rate(25), srv_serror_rate(26), rerror_rate(27), srv_rerror_rate(28), same_srv_rate(29), diff_srv_rate(30), srv_diff_host_rate(31), dst_host_count(32), dst_host_srv_count(33), dst_host_same_srv_rate(34), dst_host_diff_srv_rate(35), dst_host_same_src_port_rate(36), dst_host_srv_diff_host_rate(37), dst_host_serror_rate(38), dst_host_srv_serror_rate(39), dst_host_rerror_rate(40), dst_host_srv_rerror_rate(41)

For Binomial classification,  create an attack variable with attack vs. normal. For Multinomial classification, create an attack variable with normal vs. Back vs. Buffer Overflow vs. FTP Write vs. Guess Password vs. Neptune vs. N-Map vs. Port Sweep vs. Root Kit vs. Satan vs. Smurf.
