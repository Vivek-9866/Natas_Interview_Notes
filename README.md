🟢 LEVEL 1 — Client-Side Security / Hidden Functionality
🎯 Core Concept

Never trust the client. Always verify security controls on the server.

Q1. Hidden Functionality / Information Disclosure
🏢 Scenario 1: Hidden Information in Login Page
Interviewer:

A login page looks normal. How would you check whether sensitive information is hidden in the webpage?

⭐ Memorable Answer

"First, I inspect the page source for HTML comments, hidden fields, and linked JavaScript files. Then I use Burp Suite to inspect HTTP requests and responses. If I find sensitive information, I validate whether an unauthorized user can access it, assess the impact, and report it with evidence."

💡 Real-Time Example
Login Page
    ↓
View Source
    ↓
HTML comment:
<!-- admin password = test123 -->
    ↓
Validate access
    ↓
Sensitive information exposed
    ↓
Report with evidence + impact
🧠 Remember:

Source → Burp → Validate → Impact → Report

🏢 Scenario 2: Hidden Files / Directories
Interviewer:

You are testing an e-commerce website. No admin link is visible. How would you find hidden files or directories?

⭐ Memorable Answer

"First, I manually explore the application. Then I use FFUF to find hidden files and directories. If I find a publicly accessible resource, I verify whether it exposes sensitive data or functionality, assess the impact, and report it with evidence."

💡 Real-Time Example
Website
   ↓
Manual exploration
   ↓
FFUF
   ↓
/admin
/backup
/config
   ↓
/admin is publicly accessible
   ↓
Check what it exposes
   ↓
Impact + Evidence + Report
🔧 Tool

FFUF = a web fuzzing tool used to discover hidden paths/files/directories.

🧠 Remember:

Explore → FFUF → Verify → Impact → Report

🏢 Scenario 3: Hidden JavaScript File
Interviewer:

You discover a hidden JavaScript file on a login page. What would you do to check whether it creates a security risk?

⭐ Memorable Answer

"I log in with a basic account and use Burp Suite to inspect the requests and responses. I check whether the JavaScript exposes sensitive information, endpoints, or functionality. Then I validate access control and report the issue with clear evidence and impact."

💡 Real-Time Example
Login Page
    ↓
Hidden JS file
    ↓
app.js
    ↓
Contains:
/admin/deleteUser
/api/export
    ↓
Test access with basic account
    ↓
Can normal user access it?
    ↓
If yes → Broken Access Control
🧠 Remember:

Find JS → Burp → Check endpoints → Validate access → Report

🔥 Quick Revision — Day 1
Scenario 1

Hidden information

Source → Burp → Validate → Impact → Report

Scenario 2

Hidden files/directories

Explore → FFUF → Verify → Impact → Report

Scenario 3

Hidden JavaScript

Find JS → Burp → Check endpoints → Validate → Report
