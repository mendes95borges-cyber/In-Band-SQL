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
<img src="https://imgur.com/RKgpcZL.png" height="120%" width="60%"/>
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

To validate the SQL Injection vulnerability, the login page was tested locally using the following payload injected into the username field:  **username** field:admin' OR '1'='1' --  
<p align="center"> 
<img src="https://imgur.com/Jpqw147.png" height="120%" width="25%"/> <img src="https://imgur.com/53V1lVd.png" height="120%" width="25%"/>     
 
 This payload bypassed authentication logic and resulted in a successful login, as shown in the screenshots below. The application loaded login.php without properly validating or sanitizing user input.
By default, the Apache access log does not record how the application processed the submitted credentials. To capture this information, I implemented a custom authentication logging mechanism. This allowed me to record each login attempt, including the injected payload and source IP address.
An excerpt of the authentication log is shown below:

 <p align="center"> 

 <img src="https://imgur.com/WadY7WY.png" height="120%" width="50%"/>

---
  
Database Article Page Testing

In the second phase of the project, I tested another vulnerable component of the web application: the article listing page (artigo.php).
This page retrieves and displays article records directly from the MySQL database without proper input validation or query sanitization.
To illustrate this, the database table articles contains the following sample entries:

Article 1: “Welcome” – This is the first article
Article 2: “Cyber Defense” – Learning SQL Injection and prevention
Article 3: “Security Lab” – Building a vulnerable environment safely
<p align="center"> 
 <img src="https://imgur.com/uxejGPl.png" height="120%" width="50%"/>

so in second phase we will use our kali machine to attack the vulnerable artigo web page without any firewall rule or waf to block the connetion 
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
