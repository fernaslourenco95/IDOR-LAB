# 🔍 IDOR Lab

## 🎯 Objective
Demonstrate, exploit, and document Insecure Direct Object Reference (IDOR) vulnerabilities through realistic attack scenarios and structured analysis.

## 🧠 Overview
IDOR (Insecure Direct Object Reference) is an access control vulnerability that occurs when an application exposes internal object identifiers (e.g., user IDs, file IDs) without enforcing proper authorization checks.

This lab focuses on identifying and exploiting these weaknesses in a controlled environment.

---

## 🧪 Lab Environment

The environment simulates a vulnerable web application with:

- Authentication system (multi-user)
- ID-based resource access
- Missing authorization validation layer
- Predictable object references

---

## 🔎 Reconnaissance

Initial analysis reveals:

- Sequential numeric IDs
- Direct object access via URL parameters
- No ownership validation on backend requests

Example endpoint:
    /profile?id=10084

---

## 💥 Exploitation Process

1. Authenticate as a standard user  
2. Intercept request using Burp Suite  
3. Identify direct object reference:
4. Modify parameter:
    /profile?id=10085

5. Forward request and observe unauthorized data exposure  
---
## 📡 Request Example

GET /profile?id=10084 HTTP/1.1
Host: target.local
Cookie: session=abc123

---

## ⚠️ Impact

- Unauthorized access to user data  
- Potential horizontal privilege escalation  
- Exposure of sensitive information  

---

## 🛠 Tools Used

- Burp Suite (Proxy & Repeater)
- Browser Developer Tools

---

## 🔐 Mitigation Strategies

- Enforce server-side authorization checks  
- Validate resource ownership on every request  
- Replace direct references with indirect identifiers (UUIDs)  
- Implement Role-Based Access Control (RBAC)  

---

## 📌 Conclusion

IDOR vulnerabilities remain prevalent due to improper authorization implementation.  
Despite their simplicity, they can lead to severe data breaches and privilege escalation.

---

## 🧪 Next Steps

- Test POST/PUT endpoints for hidden IDOR  
- Explore chained vulnerabilities (IDOR + privilege escalation)  
- Automate detection using Burp Intruder  
