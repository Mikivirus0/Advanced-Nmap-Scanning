# Advanced Nmap Scanning - Top 20 Nmap Commands

## Introduction
Nmap (Network Mapper) is one of the most powerful network scanning tools used for reconnaissance, vulnerability assessment, and penetration testing. This guide covers **20 advanced Nmap commands** to help security professionals, pentesters, and system administrators get the most out of Nmap.

---

## 1. **Basic Host Discovery**
Scan a single target to check if it is online.
```bash
nmap -sn <target-IP>
```
Example:
```bash
nmap -sn 192.168.1.1
```

## 2. **Scan an Entire Subnet**
```bash
nmap -sn 192.168.1.0/24
```

## 3. **Aggressive Scan (OS, Services, Versions, Scripts)**
```bash
nmap -A <target-IP>
```

## 4. **Scan Multiple Targets**
```bash
nmap <target1> <target2>
```
Example:
```bash
nmap 192.168.1.1 192.168.1.2
```

## 5. **Scan Ports (Specific & Full Range)**
Scan a single port:
```bash
nmap -p 80 <target-IP>
```
Scan multiple ports:
```bash
nmap -p 22,80,443 <target-IP>
```
Scan all 65535 ports:
```bash
nmap -p- <target-IP>
```

## 6. **Service and Version Detection**
```bash
nmap -sV <target-IP>
```

## 7. **OS Detection**
```bash
nmap -O <target-IP>
```

## 8. **Scan with Stealth (SYN Scan)**
```bash
nmap -sS <target-IP>
```

## 9. **Scan with UDP**
```bash
nmap -sU <target-IP>
```

## 10. **Detect Firewall and Bypass with Fragmented Packets**
```bash
nmap -f <target-IP>
```

## 11. **Spoof IP Address**
```bash
nmap -S <spoofed-IP> <target-IP>
```

## 12. **Scan with Decoy (Avoid Detection)**
```bash
nmap -D RND:10 <target-IP>
```

## 13. **Evade Intrusion Detection Systems (IDS)**
```bash
nmap --data-length 50 <target-IP>
```

## 14. **Scan for Open Ports without Ping**
```bash
nmap -Pn <target-IP>
```

## 15. **Scan for Common Vulnerabilities (Nmap Scripts)**
```bash
nmap --script vuln <target-IP>
```

## 16. **Brute Force Login with Nmap Scripts**
Example for SSH brute force:
```bash
nmap --script ssh-brute -p 22 <target-IP>
```

## 17. **Scan Multiple Hosts from a List**
```bash
nmap -iL targets.txt
```

## 18. **Scan for Default Credentials**
```bash
nmap --script http-default-accounts <target-IP>
```

## 19. **Save Scan Results in Different Formats**
```bash
nmap -oN output.txt -oX output.xml -oG output.gnmap <target-IP>
```

## 20. **Scan for SMB Vulnerabilities**
```bash
nmap --script smb-vuln* -p 445 <target-IP>
```

---

## 21. **Bypass Firewalls with IP Fragmentation**
```bash
nmap -f <target-IP>
```

## 22. **Use Randomized Hosts and Ports to Evade Detection**
```bash
nmap -T4 -D RND:10 --randomize-hosts -p- <target-IP>
```

## 23. **All In One Commands**
```bash
sudo nmap -sS -Pn -T1 --scan-delay 500ms --max-retries 2 --data-length 20 -f --mtu 16 --source-port 53 -D RND:5 -p- <target-IP>
```
```bash
sudo nmap -sS 49.50.79.115 --script firewall-bypass --mtu 16 -T2 -p- --data-length 24 --source-port 53 <target-IP>
```
```bash
sudo nmap -sS 49.50.79.115 --script firewall-bypass --mtu 16 -v --min-rate=200 --max-retries 3 --scan-delay 100ms -p- --data-length 24 --source-port 53 -D RND:10 <target-IP>
```

## **RustScan and FScan**
### RustScan
RustScan is an extremely fast port scanner that integrates with Nmap for detailed service enumeration. It helps to quickly identify open ports before performing deeper scans. [Link](https://github.com/RustScan/RustScan)
```bash
rustscan -a <target-IP> --ulimit 5000 | nmap -sV -A -p- -
```

### FScan
FScan is a simple and fast scanning tool used to discover open ports and vulnerabilities. It is widely used for internal and external network reconnaissance and is particularly effective for identifying internal hosts and performing internal port scanning. [Link](https://github.com/shadow1ng/fscan)
```bash
./fscan -h <target-IP> -p 80,443,3389 -m vulscan
```

---

---

## Conclusion
Nmap is a **must-have** tool for any cybersecurity expert. Whether you are conducting network reconnaissance, penetration testing, or vulnerability assessment, mastering these Nmap commands can greatly enhance your efficiency and effectiveness.

**References:**
- [Recorded Future - Nmap Commands](https://www.recordedfuture.com/threat-intelligence-101/tools-and-techniques/nmap-commands)
- [Zero To Mastery - Nmap Cheat Sheet](https://zerotomastery.io/cheatsheets/nmap-cheat-sheet/)
- [Nmap Cheat Sheet - GitHub](https://github.com/ekol-x9/nmap-cheatsheet)
- [Hacking Resources - GitHub](https://github.com/Lifka/hacking-resources/blob/main/nmap-cheat-sheet.md)
- [NMAP](https://nmap.org/book/man.html)

---

🔥 **If you found this guide useful, give it a ⭐ on GitHub!** 🔥

