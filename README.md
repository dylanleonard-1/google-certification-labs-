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
