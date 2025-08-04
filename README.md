# Elevate_Labs_Internship_Day_1-Task-1

---

````markdown
 🔍 Nmap Network Scan & Port Security Analysis

 📌 Objective

This project involves performing a network scan using **Nmap** to identify active devices, open TCP ports, and associated services within a given subnet. The ultimate goal is to detect potential security risks associated with exposed ports and suggest mitigation strategies.

---

 🛠️ Tools Used

- [Nmap](https://nmap.org/download.html) – Network scanning tool
- [Wireshark](https://www.wireshark.org/) (Optional) – Packet analysis
- [SpeedGuide Port Database](https://www.speedguide.net/port.php) – Port info
- [SANS ISC](https://isc.sans.edu/) – Port vulnerability references

---

 🔄 Steps Performed

1. **Install Nmap** from the official [Nmap download page](https://nmap.org/download.html).
2. **Identify local IP address** using:
   ```bash
   ipconfig   # (Windows) or ifconfig / ip a (Linux)
````

3. Determine subnet range (e.g., for `192.168.29.168` with subnet mask `255.255.224.0`, CIDR = `/19`)
4. Run a TCP SYN scan on the host:

   ```
   nmap -sS 192.168.29.168
   ```
5. Review open ports and running services.
6. Research common services using:

    [https://www.speedguide.net/port.php](https://www.speedguide.net/port.php)
    [https://nmap.org/book/services.html](https://nmap.org/book/services.html)
7. Identify potential security risks (see analysis below).
8. Export results to a file:

   ```
   nmap -sS 192.168.29.168 -oN scan_results.txt
   ```


 🛡️ Recommendations

* 🔐 Block unused ports on firewall (especially 135, 139, 445).
* 🔄 Regularly update Windows and associated services.
* 🧩 Disable NetBIOS and WSDAPI if not in use.
* 📜 Investigate unknown ports (like 8089) using:

  ```
  nmap -sV -sC 192.168.29.168
  ```
 🛠️ Run vulnerability scans using tools like Nessus or OpenVAS.
 👁️‍🗨️ Monitor port usage with `netstat -aon` or endpoint protection.

---

 📂 Files

 `scan_results.txt` – Nmap output
 `README.md` – Documentation
 (Optional) `scan_capture.pcapng` – Wireshark packet capture (if done)

---

📚 References

 [Nmap Book](https://nmap.org/book/man-port-scanning-techniques.html)
 [SpeedGuide Port Database](https://www.speedguide.net/port.php)
 [SANS ISC Port List](https://isc.sans.edu/port.html)
* [Microsoft SMB Security Best Practices](https://learn.microsoft.com/en-us/windows-server/storage/file-server/smb-security)
