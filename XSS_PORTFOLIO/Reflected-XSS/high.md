
# 🧪 XSS Report — Reflected XSS (High Level)

**📘 Environment:** DVWA (High Security Level) on Kali Linux + Ubuntu Server  
**🌐 Target URL:**  
http://192.168.1.48/dvwa/vulnerabilities/xss_r/?name=<payload>  
**👤 Tester:** Tetiana Trunova

---

## 🔍 Vulnerability Overview
This report documents a successful Reflected Cross-Site Scripting (XSS) attack on the DVWA platform at the **High** security level.

**🧬 Vulnerability Type:** Reflected XSS (High)  
**🧭 Affected Parameter:** `name` in URL query string

---

## 💣 Payloads Tested

1. `<img src=x onerror=alert(1)>`  
   _Standard image-based payload using `onerror`._

2. `<svg/onload=alert(1)>`  
   _SVG tag triggers JavaScript alert._

3. `<input type="image" src=x onerror=alert(1)>`  
   _Input-based image payload with `onerror`._

All payloads triggered alert boxes, demonstrating successful JavaScript execution.

---

## 🧪 Steps to Reproduce

1. Navigate to the DVWA Reflected XSS (High) page.
2. Inject one of the tested payloads into the `name` parameter of the URL.
3. Press Enter and observe browser behavior.
4. DOM inspection or page source reveals how payload was handled.

---

## 📸 Evidence

### Screenshot 1
![Reflected XSS — High #1](../SCREENSHOTS/reflected-high-1.png)

### Screenshot 2
![Reflected XSS — High #2](../SCREENSHOTS/reflected-high-2.png)

### Screenshot 3
![Reflected XSS — High #3](../SCREENSHOTS/reflected-high-3.png)

### Screenshot 4
![Reflected XSS — High #4](../SCREENSHOTS/reflected-high-4.png)

### Screenshot 5
![Reflected XSS — High #5](../SCREENSHOTS/reflected-high-5.png)

### Screenshot 6
![Reflected XSS — High #6](../SCREENSHOTS/reflected-high-6.png)

### Screenshot 7
![Reflected XSS — High #7](../SCREENSHOTS/reflected-high-7.png)

### Screenshot 8
![Reflected XSS — High #8](../SCREENSHOTS/reflected-high-8.png)

### Screenshot 9
![Reflected XSS — High #9](../SCREENSHOTS/reflected-high-9.png)

_The screenshots confirm alert boxes, source code reflection, and DOM rendering._

---

## 💥 Impact

This vulnerability could allow:

- JavaScript execution in a user's browser
- Session hijacking
- Credential theft
- Redirection to malicious sites

---

## 🛡️ Recommendations

- Implement input sanitization using secure libraries
- Apply Content Security Policy (CSP) headers
- Escape output contextually in templates
- Avoid unsafe DOM manipulations

---

## 👩‍💻 Tester Information

- **👤 Name:** Tetiana Trunova  
- **🗓 Date:** 25.07.2025  
- **🛠 Tools:** Kali Linux, Firefox, Burp Suite  
- **🎯 Test Target:** DVWA – Reflected XSS (High)  
- **📌 Purpose:** Bug Bounty documentation, XSS portfolio

---

_This report is part of the [XSS Vulnerability Testing Portfolio](../README.md)._
