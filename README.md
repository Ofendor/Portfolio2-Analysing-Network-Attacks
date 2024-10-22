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

<pre><code style="color: #ff3f31;">Portfolio Activity 2 - TCP protocol and Wireshark log analysis</code></pre>

In this project, I used the information learned from known network attacks like **DoS Attack, DDoS, SYN Flood Attacks**, **Ping of Death**, and more. I also referenced material provided by:

- [CISA: Understanding and Responding to Distributed Denial-of-Service Attacks (2024)](https://www.cisa.gov/sites/default/files/2024-03/understanding-and-responding-to-distributed-denial-of-service-attacks_508c.pdf)
- [NIST SP 800-61r3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management 2024 (pages 21, 29, 33, 39)](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r3.ipd.pdf)

Understanding how attacks impact networks from the target's perspective helped me troubleshoot issues and respond in time, taking the right steps to mitigate damage and protect the network from future attacks.
  
<p style="font-size: 12px; font-style: italic; color: #4a4a4a;">
  All portfolio items represent fictional companies, IP addresses, websites, and emails, used strictly for educational purposes; and provided hands-on experience in real-world cybersecurity practices.  
</p>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Activity Overview</p>
In this scenario, working as a security analyst for a travel agency that advertises sales and promotions on the company's website, I receive an automated alert from a monitoring system (**Wireshark**) indicating a problem with the web server. I attempt to visit the company's website, but I get the message: "timeout error". After using a packet sniffer to capture data packets in transit to and from the web server, I noticed a large number of **TCP** **SYN** **requests** coming from an unfamiliar IP address.

![Wireshark Report - SYN Flood Attack](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack.png)

![Wireshark Report - SYN Flood Attack part 1](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack%20part%201.png)

![Wireshark Report - SYN Flood Attack part 2](https://raw.githubusercontent.com/Ofendor/Portfolio2-Analysing-Network-Attacks/refs/heads/main/Wireshark%20report%20-%20SyN%20Flood%20Attack%20part%202.png)


<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Report</p>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Key Takeaways</p>


