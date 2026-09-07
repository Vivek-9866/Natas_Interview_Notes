# 🔥 Q1 — Hidden Functionality

## 🟢 Scenario 1 — Hidden Information

### 🎤 Interview Question

**How would you find hidden sensitive information in a webpage?**

### 💡 Answer

I would first inspect the page source, HTML comments, hidden fields, and JavaScript files for sensitive information.

Then I would use Burp Suite to inspect the requests and responses and verify whether the information is actually accessible or usable.

### 🌐 Real-Time Example

A login page looks normal, but the source contains:

`<!-- Admin test password: admin123 -->`

I would verify whether the credential is valid and what access it provides. If it provides unauthorized access, I would report it with evidence and impact.

### 🧠 Remember

**Source → Burp → Validate → Impact → Report**

---

## 🟡 Scenario 2 — Hidden Files / Directories

### 🎤 Interview Question

**No admin link is visible. How would you discover hidden files or directories?**

### 💡 Answer

I would first manually explore the application and identify interesting paths.

Then I would use FFUF to discover hidden files and directories. After finding a resource, I would verify whether it is publicly accessible and whether it exposes sensitive information or functionality.

### 🌐 Real-Time Example

FFUF discovers:

`/backup`

The directory contains a sensitive configuration file and is accessible without authentication.

I would verify the exposure, assess the impact, and report it as an information disclosure issue.

### 🧠 Remember

**Explore → FFUF → Verify → Impact → Report**

---

## 🔴 Scenario 3 — Hidden JavaScript

### 🎤 Interview Question

**You discover a JavaScript file. What security issues would you look for?**

### 💡 Answer

I would review the JavaScript for sensitive information, API endpoints, hidden functionality, and internal paths.

Then I would test the discovered endpoints using Burp Suite and verify whether proper authentication and authorization are enforced.

### 🌐 Real-Time Example

JavaScript reveals:

`/admin/deleteUser`

I would log in as a normal user and test the endpoint. If the normal user can perform the admin action, it indicates a broken access control issue.

### 🧠 Remember

**JS → Endpoint → Burp → Access Control → Report**

---

# ⚡ QUICK REVISION

- 🟢 **Hidden Information:** Source → Burp → Validate
- 🟡 **Hidden Files:** Explore → FFUF → Verify
- 🔴 **Hidden JS:** JS → Endpoint → Access Control
