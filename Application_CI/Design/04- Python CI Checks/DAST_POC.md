# DAST POC for Python
| Author | Created On | Last Updated | Document Version | Last Updated By |
| ------ | ---------- | ------------ | ---------------- | --------------- |
| Shantanu | 31-01-2024 | 04-02-2024   |         v1     |     Shantanu    |
***
![image](https://github.com/avengers-p7/Documentation/assets/156056364/12604427-c916-4d1b-95af-272227318369)
***
# Table of Contents
[1. POC](#poc)

[2. HTML Report](#html-report)

[3. Analyzing the report](#analyzing-the-report)

[4. Contact Information](#contact-information)

[5. References](#refrences)

For more understanding on ZAP please click [here](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/05-%20GoLang%20CI%20Checks/DAST_POC%20(%20Golang%20CI%20Checks).md)

For detailed understanding on  DAST please click [here](https://github.com/avengers-p7/Documentation/blob/main/Application_CI/Design/02-%20Generic%20CI%20operation/DAST/Documentation/README.md)
# POC 
**Dowload ZAP**
```shell
wget https://github.com/zaproxy/zaproxy/releases/download/v2.14.0/ZAP_2.14.0_Linux.tar.gz
```
**Extract the package**
```shell
tar -xf ZAP_2.14.0_Linux.tar.gz
```
**Run this command**
```shell
./zap.sh -cmd port 8090 -quickurl http://34.100.232.65:8080/api/v1/attendance/health -quickprogress -quickout ~/out2.html
```
# HTML Report
![Screenshot 2024-02-04 at 12 15 59 PM](https://github.com/avengers-p7/Documentation/assets/156056364/ca84d07a-5208-4762-9bf8-fa4198832f71)

# Analyzing the report
So we found issues like Cross-Domain Misconfiguration and X-Content-Type-Options Header Missing, now down below we going to explain them and explore some remediation steps.this report highlights a low-severity security issue related to the missing "X-Content-Type-Options" header in the HTTP response. The recommended solution is to set the appropriate headers to prevent MIME-sniffing, which is especially important for older web browsers.

**Severity**: 

Content Security Policy (CSP) Header Not Set: Medium

X-Content-Type-Options Header Missing: Low

Description: The issue is related to the absence of the "X-Content-Type-Options" header in the HTTP response. This header is used to prevent MIME-sniffing, which is a security feature that browsers employ to determine the content type of a response. Without this header, older versions of Internet Explorer and Chrome may perform MIME-sniffing, potentially causing the response to be interpreted and displayed as a different content type than what was declared.

**URL**: This is the URL of the web application where the issue was detected.

**Method**: The HTTP method used for the request, in this case, it's a GET request.

**Parameter**: The parameter associated with the issue, in this case, "x-content-type-options."

**Attack**: This section typically describes how an attacker could potentially exploit the issue, but in this case, it's not specified.

**Evidence**: There's no specific evidence mentioned in the report.

**Other Info**: This note explains that the issue still applies to error pages (e.g., 401, 403, 500) as they can also be affected by injection issues, potentially causing browsers to interpret the content type incorrectly.

# Contact Information
| Name | Email Address |
| ---- | ------------- |
| Shantanu  | shantanu.chauhan.snaatak@mygurukulam.co |

# References
| Source | Description  | 
| -------- | ------- |
| https://www.zaproxy.org/download/ | OWASP ZAP Download |
