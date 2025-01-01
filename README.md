#          Google Labs   
#  PASTA worksheet exemplar 

### Importance of the PASTA Methodology

See Details
<details>
  <summary>Click to expand</summary>
  

The PASTA (Process for Attack Simulation and Threat Analysis) methodology, as demonstrated in this worksheet, is important for several reasons:

*   **Structured Approach:** It provides a systematic and repeatable process for security analysis, ensuring that all aspects of the application are considered.
*   **Proactive Security:** By identifying threats and vulnerabilities *before* they can be exploited, it enables proactive security measures, reducing the likelihood and impact of successful attacks.
*   **Risk-Based Approach:** It focuses on analyzing risks and their potential impact on the business, allowing for prioritization of security controls based on business needs.
*   **Improved Communication:** The visual diagrams (data flow and attack tree) facilitate communication and understanding of security risks among technical and non-technical stakeholders.
*   **Compliance:** It helps organizations meet compliance requirements, such as PCI-DSS, by demonstrating a structured approach to security assessment.
*   **Comprehensive Coverage:** By covering all stages from defining objectives to implementing controls, it ensures that security is considered throughout the application's lifecycle.

In summary, this PASTA worksheet demonstrates a valuable methodology for identifying, analyzing, and mitigating security risks in applications. It's a crucial tool for building secure systems and protecting sensitive information.

</details>

[View my lab(PDF)](https://docs.google.com/document/d/1RdqmR63vrr6zQLHcyatlzZdnCD9LuEcRCsVzEAB6CJU/edit?usp=sharing)


## Python Algorithm for File Updates (IP Address Filtering)

See Details
<details>
  <summary>Click to expand</summary>

This project describes the development of a Python algorithm designed to filter IP addresses from an allow list file. The algorithm efficiently identifies and removes IP addresses that are no longer authorized to access restricted content.

**Key Steps of the Algorithm:**

1.  **Open the allow list file:** The script opens the file containing the authorized IP addresses using Python's `open()` function and the `with` statement for proper file handling.
2.  **Read file contents:** The contents of the allow list file are read into memory, typically as a string, using the `.read()` method.
3.  **Convert to a list:** The string of IP addresses is converted into a Python list, likely using the `.split()` method to separate IP addresses based on a delimiter (e.g., newline characters).
4.  **Iterate through the remove list:** The script uses a `for` loop to iterate through each IP address in the "remove list."
5.  **Remove matching IPs:** An `if` statement checks if each IP from the remove list exists within the allow list. If a match is found, the IP address is removed from the allow list.
6.  **Update the file:** The updated allow list (now without the removed IPs) is written back to the original file, overwriting its previous contents, using the `.write()` method.

**Importance of This Algorithm:**

This algorithm is crucial for several reasons, particularly in a cybersecurity context:

*   **Access Control:** Allow lists are a fundamental security mechanism for controlling access to resources. This algorithm ensures that only authorized IP addresses can access restricted content or systems.
*   **Automation:** Automating the allow list updating process is essential for efficiency and accuracy, reducing the risk of human error associated with manual edits.
*   **Security Automation and Orchestration (SOAR):** This type of algorithm is often a component of SOAR systems, enabling automated responses to security events.
*   **Dynamic Updates:** The algorithm facilitates dynamic updates to the allow list, allowing for rapid adjustments to access permissions as needed.
*   **Reduced Attack Surface:** By promptly removing unauthorized IP addresses, the algorithm minimizes the risk of unauthorized access and potential attacks.
*   **Maintainability and Scalability:** Using Python and a structured algorithm makes the process easily maintainable and scalable to handle large allow lists and frequent updates.

**Summary of Python Concepts Used:**

*   **File Handling:**
    *   `with` statement: Ensures proper file opening and closing.
    *   `open()` function: Opens files for reading (`"r"`) or writing (`"w"`).
    *   `.read()` method: Reads file contents.
    *   `.write()` method: Writes content to a file.
*   **Data Structures and Control Flow:**
    *   `for` loop: Iterates over lists.
    *   `if` statement: Conditional execution.
    *   `.split()` method: Converts strings to lists.
*   **Functions:** Algorithms can be encapsulated within functions for reusability and modularity.

In conclusion, this project demonstrates a practical application of Python for automating a key security task. It emphasizes the importance of efficient and accurate allow list management for robust access control and a strengthened security posture.

</details>

[View my lab(PDF)](https://docs.google.com/document/d/1XC9zey30RKyeclrGuJmXxkIaQszEcdrpLvxTR9Cj9gg/edit?tab=t.0)


#  Apply filters to SQL queries

See Details
<details>
  <summary>Click to expand</summary>

  ## Applying Filters to SQL Queries for Cybersecurity Analysis

This project demonstrates proficiency in constructing and executing SQL queries to filter and extract specific data, with a focus on applications relevant to cybersecurity analysis. It showcases the use of various SQL clauses, operators, and functions to retrieve targeted information based on diverse criteria.

**Key Operations Demonstrated:**

*   **Retrieving After-Hours Failed Login Attempts:** This demonstrates time-based filtering (using `WHERE` clauses with time comparison operators like `>`, `<`, and `=`) to pinpoint suspicious login activity outside of normal business hours. Example:

    ```sql
    SELECT * FROM LoginAttempts WHERE LoginTime < '18:00:00' AND LoginStatus = 'Failed';
    ```

*   **Retrieving Login Attempts on Specific Dates:** This showcases filtering based on date ranges (using `BETWEEN` or comparison operators with dates) to isolate login attempts within a specific timeframe, crucial for incident investigation. Example:

    ```sql
    SELECT * FROM LoginAttempts WHERE LoginTime BETWEEN '2024-03-10' AND '2024-03-12';
    ```

*   **Retrieving Login Attempts Outside of a Specific Location (e.g., Mexico):** This demonstrates using the `NOT` operator and wildcard characters (e.g., `%`) in `WHERE` clauses to exclude data based on location or other string patterns. Example:

    ```sql
    SELECT * FROM LoginAttempts WHERE NOT Location LIKE 'MEX%';
    ```

*   **Retrieving Employees in Specific Departments (e.g., Marketing, Finance, Sales, excluding IT):** This showcases filtering based on categorical data (department names) using `WHERE` clauses with `=`, `OR`, and `NOT` operators. Examples:

    ```sql
    -- Marketing Employees
    SELECT * FROM Employees WHERE Department = 'Marketing';

    -- Finance OR Sales Employees
    SELECT * FROM Employees WHERE Department = 'Finance' OR Department = 'Sales';

    -- Employees NOT in IT
    SELECT * FROM Employees WHERE NOT Department = 'IT';
    ```

**Importance of SQL Filtering for Cybersecurity:**

SQL filtering is a critical skill for cybersecurity analysts due to its applications in:

*   **Incident Investigation:** Quickly narrow down large log datasets based on specific criteria (timestamps, user IDs, IP addresses, event types) to identify relevant events.
*   **Threat Hunting:** Proactively search for indicators of compromise (IOCs) within system logs and other data sources using pattern matching and filtering.
*   **Security Auditing:** Audit database configurations and access controls to identify users with excessive privileges or misconfigurations.
*   **Compliance Reporting:** Extract necessary data for compliance reports (e.g., PCI-DSS, HIPAA) by filtering based on regulatory requirements.
*   **Data Analysis and Trend Identification:** Identify trends and patterns in security events to predict future attacks or uncover systemic weaknesses.
*   **Efficient Data Extraction:** Extract specific data efficiently, avoiding manual review of extensive datasets.

**Summary of SQL Concepts Demonstrated:**

This project highlights the importance of logical operators (`NOT`, `AND`, `OR`), comparison operators (`=`, `>`, `<`, `BETWEEN`, `LIKE`), and the `WHERE` clause in SQL. These elements are essential for creating precise filters and extracting relevant information. The ability to filter data based on various parameters is crucial for:

*   Conducting thorough incident investigations.
*   Identifying emerging threats.
*   Developing data-driven risk mitigation strategies.

This project demonstrates the practical application of SQL skills in a cybersecurity context, showing how effective data filtering provides valuable insights for security analysis and informed decision-making.

</details>

[View my lab(PDF)](https://docs.google.com/document/d/1QHnoZ4T-RV0SVVCC5t68zwe2wRakQqm90U_CLnSMiAU/edit?usp=sharing)


# Controls and compliance checklist

See Details
<details>
  <summary>Click to expand</summary>

  ## Importance of Controls and Compliance Checklists

These checklists and the associated recommendations are crucial for establishing and maintaining a robust security posture for any organization. They serve as a foundational tool for assessing current security practices, identifying vulnerabilities, and ensuring adherence to relevant industry standards and regulations.

**Why are these checklists important?**

*   **Baseline Security Assessment:** The controls checklist provides a structured way to evaluate the implementation of fundamental security controls. This assessment helps organizations understand their current security posture and identify areas of weakness. By systematically checking for the presence of controls like least privilege, password policies, and intrusion detection systems, organizations can gain a clear picture of their security strengths and weaknesses.
*   **Compliance with Standards and Regulations:** The compliance checklist ensures adherence to crucial industry standards and regulations such as PCI DSS, GDPR, and SOC. Meeting these requirements is not only essential for avoiding legal penalties and reputational damage but also demonstrates a commitment to data protection and security best practices.
*   **Identification of Security Gaps:** By systematically checking for the presence and effectiveness of security controls and comparing them against compliance requirements, these checklists help identify critical security gaps. This allows organizations to proactively address vulnerabilities before they can be exploited by attackers.
*   **Guidance for Security Improvements:** The recommendations section provides actionable steps for improving the organization's security posture. These recommendations are based on industry best practices and address the identified security gaps, providing a roadmap for implementing effective security measures.
*   **Risk Reduction:** Implementing the recommended controls and achieving compliance significantly reduces the likelihood and impact of security incidents. This protects sensitive data, maintains business continuity, and safeguards the organization's reputation.
*   **Support for Audits and Assessments:** These checklists can be used as valuable tools during internal and external security audits and assessments. They provide a standardized framework for evaluating security controls and demonstrating compliance.
*   **Proactive Security Approach:** By focusing on preventative measures and continuous monitoring, these checklists and recommendations promote a proactive security approach. This helps organizations shift from a reactive "break-fix" model to a more robust and resilient security posture.

**In Summary:**

These checklists are not merely a formality; they are essential tools for managing risk, ensuring compliance, and building a strong security foundation. By regularly assessing controls and compliance, organizations can proactively identify and mitigate vulnerabilities, ultimately protecting their valuable data assets and maintaining trust with their customers and stakeholders.

</details>

[View my lab(PDF)](https://docs.google.com/document/d/1baK64ZYJ7_WV1yfbBhWFdvP-WzCMtfJocGtETIhjRMk/edit?usp=sharing)


# Cybersecurity incident report

See Details
<details>
  <summary>Click to expand</summary>

## Cybersecurity Incident Report: Network Interruption Analysis

This report documents an analysis of a network interruption, identifying it as a Denial-of-Service (DoS) attack, specifically a SYN flood. The report explains the technical details of the attack and its impact on the website's functionality.

**Section 1: Identify the Type of Attack**

The observed errors, timeout messages, and the server's unresponsiveness after being overloaded with SYN packets strongly suggest a DoS attack. The specific type of DoS attack is identified as a SYN flood.

**Section 2: Explain How the Attack is Causing the Website to Malfunction**

The normal TCP connection establishment process involves a three-way handshake:

1.  **SYN:** The client sends a SYN packet to the server to initiate a connection.
2.  **SYN-ACK:** The server responds with a SYN-ACK packet, acknowledging the request and allocating resources for the connection.
3.  **ACK:** The client sends an ACK packet back to the server to complete the connection establishment.

A SYN flood attack disrupts this process by overwhelming the server with a large volume of SYN packets. The server responds to each SYN with a SYN-ACK and allocates resources, but it never receives the final ACK from the attacker. This leaves the server with a large number of half-open connections, consuming its resources and preventing it from responding to legitimate connection requests. As a result, legitimate users experience connection timeouts.

Server logs confirm the overload scenario, indicating the server's inability to process legitimate SYN requests and establish new connections, leading to connection timeout messages for visitors.

**Importance of This Report and the Analysis:**

This type of incident report and analysis is crucial for several reasons:

*   **Incident Response:** Documents the details of the security incident for effective response, understanding the scope, impact, and recovery steps.
*   **Root Cause Analysis:** Identifies the root cause (SYN flood), enabling implementation of appropriate mitigation measures.
*   **Technical Understanding:** Demonstrates understanding of the TCP three-way handshake and SYN flood mechanics.
*   **Communication:** Provides a clear explanation for both technical and non-technical stakeholders.
*   **Evidence and Forensics:** Serves as a record of the incident for potential forensic investigations.
*   **Security Posture Improvement:** Enables identification of security weaknesses and implementation of preventative measures.

**Demonstrated Skills:**

By creating this report, the following skills were demonstrated:

*   **Incident Identification:** Ability to identify a network interruption as a DoS attack.
*   **Technical Analysis:** Understanding of the TCP three-way handshake and SYN flood attack.
*   **Log Analysis:** Utilizing server logs to support conclusions.
*   **Communication Skills:** Clear and understandable presentation of technical information.
*   **Problem-Solving:** Contributing to incident response by identifying the root cause.

In summary, this Cybersecurity Incident Report showcases the ability to analyze security incidents, understand technical details, and communicate findings effectively, a valuable skill for any cybersecurity professional.

  </details>

[View my lab(PDF)](https://docs.google.com/document/d/1izEafzURaE2SY-eUa5Yzr3FOUBKAmqhVIkI8h1Q_KGw/edit?usp=sharing)

# File permissions in Linux

See Details
<details>
  <summary>Click to expand</summary>

## Linux File Permissions Management

This project demonstrates proficiency in managing file permissions in Linux using the command-line interface. It covers listing file details (including permissions) with `ls` and `ls -l`, and modifying permissions using `chmod` with the `+` and `-` operators. The project also addresses handling hidden files and directory permissions.

**Key Operations Demonstrated:**

*   **Check File and Directory Details:** Demonstrates using `ls` to list files and `ls -l` to display detailed file information, including permissions, ownership, file size, and modification time. Example:

    ```bash
    ls
    ls -l
    ```

*   **Describe the Permissions String:** Explains the meaning of the permission string (e.g., `-rw-rw-r--`). Breaks down the string into user (owner), group, and others, and explains `r` (read), `w` (write), and `x` (execute). Example:

    `-rw-rw-r--` breaks down as: `- (file type) rw- (user) rw- (group) r-- (others)`

*   **Change File Permissions:** Demonstrates using `chmod` with `+` and `-` to grant and revoke permissions. Example:

    ```bash
    chmod o-w filename  # Removes write permission for others
    chmod u+x script.sh # Adds execute permission for the user
    chmod 755 filename # Sets permissions to rwxr-xr-x (using octal notation)
    ```

*   **Change File Permissions on a Hidden File:** Shows how to view and modify permissions for hidden files using `ls -la` and `chmod`. Example:

    ```bash
    ls -la
    chmod g+r .hiddenfile # Adds read permission for the group
    ```

*   **Change Directory Permissions:** Demonstrates changing permissions for directories, focusing on the execute permission (`x`), which is necessary for accessing the contents of a directory. Example:

    ```bash
    chmod u+x directoryname # Adds execute permission for the user to the directory
    chmod 700 directoryname # Sets permissions to rwx------ (only user has full access)
    ```

**Importance of Understanding File Permissions in Linux:**

Understanding and managing file permissions in Linux is crucial for:

*   **Data Confidentiality:** Controls who can read file content.
*   **Data Integrity:** Prevents unauthorized file modifications.
*   **System Security:** Prevents unauthorized program execution.
*   **Principle of Least Privilege:** Enforces granting only necessary permissions.
*   **Incident Response and Forensics:** Aids in understanding access patterns during investigations.
*   **Compliance:** Meets security standards and regulatory requirements.

**Demonstrated Skills:**

*   Using `ls` and `ls -l` to view file information.
*   Interpreting permission strings.
*   Using `chmod` (including octal notation) to modify permissions.
*   Managing hidden file permissions.
*   Managing directory permissions.

In summary, this project highlights practical skills in Linux file system management, focusing on the critical security aspect of file permissions. This is a fundamental skill for any system administrator, cybersecurity analyst, or Linux user.

</details>

[View my lab(PDF)](https://docs.google.com/document/d/1MHv1Mfv_P7n_H7wXdYg3yPHlUUjXhja-ZhHBQ5cHR_U/edit?usp=sharing)

# incident handler's journal 

See Details
<details>
  <summary>Click to expand</summary>

## Incident Handler's Journal

This journal documents learning experiences and reflections on various cybersecurity concepts and tools, logging activities related to incident response, network analysis, and malware analysis.

**Date: July 23, 2024**

**Entry #1: Documenting a Cybersecurity Incident**

**Description:** Documenting a cybersecurity incident involving ransomware.

*   **Detection and Analysis:** The organization detected the ransomware incident and contacted external organizations for technical assistance.
*   **Containment, Eradication, and Recovery:** The company shut down their computer systems as a containment measure and sought external assistance for eradication and recovery.

**Tool(s) used:** None

**The 5 W's:**

*   **Who:** An organized group of unethical hackers.
*   **What:** A ransomware security incident.
*   **Where:** A health care company.
*   **When:** Tuesday, 9:00 a.m.
*   **Why:** A phishing attack allowed attackers to access systems, deploy ransomware, and demand a ransom (financial motivation).

**Additional notes:**

*   How could the health care company prevent similar incidents?
*   Should the company pay the ransom?

---

**Date: July 25, 2024**

**Entry #2: Analyzing a Packet Capture File**

**Description:** Analyzing a packet capture file.

**Tool(s) used:** Wireshark (network protocol analyzer with a GUI).

**The 5 W's:** N/A

**Additional notes:** First experience with Wireshark; initial impression of the interface being overwhelming but powerful.

---

**Date: July 25, 2024**

**Entry #3: Capturing My First Packet**

**Description:** Capturing network traffic.

**Tool(s) used:** `tcpdump` (command-line network protocol analyzer).

**The 5 W's:** N/A

**Additional notes:** Challenges using the command-line interface for capturing and filtering; learned the importance of careful instruction following.

---

**Date: July 27, 2024**

**Entry #4: Investigate a Suspicious File Hash**

**Description:** Investigating a suspicious file hash.

**Tool(s) used:** VirusTotal (malware analysis tool).

**Incident Phase:** Detection and Analysis (SOC scenario).

**The 5 W's:**

*   **Who:** Unknown malicious actor.
*   **What:** Malicious file attachment (SHA-256 hash: `54e6ea47eb04634d3e87fd7787e2136ccfbcc80ade34f246a12cf93bab527f6b`).
*   **Where:** An employee's computer at a financial services company.
*   **When:** 1:20 p.m. (alert from IDS).
*   **Why:** Employee downloaded and executed a malicious email attachment.

**Additional notes:**

*   How can this incident be prevented in the future?
*   Should security awareness training be improved?

---

**Reflections/Notes:**

*   **Challenges:** `tcpdump` was challenging due to unfamiliarity with the command-line interface; learned the importance of careful instruction following.
*   **Changed Understanding of Incident Detection and Response:** Developed a deeper understanding of the incident lifecycle, plans, processes, people, and tools involved.
*   **Most Enjoyed Tool/Concept:** Enjoyed learning about network traffic analysis and using network protocol analyzer tools.

This journal demonstrates an understanding of incident response, tool proficiency (Wireshark, `tcpdump`, VirusTotal), analytical skills, self-reflection, and documentation skills.

</details>

[View my lab(PDF)](https://docs.google.com/document/d/1lS5JGUSRnaYukYXJPpkqVujvtgSezwHIaiz_akqfGtA/edit?usp=sharing)

# Security incident report template

See Details
<details>
  <summary>Click to expand</summary>

## Security Incident Report: Website Compromise and User Redirection

This report details a security incident involving a website compromise and user redirection for malicious purposes.

**Section 1: Network Protocol Involved**

The primary protocol involved in this incident is **HTTP (Hypertext Transfer Protocol)**. HTTP is used for communication between web browsers and servers. The compromised website initially used HTTP to deliver legitimate content. However, after the malicious file download, the attacker manipulated user traffic through HTTP requests to a different, malicious website. `tcpdump` logs confirmed HTTP traffic interacting with the requests, particularly the transfer of the malicious file at the application layer.

**Section 2: Incident Documentation**

**2.1 Initial Reports**

Several customers reported experiencing issues after visiting `yummyrecipesforme.com`, including:

*   Prompted to download a file for new recipes.
*   Slow computer performance after the download.
*   The website owner's account being locked out.

**2.2 Investigation**

*   A cybersecurity analyst used an isolated environment to simulate a user's experience.
*   The analyst downloaded the offered file and observed a redirection to a fake website, `greatrecipesforme.com`.
*   Initial network traffic analysis showed normal communication with the legitimate server (`yummyrecipesforme.com`).
*   Post-download, traffic was redirected to the fake website (`greatrecipesforme.com`).

**2.3 Root Cause Analysis**

The investigation revealed:

*   Attackers compromised `yummyrecipesforme.com` by tampering with its code.
*   The altered code displayed a fake browser update prompt, which was actually a malicious file.
*   The website owner was likely locked out via a brute-force attack, granting the attacker control to manipulate the website.
*   The downloaded file rerouted user connections, potentially compromising visitors' computers.

**Section 3: Recommended Remediation for Brute-Force Attacks**

To prevent future brute-force attacks, the following measures are recommended:

*   **Enforce Password Complexity:** Require strong passwords (e.g., minimum 15 characters, mixed case, numbers, symbols).
*   **Disallow Password Reuse:** Implement a policy preventing users from reusing previous passwords.
*   **Enable Two-Factor Authentication (2FA):** Implement 2FA using one-time passcodes (OTPs) sent to users' devices.

**Importance of Security Incident Reports:**

Security incident reports are essential for:

*   **Understanding Attack Scope:** Documenting details helps understand attack vectors, affected systems, and user impact.
*   **Facilitating Remediation:** Provides a basis for implementing corrective actions and preventing recurrence.
*   **Compliance and Regulations:** Supports compliance with reporting requirements.
*   **Communication and Collaboration:** Facilitates communication with stakeholders.
*   **Learning and Improvement:** Provides insights for improving future security posture.

**Note on `tcpdump` Traffic Log:**

`tcpdump` was used to capture network traffic. The logs likely showed the initial legitimate HTTP requests followed by the redirection to the malicious domain after the file download. Including relevant log excerpts would further strengthen the report.

</details>

[View my lab(PDF)](https://docs.google.com/document/d/1eQEJ45C15MO0S_jvJWQj4oHtcSL8PKXSJZ4FIMzBHDc/edit?usp=sharing)

