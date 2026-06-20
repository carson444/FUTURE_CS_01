# FUTURE_CS_01
Vulnerability Assessment Report - Task 1
Target: demo.testfire.net
Date: June 18, 2026
Auditor: OGBONE Iredon Ammal
Status: ✅ Completed

📋 Project Overview
This report presents the findings of a vulnerability assessment conducted on demo.testfire.net as part of my Cyber Security internship at Future Interns.

The objective was to identify, classify, and document security weaknesses using industry-standard tools and methodologies.

🛠️ Tools Used
Tool	Purpose
Nmap	Port scanning and service detection
Sucuri SiteCheck	Malware and blacklist detection
Qualys SSL Labs	SSL/TLS configuration analysis
Chrome DevTools	HTTP security headers analysis
📊 Key Findings
Severity	Count
🔴 Critical	1
🟠 Medium	4
🟡 Low	5
Total	10
🔴 Main Vulnerability
Login form uses HTTP (not HTTPS)

Location: http://demo.testfire.net/login.jsp
Issue: Credentials transmitted in clear text over the network
Impact: An attacker can intercept usernames and passwords
Solution: Enable HTTPS immediately for all login forms
🟠 Other Medium Severity Issues
No HTTP to HTTPS redirect
TLS 1.0 and 1.1 supported (obsolete protocols)
Weak Diffie-Hellman parameters
Missing HSTS header
🟡 Low Severity Issues
Missing X-Frame-Options header
Missing X-Content-Type-Options header
Missing Content-Security-Policy
TLS 1.3 not supported
Server version exposed (Apache-Coyote/1.1)
📁 Files Included
File	Description
Rapport_Vulnerabilites.pdf	Full assessment report (French)
sucuri_capture.png	Sucuri scan results
nmap_capture.png	Nmap scan results
ssllabs_capture.png	SSL Labs analysis
devtools_capture.png	HTTP headers analysis
login_capture.png	Login page showing HTTP
🔧 Recommendations
🔴 URGENT (Day 1)
 Enable HTTPS on all pages
 Redirect HTTP → HTTPS (301 permanent)
 Secure login form with HTTPS
🟠 IMPORTANT (Week 1)
 Disable TLS 1.0 and TLS 1.1
 Add HSTS header
 Upgrade DH parameters to 2048 bits
🟡 IMPROVEMENT (Week 2-4)
 Add X-Frame-Options: DENY
 Add X-Content-Type-Options: nosniff
 Add Content-Security-Policy
 Update server to support TLS 1.3
 Hide server version in headers
Summary
