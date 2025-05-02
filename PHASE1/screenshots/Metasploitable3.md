# Metasploitable3 Installation Guide

This guide provides a step-by-step walkthrough for installing **Metasploitable 3** as an OVA file in VirtualBox.

## Prerequisites

- Install [VirtualBox](https://www.virtualbox.org/)
- Download the pre-built Metasploitable 3 OVA file:
  [Metasploitable3 OVA](https://sourceforge.net/projects/metasploitable3-ub1404upgraded/files/)

## Installation Steps

### 1️⃣ Open VirtualBox
- Launch Oracle VirtualBox.

### 2️⃣ Import the Metasploitable 3 VM (.ova)
- Go to `File → Import Appliance`.
- Browse and select your downloaded `.ova` file.
- Click `Next` and follow the prompts to complete the import.

### 3️⃣ Configure Network Settings
- Set the network adapter to `Host-Only Adapter` (for isolated testing).

### 4️⃣ Start the VM
- Boot up Metasploitable3 and log in.

---

## Checking Network

- Run `ifconfig` inside Metasploitable3 to get its IP address.
- Verify reachability using `ping` from your Kali machine.
