# ICS344-03-G06-Final-Project

## Course: ICS344 – Information Security  
**Project Title:** Vulnerability Exploitation, SIEM Analysis & Defense Strategy

---

## Group Information

| **Group Number** | 03-G06 |
|------------------|--------|
| **Course Section** | 03 |
| **Course** | ICS344 |

### Group Members

| **Name**                | **Student ID** |
|-------------------------|----------------|
| Ali Ahmed Alafif        | 202064260      |
| Saud Abdulaziz Alhawas  | 202014840      |
| Salman Ali Alsayab      | 202039060      |

---

## Work Distribution

- **Phase 1 (Setup & Compromise):**
  - Setting up Metasploitable3 & Kali Linux: Student 1
  - Performing Metasploit attack: Student 2
  - Developing the custom attack script: Student 3

- **Phase 2 (SIEM Dashboard Analysis):**
  - Installing and configuring Splunk: Student 1
  - Integrating logs & creating visualizations: Student 2

- **Phase 3 (Defensive Strategy Proposal):**
  - Defense setup & implementation: Student 3
  - Testing, validation & documentation: Student 1

---

## Project Overview

This project follows the requirements from the [ICS344 Course Project Guide](https://github.com/osamacs7/344-Setup-Guide) and is divided into three phases:

### Phase 1: Setup & Compromise the Service

- **Victim Environment:** Metasploitable3 VM
- **Attacker Environment:** Kali Linux VM
- **Selected Service:** SSH (port 22)
- **Tools:**
  - Metasploit Framework
  - Custom Python Script

**Summary:**
- The attack was executed using `msfconsole` with the `auxiliary/scanner/ssh/ssh_login` module.
- Credentials found: `vagrant:vagrant`.
- The session was upgraded to a Meterpreter shell.
- A custom Python script was developed to automate the SSH brute force attack and demonstrate exploitation.

### Phase 2: SIEM Dashboard Analysis

- **Tool:** Splunk v9.3.2
- **Setup:**
  - Logs were forwarded from the victim machine to Splunk.
  - Two indexes were created to track attack logs.
- **Visualization:**
  - Attack logs (e.g., failed SSH login attempts) were charted using Splunk’s search and visualization tools.
  - Key searches included:
    - `index=* "Failed password" | timechart count`
    - `index=* "Failed password" | stats count by host`

### Phase 3: Defensive Strategy Proposal

- **Defense Mechanisms:**
  - Updated SSH configurations (disabled root login, strong passwords).
  - Installed and configured Fail2Ban.
  - Applied firewall rules to limit SSH access.
- **Validation:**
  - The original attack scripts were re-run post-defense implementation.
  - Logs showed a significant reduction in successful login attempts, demonstrating the effectiveness of the defense.

---

## Repository Structure

