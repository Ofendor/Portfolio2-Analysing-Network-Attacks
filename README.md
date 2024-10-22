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
In this scenario, working as a security analyst for a travel agency that advertises sales and promotions on the company's website, I receive an automated alert from a monitoring system (Wireshark) indicating a problem with the web server. I attempt to visit the company's website, but I get the message: "timeout error." After using a packet sniffer to capture data packets in transit to and from the web server, I noticed a large number of TCP SYN requests coming from an unfamiliar IP address.

| Color   | No. | Time      | Source          | Destination     | Protocol | Info                                                    |
|---------|-----|-----------|------------------|------------------|----------|---------------------------------------------------------|
| **red** | 52  | 3.390692  | 203.0.113.0     | 192.0.2.1        | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0...               |
| **red** | 53  | 3.441926  | 192.0.2.1       | 203.0.113.0      | TCP      | 443->54770 [SYN, ACK] Seq=0 Win=5792 Len=120...        |
| **red** | 54  | 3.493160  | 203.0.113.0     | 192.0.2.1        | TCP      | 54770->443 [ACK] Seq=1 Win=5792 Len=0...               |
| **green** | 55 | 3.544394  | 198.51.100.14   | 192.0.2.1        | TCP      | 14785->443 [SYN] Seq=0 Win=5792 Len=120...             |
| **green** | 56 | 3.599628  | 192.0.2.1       | 198.51.100.14    | TCP      | 443->14785 [SYN, ACK] Seq=0 Win=5792 Len=120...        |
| **red** | 57  | 3.664863  | 203.0.113.0     | 192.0.2.1        | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0...               |
| **green** | 58 | 3.730097  | 198.51.100.14   | 192.0.2.1        | TCP      | 14785->443 [ACK] Seq=1 Win=5792 Len=120...             |
| **red** | 59  | 3.795332  | 203.0.113.0     | 192.0.2.1        | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=120...             |
| **green** | 60 | 3.860567  | 198.51.100.14   | 192.0.2.1        | HTTP     | GET /sales.html HTTP/1.1                                |
| **red** | 61  | 3.939499  | 203.0.113.0     | 192.0.2.1        | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=120...             |
| **green** | 62 | 4.018431  | 192.0.2.1       | 198.51.100.14    | HTTP     | HTTP/1.1 200 OK (text/html)                             |





<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Report</p>

<p style="color: #1e203b; font-size: 16px; font-weight: bold;">Key Takeaways</p>


