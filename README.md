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

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Report</p>

<a href="https://drive.google.com/file/d/1NFUPLDN4hY7igV8MxEsnM2vxwRaUPtFc/view?usp=sharing" target="_blank">
  <img src="https://www.clipartmax.com/png/small/36-360030_pdf-clipart-free-download-clip-building-materials-symbol-pdf.png" alt="PDF Report" width="24" height="24" />
</a>

<table>
  <tr>
    <th style="text-align:left;"><strong>Summary of the Problem</strong></th>
  </tr>
  <tr>
    <td>Today, we intercepted an alert from our traffic monitoring systems indicating a potential <strong>DoS attack</strong>. 
        We filtered some of the data logs provided by <strong>Wireshark</strong> and discovered the reasons why the systems weren’t responding smoothly. 
        After further investigation, the team concluded that the issues were linked to a <strong>foreign IP address</strong> that had been sending <strong>SYN packet requests</strong>, overwhelming our company’s network. 
        I attempted to visit the company’s website, but my request was denied with the message <strong>“timeout error”</strong>.
        The team decided to take the server offline temporarily so the machine could recover and return to normal operating status. 
        We configured the company's firewall to block the IP address that was sending the attack.
        We are aware that blocking this IP is a temporary solution, as the hacker could employ different techniques, such as <strong>spoofing other IP addresses</strong>, to initiate a new attack.<br>
        <strong>Note</strong>: Network interception attacks work by intercepting network traffic and stealing valuable information, or interfering with transmissions, causing extensive damage to a company’s assets.
    </td>
  </tr>
</table>
<table>
  <tr>
    <th style="text-align:left;"><strong>Website function explained</strong></th>
  </tr>
  <tr>
    <td>When the website visitors try to establish a connection with the web server, there is a three-way handshake that occurs using the TCP Protocol. 
The TCP Protocol is part of the Transport Layer in the TCP/ IP Model, and is in charge of all internet communications that allow two devices to form a connection and stream data. This protocol ensures that the data is reliable and it is transmitted to the destination service without any issues using the ‘Handshake’ process. This ‘Handshake’ consists of the following steps:
From a source IP address, a user sends a request to access systems that possess a different destination IP address. The request consists of a data packet containing a flag called SYN (Synchronisation) located in the header, along with a sequence number that helps facilitate communication.
After receiving the request, the destination IP address replies to the source IP address with another TCP packet carrying the SYN-ACK flag, acknowledging the connection and accepting the request to access the network. It also adds a number to the previous sequence to maintain a proper order during the communication exchange.
The third step finalises the Handshake. In this step, the source IP address sends another data packet back with an ACK flag, confirming that the TCP connection has been successfully established, allowing both systems to begin sending data packets reliably over the network.
    </td>
  </tr>
</table>
A normal transaction between a website visitor and the web server would be like:

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Network Traffic Log</p>
![Normal traffic on a TCP SYN-AKL request](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Normal%20TCP%20SYN%20Protocol%20function%20explained.png)

<table>
  <tr>
    <th style="text-align:left;"><strong>The Attack Explained</strong></th>
  </tr>
  <tr>
    <td>
      According to CISA, a DoS Attack involves a single source used to overwhelm the target system with a flood of traffic or resource-consuming requests. 
      The malicious actor typically uses one computer or a small network to generate the attack. The goal is to render the target system unavailable to its intended users and deny access to resources or services.<br><br>
      A malicious actor can take advantage of the TCP protocol by flooding a server with SYN requests for the first part of the handshake, as shown in the Wireshark captures. 
      If the number of SYN packets is greater than the server resources available to handle them, the server will become overwhelmed and unable to respond. 
      This is a Protocol-Based Attack, also known as a SYN Flooding Attack, that exploits vulnerabilities in the network protocols to disrupt their targets. 
      These types of attacks normally target the bandwidth of the Network Layer from the TCP/IP Domain and the Transport Layer in the OSI Model.<br><br>
      The interactions with the attacker’s IP address 203.0.113.0 are shown in red in the Wireshark graphic. 
      Initially, the SYN requests are answered normally by the web server (log items 52-54). However, the attacker continues sending SYN requests, creating an abnormal environment for the network.<br><br>
      The green colored log entries show the responses to normal visitor traffic, which means that until this point the server is still capable of managing its bandwidth and providing access to the network for the source IP address 198.51.100.14 (check log items 55, 56, 58, 60, 62 in the graphic). 
      In the next rows, the log begins to show the struggles the web service is having to keep up with the number of SYN requests coming in at a rapid pace, generating the following log errors:<br>
      <ul>
        <li>An getaway server message displaying: HTTP/1.1 504 Gateway Time-out (text/html). This error message is sent as a timeout error for the requesting browser. (check log 77)</li>
        <li>An [RST, ACK] packet, a ‘reset, acknowledge’ packet that will show an error message in the browser and will drop the connection.</li>
      </ul>
    </td>
  </tr>
</table>

![Wireshark Report - SYN Flood Attack part 1](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack%20part%201.png)

![Wireshark Report - SYN Flood Attack part 2](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack%20part%202.png)

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Steps to Follow</p>
<p>
  In the event of an issue of this magnitude, there are a series of steps that the organisation should take both during and before the attack to demonstrate its resilience.<br>
  During a DoS attack, we have to focus on how to respond. According to NIST and their Incident Response Recommendations and Considerations for Cybersecurity Risk Management, the main steps to consider are:
</p>
<ul>
  <li><strong>Identify the Attack as soon as possible</strong>: Observe the behaviour of the network and alert the abnormalities shown by traffic analysers to confirm the attack.</li>
  <li><strong>Activate Incident Response Plan if any</strong>: The organisation’s plan will outline the roles and responsibilities of key personnel and communications during the event of an attack.</li>
  <li><strong>Gather Evidence</strong>: Collecting and documenting as much information as possible about the attack will provide useful evidence for reporting the incident to law enforcement or future analysis.</li>
  <li><strong>Implement Traffic Filtering</strong>: Configure the network structure, firewalls, or IDS to filter out malicious traffic.</li>
  <li><strong>Communication</strong>: Communication internally and externally is essential to maintain a clear report to key stakeholders, including employees, customers, vendors, etc.</li>
  <li><strong>Learn from the Attack</strong>: After the situation is resolved, conduct a deep post-incident analysis to understand the attack vectors, patch the affected systems, expose the current vulnerabilities, and learn our lessons. With this information, update whatever is necessary, patch the respective systems to prevent future attacks and strengthen the company’s cybersecurity mindset.</li>
</ul>
<p>
  Since the organisation can’t predict when a DoS attack will occur, it is imperative that our network defenders implement best practices to minimise the potential damage of these types of attacks:
</p>
<ul>
  <li><strong>Risk Assessment</strong>: A proactive approach for risk assessments to determine the vulnerabilities of the organisation and identify the weak points and the potential impact a cyber attack can provoke.</li>
  <li><strong>Network Monitoring and Traffic Analysis</strong>: Tools and Intrusion Detection Systems to identify any abnormality or suspicious traffic patterns.</li>
  <li><strong>Captcha</strong>: Integrating captchas into a website or online service will help differentiate between human users and automated bots.</li>
  <li><strong>Incident Response Plan</strong>: A comprehensive plan to outline steps to be taken in the event of a DoS attack will ensure effective mitigation of the problem using the correct strategies.</li>
  <li><strong>Firewall Configuration</strong>: To filter out suspicious traffic patterns and block traffic from unknown IP addresses. Also, consider implementing rate limitations to prevent overwhelming traffic.</li>
  <li><strong>Patch and Update Systems</strong></li>
  <li><strong>Employee Awareness and Training</strong>: Educating employees about DoS attacks is beneficial for the company, as it helps maintain service availability during an attack.</li>
  <li><strong>Backup and Recovery</strong>: Regular backups are critical in case of a disaster recovery plan to recover quickly after an attack and minimise potential data loss.</li>
</ul>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Key Takeaways</p>
<p>
  In response to today's <strong>DoS attack</strong>, our network analyzers (<strong>Wireshark</strong>) identified traffic anomalies linked to an <strong>unknown IP address</strong>, causing customer service disruptions. As a result, a <strong>SYN flood attack</strong> overwhelmed the company’s network. The temporary solution of configuring the <strong>Firewall</strong> to block the IP address allowed the server to recover, but it is critical that we implement immediate and robust defensive measures to prevent future incidents.<br>
  Moving forward, strategies such as proper <strong>firewall configuration</strong>, <strong>employee training</strong>, regular <strong>backups</strong>, and a comprehensive <strong>incident response plan</strong> are critical to safeguarding information and ensuring availability against future attacks.<br>
  We recommend conducting a <strong>post-incident analysis</strong> to patch vulnerabilities and strengthen resilience against <strong>TCP protocol exploitation</strong> and other similar cyber threats.
</p>
