# DAY 1 — VAPT INTERVIEW PREPARATION

## LEVEL 1 — Client-Side Security / Hidden Functionality

### Core Concept

- Never trust the client.
- Always verify security controls on the server.

---

# Q1 — Hidden Functionality / Information Disclosure

## Scenario 1 — Hidden Information in Login Page

### Interviewer

- A login page looks normal. How would you check whether sensitive information is hidden in the webpage?

### Memorable Answer

- First, I inspect the page source for HTML comments, hidden fields, and linked JavaScript files.
- Then I use Burp Suite to inspect HTTP requests and responses.
- If I find sensitive information, I validate whether an unauthorized user can access it.
- Finally, I assess the impact and report it with evidence.

### Real-Time Example

- Open the login page.
- View the page source.
- Check:
  - HTML comments
  - Hidden fields
  - JavaScript files
- Example:

  <!-- admin password = test123 -->

- If sensitive information is exposed, verify whether it can actually be accessed or misused.
- Document the evidence and impact.

### Remember

- Source → Burp → Validate → Impact → Report

---

## Scenario 2 — Hidden Files / Directories

### Interviewer

- You are testing an e-commerce website.
- No admin link is visible.
- How would you find hidden files or directories?

### Memorable Answer

- First, I manually explore the application.
- Then I use FFUF to find hidden files and directories.
- If I find a publicly accessible resource, I verify what it exposes.
- Then I assess the impact and report it with evidence.

### Real-Time Example

- Website:
  - https://example.com

- Use FFUF to discover hidden paths.
- Possible results:

  - /admin
  - /backup
  - /config

- Suppose `/admin` is discovered.
- Try accessing it without proper authorization.
- Check whether sensitive information or privileged functionality is exposed.
- If it is accessible, document the evidence and impact.

### Remember

- Explore → FFUF → Verify → Impact → Report

### Tool

- FFUF = Fast web fuzzing tool.
- Used to discover hidden files, directories, and endpoints.

---

## Scenario 3 — Hidden JavaScript File

### Interviewer

- You discover a hidden JavaScript file on a login page.
- What would you do to check whether it creates a security risk?

### Memorable Answer

- I log in with a basic account and use Burp Suite to inspect the requests and responses.
- I check the JavaScript for sensitive information, hidden endpoints, or functionality.
- Then I validate whether the basic user can access restricted functionality.
- Finally, I assess the impact and report it with clear evidence.

### Real-Time Example

- Login with a normal user.
- Find a JavaScript file:

  - app.js

- While reviewing it, you find:

  - /admin/deleteUser
  - /api/export

- Use Burp Suite to test whether a normal user can access these endpoints.
- If a normal user can perform an admin-level action:

  - Broken Access Control

- Report:
  - Steps to reproduce
  - Evidence
  - Impact
  - Recommended fix

### Remember

- Find JS → Burp → Check endpoints → Validate access → Report

---

# QUICK REVISION

## Scenario 1

- Hidden information
- Source → Burp → Validate → Impact → Report

## Scenario 2

- Hidden files/directories
- Explore → FFUF → Verify → Impact → Report

## Scenario 3

- Hidden JavaScript
- Find JS → Burp → Check endpoints → Validate → Report

---

# COMMUNICATION PRACTICE

## Avoid

- "I can... I can... I can..."
- "I see... I see..."
- "It opens everyone..."
- "I validate accessible..."

## Use

- "First, I..."
- "Then, I..."
- "If I find..."
- "I would validate..."
- "Finally, I would..."

### Professional Flow

- First → Then → If I find → Validate → Impact → Report

---

# DAY 1 STATUS

- Q1 completed
- 3 different real-world scenarios covered
- Burp Suite covered
- FFUF covered
- Source-code inspection covered
- Hidden endpoints covered
- Access control validation covered
- Impact and reporting covered

### Interview Rule

- I must explain the scenario confidently before moving to the next question.
- If my answer is weak, repeat the same scenario.
- After preparation, conduct a strict MNC-style mock interview.
- No hints during the strict interview.
- Move to the next question only after passing.
