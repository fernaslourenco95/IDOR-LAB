# 🔍 IDOR Lab

## 🎯 Objective
Demonstrate and exploit Insecure Direct Object Reference (IDOR) vulnerabilities.

## 🧠 What is IDOR?
IDOR occurs when an application exposes direct object references without proper authorization checks.

## 🧪 Lab Setup
- Simple web app with user profiles
- ID-based access control

## 💥 Exploitation
1. Login as user A
2. Capture request:
   /profile?id=1
3. Change to:
   /profile?id=2
4. Access unauthorized data

## 🛠 Tools Used
- Burp Suite
- Browser DevTools

## ✅ Mitigation
- Proper authorization checks
- Avoid direct object references

## 📌 Conclusion
IDOR is simple but critical and widely found in real-world apps.
