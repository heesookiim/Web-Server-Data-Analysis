# BoilerExam-Data-Analysis

## 1. Suspicious requests from certain IP
- IP 52.169.249.118 has been requesting multiple wp-content or wp related php files.
    - wp means WordPress, which is an open-source web content management system.
- However, according to _isitwp.com_, BoilerExams does not use WordPress

### Observations on Requests
- All top requests target files that are typically associated with WordPress (/wp-includes/, /wp-admin/, /wp-content/).
- Examples include 403.php, readme.php, and themes.php, which are often used in reconnaissance or to exploit vulnerabilities in WordPress installations.
- Requests for files like bak.php and cloud.php suggest probing for backup or misconfigured files, which could reveal sensitive data.
- Each of these requests was made multiple times, which could indicate systematic probing by an automated bot.

### Observations on Time:
- A significant number of requests (438) occurred in a single minute (20th minute), indicating a high likelihood of automated activity, such as a bot or script.
- This was followed by only 20 requests in the next minute, suggesting a sharp drop in activity, potentially due to rate limiting or server defenses.
