# FUTURE_CS_01 — Vulnerability Assessment Report

**Future Interns · Cyber Security Internship · Task 1**  
CIN: `FIT/APR26/CS8070` · Intern: Romano · Date: 03 May 2026

---

## 🎯 Overview

This repository contains the deliverables for **Task 1** of the Future Interns Cyber Security internship:  
a passive, read-only **Vulnerability Assessment** of a public test web application.

---

## 🌐 Website Tested

| Field | Detail |
|---|---|
| **Target** | `http://testphp.vulnweb.com` |
| **Type** | Deliberately vulnerable demo app (Acunetix) |
| **Purpose** | Ethical security testing & education |
| **Scope** | Public-facing pages, HTTP headers, cookies, open ports |

> ⚠️ `testphp.vulnweb.com` is a legally sanctioned, intentionally vulnerable test site maintained by Acunetix specifically for security education. No actual production or private systems were tested.

---

## 🔍 Scope & Ethics

### ✅ Allowed
- Public-facing page review
- Passive HTTP header inspection
- Browser DevTools analysis
- Port scanning (non-intrusive)
- OWASP ZAP passive scan

### ❌ Not Allowed (Not Performed)
- Login bypass or exploitation
- Brute force attacks
- Denial of Service (DoS)
- Any activity that could harm the site

---

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| **Nmap** | Port and service version detection |
| **OWASP ZAP** (Passive mode) | Automated passive vulnerability scanning |
| **Browser DevTools** | Cookie inspection, header review, source code analysis |
| **curl** | Raw HTTP response header capture |

---

## 📊 Findings Summary

| ID | Vulnerability | Severity |
|---|---|---|
| F-01 | SQL Injection via URL parameter | 🔴 HIGH |
| F-02 | Reflected Cross-Site Scripting (XSS) | 🔴 HIGH |
| F-03 | Directory Listing Enabled | 🔴 HIGH |
| F-04 | Missing HTTP Security Headers (5 absent) | 🟡 MEDIUM |
| F-05 | No CSRF Protection on Forms | 🟡 MEDIUM |
| F-06 | Insecure Cookie Configuration | 🟡 MEDIUM |
| F-07 | Server Version Disclosure | 🟡 MEDIUM |
| F-08 | Sensitive Info in HTML Comments | 🟢 LOW |
| F-09 | No HTTPS / SSL Enforcement | 🟢 LOW |

**Total: 9 findings — 3 High · 4 Medium · 2 Low**

---

## 📁 Repository Structure

```
FUTURE_CS_01/
├── README.md                                       ← this file
├── FUTURE_CS_01_Vulnerability_Assessment_Report.html  ← full report
└── evidence/
    ├── nmap_output.txt                             ← tool output
    ├── zap_scan_summary.txt                        ← ZAP results
    └── headers_curl.txt                            ← HTTP headers
```

---

## 📄 Report

The full professional report is available as:

- **`FUTURE_CS_01_Vulnerability_Assessment_Report.html`** — Open in any browser for the formatted report

---

## 🔧 Key Remediation Steps

1. **[P1 — Immediate]** Fix SQL Injection — use parameterised queries
2. **[P1 — Immediate]** Fix XSS — escape all output, implement CSP header
3. **[P1 — Immediate]** Disable directory listing — `autoindex off` in nginx
4. **[P2 — This Week]** Add all 5 security headers to server config
5. **[P2 — This Week]** Secure session cookies (HttpOnly, Secure, SameSite)
6. **[P3 — This Month]** Enable HTTPS via Let's Encrypt + enforce HSTS

---

## 📚 References

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Mozilla HTTP Observatory](https://observatory.mozilla.org/)
- [OWASP Web Security Testing Guide](https://github.com/OWASP/www-project-web-security-testing-guide)
- [Acunetix Test Site](http://testphp.vulnweb.com)

---

*Submitted as part of the Future Interns Cyber Security Internship Programme.*  
*This report is for educational and portfolio purposes only.*
