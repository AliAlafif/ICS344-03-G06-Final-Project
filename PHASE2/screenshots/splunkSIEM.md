# 📊 Phase 2: SIEM Dashboard Analysis

In this phase, we used a **SIEM (Security Information and Event Management)** platform to collect, visualize, and analyze logs from the victim machine. We chose **Splunk** as our SIEM tool to track and investigate the SSH brute-force attacks launched in Phase 1.

---

## 🔧 Splunk Installation and Setup

We installed **Splunk Enterprise v9.3.2** on the Virtual machine to collect and monitor logs from Victim.


### **Installation Commands:**

```bash
wget -O splunkforwarder-9.4.1-amd64.deb "https://download.splunk.com/products/universalforwarder/releases/9.4.1/linux/splunkforwarder-9.4.1-e3bdab203ac8-linux-amd64.deb"

sudo dpkg -i splunk-9.4.1-e3bdab203ac8-linux-amd64.deb
```

**Start Splunk for the First Time:**

```bash
sudo /opt/splunk/bin/splunk start --accept-license
```
![splunk interface](./image/Picture10.png)
![splunk interface](./image/Picture11.png)

---

### **Install and Configure Splunk Universal Forwarder:**

   ```bash
   wget -O splunkforwarder-9.4.1-e3bdab203ac8-linux-arm64.deb "https://download.splunk.com/products/universalforwarder/releases/9.4.1/linux/splunkforwarder-9.4.1-e3bdab203ac8-linux-arm64.deb"
   ```

**Install the Forwarder Package:**
   ```bash
   sudo dpkg -i splunkforwarder-9.4.1-e3bdab203ac8-linux-arm64.deb
   ```
**Start Splunk Forwarder and Accept the License:**
   ```bash
   sudo /opt/splunkforwarder/bin/splunk start --accept-license
   ```

**Verify the Setup**
**Check the Forwarder Status:**
   ```bash
   sudo /opt/splunkforwarder/bin/splunk list forward-server
   ```
![splunk interface](./image/Picture12.png)

- the logs has been sent to Splunk:

![splunk interface](./image/Picture13.png)

---

**Check the logs after the attack**

- As we can see, the number of logs is increased 
![splunk interface](./image/Picture14.png)

- Show the Failed password logs:

![splunk interface](./image/Picture15.png)

-  Visualize the attacks
* index=* "Failed password" | timechart count:
![splunk interface](./image/Picture16.png)

* index=* "Failed password" | stats count by host:
![splunk interface](./image/Picture17.png)


