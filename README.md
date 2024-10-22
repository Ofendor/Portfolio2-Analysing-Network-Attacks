<a href="https://www.linkedin.com/in/emilio-mardones" target="_blank">
  <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" alt="LinkedIn Badge" width="24" height="24" />
</a>
<a href="https://ofendor.github.io/portfolio1/" target="_blank">
  <img src="https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg" alt="GitHub Badge" width="24" height="24" />
</a>
<a href="https://coursera.org/share/38ab1d68036cb56bc093082ab335d0c1" target="_blank">
  <img src="https://www.clipartmax.com/png/small/219-2198126_contract-education-degree-certificate-diploma-certificate-icon.png" alt="Contract, Education, Degree, Certificate, Diploma, - Certificate Icon @clipartmax.com" width="24" height="24">
</a>
<a href="mailto:random@gmail.com" target="_blank">
  <img src="https://www.clipartmax.com/png/small/31-316827_gmail-icon-gmail-icon.png" alt="Gmail Icon" width="24" height="24">
</a>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Analysing Network Attacks</p>

<pre><code style="color: #ff3f31;">Portfolio Activity 2 - TCP protocol & SYN Handshake log analysis with Wireshark</code></pre>

In this project, I used the information learned from known network attacks like **DoS Attack, DDoS, SYN Flood Attacks**, **Ping of Death**, and more. I also referenced material provided by:

- [CISA: Understanding and Responding to Distributed Denial-of-Service Attacks (2024)](https://www.cisa.gov/sites/default/files/2024-03/understanding-and-responding-to-distributed-denial-of-service-attacks_508c.pdf)
- [NIST SP 800-61r3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management 2024 (pages 21, 29, 33, 39)](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r3.ipd.pdf)

Understanding how attacks impact networks from the target's perspective helped me troubleshoot issues and respond in time, taking the right steps to mitigate damage and protect the network from future attacks.
  
<p style="font-size: 12px; font-style: italic; color: #4a4a4a;">
  All portfolio items represent fictional companies, IP addresses, websites, and emails, used strictly for educational purposes; and provided hands-on experience in real-world cybersecurity practices.  
</p>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Activity Overview</p>
In this scenario, working as a security analyst for a travel agency that advertises sales and promotions on the company's website, I receive an automated alert from a monitoring system (**Wireshark**) indicating a problem with the web server. I attempt to visit the company's website, but I get the message: "**timeout error**". After using a packet sniffer to capture data packets in transit to and from the web server, I noticed a large number of **TCP** **SYN** **requests** coming from an unfamiliar IP address.

![Wireshark Report - SYN Flood Attack](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack.png)

The web server appears to be **overwhelmed** by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of **SYN** **requests**. This gave me a clear indication that the server is under attack by a malicious actor.

The team decided to take the server offline temporarily so that the machine could recover and return to normal operating status. We configured the company's firewall to block the **IP** **address** that was sending the attack. We are conscious that blocking this **IP** is a temporary solution, as the hacker can **spoof** **other** **IP** **addresses** to initiate a new attack.

The next task was to quickly alert the managers about the problem by elaborating a report on the type of attack I discovered and how it was affecting the web server and employees.

![Wireshark Report - SYN Flood Attack part 1](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack%20part%201.png)

![Wireshark Report - SYN Flood Attack part 2](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack%20part%202.png)

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Report</p>

<a href="https://drive.google.com/file/d/1NFUPLDN4hY7igV8MxEsnM2vxwRaUPtFc/view?usp=sharing" target="_blank">
  <img src="https://www.clipartmax.com/png/small/36-360030_pdf-clipart-free-download-clip-building-materials-symbol-pdf.png" alt="LinkedIn Badge" width="24" height="24" />
</a>

| **Summary of the Problem** |
|-------------------------------------------------------------|
| Today, we intercepted an alert from our traffic monitoring systems indicating a potential **DoS attack**. We filtered some of the data logs provided by **Wireshark** and discovered the reasons why the systems weren’t responding smoothly.  
After further investigation, the team concluded that the issues were linked to a **foreign IP address** that had been sending **SYN packet requests**, overwhelming our company’s network. I attempted to visit the company’s website, but my request was denied with the message **“timeout error”**.  
The team decided to take the server offline temporarily so the machine could recover and return to normal operating status. We configured the company's firewall to block the IP address that was sending the attack.  
We are aware that blocking this IP is a temporary solution, as the hacker could employ different techniques, such as **spoofing other IP addresses**, to initiate a new attack.  
**Note**: Network interception attacks work by intercepting network traffic and stealing valuable information or interfering with transmissions, causing extensive damage to a company’s assets. |


<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Key Takeaways</p>


