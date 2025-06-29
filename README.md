# Task 4 : Setup and Use a Firewall on Windows/Linux

- Objective: Configure and test basic firewall rules to allow or block traffic.
- Tools: Windows Firewall / UFW (Uncomplicated Firewall) on Linux.
- Deliverables: Screenshot/configuration file showing firewall rules applied.

## System Used
- **OS:** Windows 10 / 11
- **Tool:** Windows Defender Firewall with Advanced Security

## Steps Followed

### Step 1: Open Windows Firewall Settings
- Press `Windows + R`, type `wf.msc`, and hit Enter
- This opens **Windows Defender Firewall with Advanced Security**
![image](https://github.com/user-attachments/assets/7fe38374-60a4-49f6-ae8d-19527ef022bb)

---

### 🔧 Step 2: Block Inbound Traffic on Port 23 (Telnet)
1. Click **Inbound Rules** → **New Rule**
![image](https://github.com/user-attachments/assets/68346a38-57d2-481b-9cf8-93a44a370b06)
2. Select **Port**, click **Next**
3. Choose **TCP**, enter port `23`, click **Next**
![image](https://github.com/user-attachments/assets/237afcb1-f67d-4266-bc61-0d63db1190e0)
5. Choose **Block the connection**, click **Next**
6. Select all profiles (Domain, Private, Public), click **Next**
7. Name the rule **"Block Telnet Port 23"** → click **Finish**

---

## Testing the Rule

### Step 3: Enable Telnet (for Testing)
1. Open **Command Prompt as Administrator**
2. Run:
   ```cmd
   dism /online /Enable-Feature /FeatureName:TelnetClient
```

![image](https://github.com/user-attachments/assets/b0a90b23-9a2c-4490-a541-9c41ee53fcf1)

### Step 5: Test Port 23 Block
Run this in Command Prompt:
```cmd
telnet localhost 23
```
If firewall is correctly blocking the port:
- Connection fails or times out
- No Telnet banner or prompt appears

![image](https://github.com/user-attachments/assets/810cf688-38a5-4523-a65f-dc9dfb68a821)

## What I Learned
- How to configure inbound firewall rules
- How to block and test traffic on specific ports
- Basics of network traffic filtering and service hardening
