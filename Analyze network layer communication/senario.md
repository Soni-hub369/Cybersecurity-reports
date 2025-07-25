## 🧠 Scenario Description

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website `www.yummyrecipesforme.com`, and saw the error **“destination port unreachable”** after waiting for the page to load.

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, **tcpdump**, and attempt to load the webpage again.

To load the webpage, your browser sends a query to a DNS server via the **UDP protocol** to retrieve the IP address for the website's domain name; this is part of the **DNS protocol**. Your browser then uses this IP address as the destination IP for sending an **HTTPS** request to the web server to display the webpage.

The analyzer shows that when you send **UDP packets to the DNS server**, you receive **ICMP packets** containing the error message: **“udp port 53 unreachable.”**

=================================================================================

## 📋 tcpdump Packet Log Analysis

In the tcpdump log, you find the following information:

- The first two lines of the log file show the **initial outgoing request** from your computer to the DNS server requesting the IP address of `yummyrecipesforme.com`. This request is sent in a **UDP packet**.
- The third and fourth lines of the log show the **response to your UDP packet**. The **ICMP 203.0.113.2** line indicates that the UDP packet was undeliverable to port 53 of the DNS server.

### 🕒 Timestamp Format:
Each entry starts with a timestamp (e.g., `13:24:32.192571`) which means: 1:24 PM and 32.192571 seconds.

### 🛜 Network Flow:
- Outgoing UDP packet: `192.51.100.15 > 203.0.113.2.domain`
- ICMP Error Response: `203.0.113.2 > 192.51.100.15`

The IP on the left is the **source**, and the one on the right is the **destination**.

### 🧾 Packet Details:
- Query ID: `35084`
- The **plus sign (+)** indicates flags in the UDP message.
- `A?` flag represents a DNS **A record** request (domain to IP mapping).
- ICMP error: `"udp port 53 unreachable"` – implies **no service is listening** on port 53 at the DNS server.

=================================================================================


## ⚠️ Summary

- The **DNS request** to port 53 failed due to the port being **unreachable**.
- All follow-up attempts received the same **ICMP error**.
- The DNS server may be:
  - Down
  - Misconfigured
  - Blocked by a firewall
  - Under a Denial-of-Service attack

=================================================================================


## 🔚 Conclusion

The incident points to a **network-layer DNS protocol failure** due to an unreachable port on the DNS server. This incident was escalated to security engineers for further investigation.

