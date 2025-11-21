# Wazuh-SIEM
Home build of WAZUH SIEM using Elastic and Kibana

Short one-line summary of this project and its purpose.  
**Example:** Wazuh SIEM home-lab deployment for network and endpoint monitoring using Elastic Stack.

---

## Overview

**Goals**
- Deploy Wazuh Manager and agents
- Integrate Wazuh with Elasticsearch and Kibana
- Create detection rules and tune alerts
- Validate detections with test scenarios

**Scope**
- Included: Manager, Elasticsearch, Kibana, Agents, basic rules, examples of tuning and troubleshooting
- Excluded: Production-scale deployment hardening, automated backups, commercial integrations

**Audience**
- Home-lab builders, security students, junior SOC engineers
- Expected prior knowledge: basic Linux commands, system admin privileges, familiarity with GitHub

---

## Architecture

Components and data flow of deployment.

- **Components:** Wazuh Manager; Elasticsearch; Kibana; Wazuh agents; Beats (Filebeat, Winlogbeat) 
- **Network and ports:** Documented subnets, firewall rules, and ports used (e.g., 1514/1515, 9200, 5601)
- **Data flow:** How logs move from agents → manager → Elasticsearch → Kibana dashboards

Screenshot:  
![Architecture diagram placeholder](./screenshots/architecture-diagram.png)

Explain the diagram above and any design tradeoffs.

---

## Prerequisites

OS versions, hardware, and network prerequisites used.

- **OS and versions:** e.g., Ubuntu 22.04 (Manager), Windows 10/11 (agents)
- **Hardware (recommended minimum):** 4 vCPU, 8 GB RAM, 50 GB disk for small lab
- **Network:** Manager reachable from agents; ports open as required
- **Credentials and accounts:** Local admin / sudo access; Elasticsearch/Kibana user setup notes

Screenshot:  
![Prereqs screenshot](./screenshots/prereqs.png)

What I'm doing:

![OS Prep and Install](https://imgur.com/qF8OKyh)

---

## Installation and Configuration

Each subsection below should includes the commands that were ran, notes explaining why, and screenshots.

### 1. System updates and basic packages

Commands:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl wget apt-transport-https gnupg jq

