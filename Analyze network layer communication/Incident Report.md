
# 📡 Network Traffic Analysis Report  
______________________________________

## 📝 Summary

Multiple users reported being unable to access the website `www.yummyrecipesforme.com`. The error message shown was: **“destination port unreachable.”** As part of the investigation, a network packet capture was performed using `tcpdump` to analyze traffic at the network layer.  

The analysis revealed failed attempts to communicate with the DNS server responsible for resolving the website’s IP address. All outgoing **UDP port 53** DNS requests were met with **ICMP error messages** indicating that the destination port was unreachable.

================================================================

## 📊 Traffic Details

### Example Captured Packet Logs:
```
13:24:32.192571 IP 192.51.100.15.52444 > 203.0.113.2.domain: 35084+ A? yummyrecipesforme.com.  
13:24:36.098564 IP 203.0.113.2 > 192.51.100.15: ICMP 203.0.113.2 udp port 53 unreachable length 254
```

### Key Observations:
- **Source IP:** 192.51.100.15 (client machine)  
- **Destination IP:** 203.0.113.2 (DNS server)  
- **Query Type:** DNS A record lookup  
- **Protocol Used:** UDP (port 53)  
- **ICMP Response:** “udp port 53 unreachable”  
- **Timestamps of Error:** From 13:24:32 to 13:28:50

================================================================

## 🔍 Analysis

- The **UDP packets** sent from the browser attempted to resolve the domain via the DNS server.
- Instead of returning the IP address, the **DNS server responded with ICMP messages** indicating that **UDP port 53 was unreachable**.
- This suggests that either:
  - The DNS service on the destination server is **down**
  - Port 53 traffic is being **blocked by a firewall**
  - The server is possibly **under a Denial-of-Service (DoS) attack**
  - Or there's a **configuration issue** on the DNS server

================================================================

## 🧾 Incident Timeline

| Time       | Event                                        |
|------------|----------------------------------------------|
| 13:24:32   | DNS query for `yummyrecipesforme.com` sent   |
| 13:24:36   | ICMP error: UDP port 53 unreachable received |
| 13:26–13:28| Repeated attempts with same ICMP response    |

================================================================

## 🧩 Conclusion

The DNS server `203.0.113.2` is **unresponsive on port 53**, causing DNS resolution to fail. As a result, users cannot access the website `www.yummyrecipesforme.com`. The issue is network-layer related and involves either a service outage, firewall misconfiguration, or a potential attack.

================================================================

## 🔧 Recommended Next Steps

1. Verify DNS server `203.0.113.2` is running and listening on port 53.
2. Check firewall or router rules blocking inbound/outbound DNS traffic.
3. Investigate potential DoS activity targeting port 53.
4. Switch to a backup DNS server if available to restore access temporarily.


