
---

## 📁 PHASE2/splunkSIEM.md

```markdown
# Phase 2: SIEM Setup and Attack Visualization

## Splunk Installation

```bash
wget -O splunk-9.3.2.deb https://download.splunk.com/products/splunk/releases/9.3.2/linux/splunk-9.3.2-d8bb32809498-linux-2.6-amd64.deb
sudo dpkg -i splunk-9.3.2.deb
sudo /opt/splunk/bin/splunk start --accept-license
