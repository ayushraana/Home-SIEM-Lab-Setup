# Home-SIEM-Lab-Setup
Guide to set a SIEM Lab at home hassel free


### Overview

This project demonstrates how to set up a home lab for Elastic Stack Security Information and Event Management (SIEM) using Elastic's web portal and a Parrot OS virtual machine (VM). Follow this guide to learn how to generate security events, configure an agent to forward data, and query and analyze logs within Elastic SIEM.

---

### Prerequisites

- **VirtualBox** or **VMware**
  - Download VirtualBox: [Oracle VM VirtualBox](https://www.virtualbox.org/)
- Basic knowledge of Linux and virtualization software

---

### Steps

#### 1. Set Up an Elastic Account

1. **Sign Up**: Create a free Elastic Cloud account.
2. **Log In**: Access the Elastic Cloud console.
3. **Start Trial**: Click "Start your free trial" (14 days free).
4. **Create Deployment**: Choose "Elasticsearch" as the deployment type.
5. **Configuration**: Select region and deployment size, then click "Create Deployment."
6. **Finish Setup**: Wait for deployment configuration.

#### 2. Setting Up the Parrot OS VM

1. **Download Kali Linux**: Get the Kali Virtual Machine Edition [(from https://www.kali.org/get-kali/#kali-platforms)]
2. **Create VM**:
   - In VirtualBox or VMware, extract the Kali VM and acces it through virtualbox or VMware
   - Log in with your chosen credentials: Username = kali Password = kali

#### 3. Setting Up the Elastic Agent

1. **Navigate to Integrations**:
   - Log in to Elastic SIEM, go to Kibana menu, and select "Add Integrations."
2. **Search for Elastic Defend**:
   - Find and click "Elastic Defend."
3. **Install Agent**:
   - Follow instructions to install the agent on Kali Linux VM.
   - Run the provided command in Kali Linux terminal.
4. **Verify Installation**:
   - Check agent status: `sudo systemctl status elastic-agent.service`

#### 4. Generating Security Events

1. **Install Nmap**:
   - Run `sudo apt-get install nmap`
2. **Run Nmap Scans**:
   - Execute commands like `sudo nmap <vm-ip>`, `nmap -sS <ip>`, `nmap -p- <ip>`

#### 5. Querying Security Events

1. **Access Logs**:
   - Go to “Logs” tab under “Observability” in Elastic SIEM.
2. **Search Logs**:
   - Use filters like `event.action: "nmap_scan"` or `process.args: "sudo"`.
3. **View Results**:
   - Click “Search” to review logs.

#### 6. Create a Dashboard

1. **Navigate to Dashboards**:
   - Go to “Dashboards” under “Analytics” in the Elastic web portal.
2. **Create New Dashboard**:
   - Click “Create dashboard” and “Create Visualization.”
   - Choose “Area” or “Line” chart.
3. **Configure Metrics**:
   - Set “Count” as vertical field and “Timestamp” as horizontal field.
   - Save the visualization.

#### 7. Create an Alert

1. **Go to Alerts**:
   - Click “Alerts” under “Security” in Elastic SIEM.
2. **Create New Rule**:
   - Click “Manage rules” and “Create new rule.”
   - Choose “Custom query” and set conditions like `event.action: "nmap_scan"`.
3. **Configure Alert**:
   - Name the rule, set severity, and define actions (e.g., email notification).
   - Click “Create and enable rule.”

---

### Conclusion

You’ve successfully set up a home lab using Elastic SIEM with Parrot OS, configured log forwarding, generated and analyzed security events, and created dashboards and alerts.

### Next Steps

- Generate more security events and test alerts.
- Explore additional Elastic SIEM tools for deeper insights.

---

### References and Resources

- [Detailed Walkthrough](https://medium.com/@aali23/a-simple-elastic-siem-lab-6765159ee2b2) by Abdullahi Ali
- [YouTube Tutorial](https://www.youtube.com/watch?v=2XLzMb9oZBI&t=603s) by Gerald Auger

### Resume Bullet Points

- **Elastic Stack SIEM Configuration**: Set up and configured Elastic SIEM in a home lab environment.
- **Security Event Simulation**: Generated and analyzed security events using Nmap.
- **Visualization and Alerting**: Created dashboards and alerts in Elastic SIEM for effective monitoring.

---

### Connect with Me

- [LinkedIn](https://www.linkedin.com/in/ayushranaa/)

Thank you for exploring this guide! Feel free to reach out with any questions or feedback.

---

