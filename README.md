<h1> <p align="center"> *** SQL Injection ***</h1>

<h2>Description</h2>
This project was designed to simulate a real-world SQL Injection vulnerability in a self-built web environment and demonstrates a layered security approach: detection and prevention using a FortiGate Web Application Firewall (WAF), and centralized monitoring and analysis through a Wazuh SIEM solution.
<br />

<h2></h2>

<b> Objective:</b>

- <b>Understand how SQL Injection works at a technical level</b> 
- <b>Observe how vulnerable applications behave</b>
- <b>Analyze Apache web server logs during exploitation</b>
- <b>Configure a FortiGate WAF to detect and block SQL Injection attempts </b>
- <b>Validate detection capability using wazuh SIEM monitoring</b>

<h2></h2>

<p align="center"> 
SQL Injection Detection & Monitoring Architecture
 <br/>
<img src="https://imgur.com/O0hn0MX.png" height="120%" width="60%"/>
<br />

### 🖥️ Attacker Machine
- Kali Linux
- Manual SQL Injection testing

### 🌐 Web Server (Victim)
- Windows
- Apache
- MySQL
- Vulnerable PHP application

### 🔥 Firewall / WAF
- FortiGate Firewall
- Web Application Firewall (WAF) profile enabled
- SQL Injection signature detection configured

### 📊 SIEM Platform
- Wazuh Server
- Log collection from:
  - Apache access logs
  - Apache error logs
  - FortiGate firewall logs
 
 ## 🧪 Phase 1 – Environment Setup

- Built isolated virtual lab network
- Configured static IP addressing
- Installed Apache and MySQL
- Deployed vulnerable PHP application
- Enabled FortiGate Rules
- Integrated web server and firewall logs into Wazuh


---

## 🧪 Phase 2 – SQL Injection Attack Simulation

The login page was tested locally by injecting the following payload into the **username** field:admin' OR '1'='1' --  



<img src="https://imgur.com/Jpqw147.png" height="120%" width="25%"/>
<img src="https://imgur.com/53V1lVd.png" height="120%" width="25%"/>

---
Testing the article page that contain the follwing info in DB

<img src="https://imgur.com/5b9TE0s.png" height="120%" width="50%"/>

By using the kali machine put to check the vulnerability on web server

<img src="https://imgur.com/094syV7.png" height="120%" width="50%"/>

before applying the waf rule

<img src="https://imgur.com/SgHXfcF.png" height="120%" width="70%"/>

adddd

<img src="https://imgur.com/ilZBZaN.png" height="120%" width="70%"/>

wazuh alert

<img src="https://imgur.com/1npElMN.png" height="120%" width="70%"/>

Observed behavior:
- Application returned database name
- Confirmed lack of input validation
- Verified SQL Injection vulnerability

## 🔍 Key Learning Outcomes

- Deep understanding of SQL Injection mechanics
- Practical WAF configuration experience
- Log analysis skills (Apache + Firewall)
- SIEM integration and alert validation
- Defensive monitoring workflow
- Attack-to-detection lifecycle visibility


## 🚀 Skills Demonstrated

- Web Application Security
- SQL Injection Analysis
- Firewall & WAF Configuration
- SIEM Monitoring (Wazuh)
- Log Analysis & Incident Investigation
- Blue Team Defensive Strategy
- Security Architecture Design

---

## 📚 Future Improvements

- Add brute-force detection scenario
- Add XSS attack simulation
- Integrate Suricata IDS
- Create automated alert playbook
- Expand log correlation rules

## ⚠️ Disclaimer

This project was conducted in a controlled lab environment for educational purposes only. No real systems were targeted.

<h2>Phase 1 </h2>
A vulnerable PHP application was used
 <br/>
<img src="https://imgur.com/21BjABE.png" height="120%" width="60%"/>
<br />
<h2>Phase 2 </h2>
<h2>Phase 3 </h2>
<h2>Phase 4 </h2>
<h2>Phase 5 </h2>
<h2>Phase 6 </h2>
<h2>Phase 7 </h2>
<h2>Phase 8 </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center"> 
TESTE: <br/>
<img src="https://imgur.com/M2tc7e5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
