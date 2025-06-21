# code-alpha-Task4-NIDS-
### 🛡️ CodeAlpha Task 4 – Setting Up NIDS Using Snort on Ubuntu
This project documents the full process of setting up a Network-Based Intrusion Detection System (NIDS) using Snort on Ubuntu, as part of Task 4 in my CodeAlpha Cybersecurity Internship. The NIDS was tested using Kali Linux attacks, successfully detecting malicious scans.

📌 Objective
✅ Install and configure Snort on Ubuntu as a NIDS
✅ Monitor live traffic and detect intrusions
✅ Simulate real attacks using Kali Linux
✅ Validate intrusion alerts and logging

🧠 Steps to Set Up Snort for NIDS on Ubuntu
### 📥 1. Install Gedit (to edit Snort config easily)

# (1) sudo apt install gedit

### 🐍 2. Install Snort

# (2) sudo apt-get install snort -y During installation, you’ll be asked for your HOME_NET IP. You can modify this later if needed.

### ⚙️ 3. Configure snort.conf (set your IP address)
Open the config file in gedit:

# (3)sudo gedit /etc/snort/snort.conf Find the line: ipvar HOME_NET any

## Replace it with:
ipvar HOME_NET [your Ubuntu IP] 💡 You can find your IP with ifconfig or ip a (commonly ens33 interface)

### 🧪 4. Test the Snort Configuration
To verify if everything is working:

# (4)sudo snort -T -c /etc/snort/snort.conf -i ens33

### ▶️ 5. Start Snort in Live Detection Mode!
This command runs Snort in console alert mode:

# (5)sudo snort -A console -q -u snort -g snort -c /etc/snort/snort.conf -i ens33

#### 💣 Simulating Attacks with Kali Linux
On the Kali Linux machine, I performed Nmap scans targeting the Ubuntu system:

1. Null Scan:
nmap -sN [Target IP]

2. Ping Scan (host discovery):
nmap -Pn [Target IP]

✅ The Snort console detected and alerted these scans, proving the NIDS setup is working correctly.


🧠 What I Learned Installing and configuring Snort as a live IDS

Customizing snort.conf with the local network

Running detection on real-time traffic

Simulating threats using Kali Linux

Interpreting console-based intrusion alerts

📜 Credits 🏢 Internship Organization: CodeAlpha

🔐 Task: 4 – NIDS Setup and Attack Simulation

👨‍💻 Role: Cybersecurity Intern

🗓️ Month: June 2025
