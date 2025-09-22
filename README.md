# Cyber-Security-Internship-Task-1
Nmap local network scan results and documentation for Cyber Security Internship Task 1.
# Cyber-Security-Internship-Task-1

## 📌 Objective
Perform a local network scan using Nmap and document the findings.  
(Internal/lab network only — do not scan networks without permission.)

## 🔧 Tools Used
- Nmap (CLI) / Zenmap (GUI)  
- Windows 11 (host system)

## 📡 Command Used
bash
nmap -sS 172.20.10.0/28 -oN scan_results.txt -oX scan_results.xml

## 📑 Scan Results

### Host: 172.20.10.1

* **Open ports**

  * 21/tcp — FTP
  * 53/tcp — DNS
  * 62078/tcp — iPhone sync service
* **MAC Address:** AE:45:00\:E7\:D3:64 (Unknown vendor)

### Host: 172.20.10.3

* **Open ports**

  * 135/tcp — MSRPC
  * 139/tcp — NetBIOS-SSN
  * 445/tcp — Microsoft-DS (SMB)
  * 3306/tcp — MySQL

*Nmap summary: 16 IP addresses scanned; 2 hosts up.*

## 📂 Files Included

* `scan_results.txt` — human-readable Nmap output
* `scan_results.xml` — XML output (convertible to HTML)
* `screenshots/` — Zenmap/Wireshark screenshots

## 📝 Observations & Notes

* `172.20.10.1` shows a port typical of iOS device services — likely a mobile device.
* `172.20.10.3` is running SMB/NetBIOS and MySQL — could be a workstation or local server; these services can be attractive attack targets if exposed.
* No unexpected hosts responded beyond these two in the scanned subnet.

## ⚠ Risks & Recommendations

* **FTP (21):** insecure — avoid plaintext credentials; replace with SFTP/FTPS where possible.
* **SMB (445) / NetBIOS (139):** ensure SMBv1 disabled, restrict access via firewall, keep systems patched.
* **MySQL (3306):** restrict remote access, use strong passwords and least-privilege DB accounts.
* **General:** apply regular patching, enforce strong authentication, and limit exposure using firewalls.

## ✅ Conclusion

The scan identified two active hosts with multiple services. Follow remediation steps above to reduce exposure. This repository contains scan output and supporting screenshots for review.
## Author

* Abuzar1229
