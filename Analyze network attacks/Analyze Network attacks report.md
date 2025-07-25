# Analyze Network Attacks Report
________________________________

## Scenario

You work as a security analyst for a travel agency that advertises sales and promotions on the company’s website. The employees of the company regularly access the company’s sales webpage to search for vacation packages their customers might like.

One afternoon, you receive an automated alert from your monitoring system indicating a problem with the web server. You attempt to visit the company’s website, but you receive a connection timeout error message in your browser.

You use a packet sniffer to capture data packets in transit to and from the web server. You notice a large number of TCP SYN requests coming from an unfamiliar IP address. The web server appears to be overwhelmed by the volume of incoming traffic and is losing its ability to respond to the abnormally large number of SYN requests. You suspect the server is under attack by a malicious actor.

You take the server offline temporarily so that the machine can recover and return to a normal operating status. You also configure the company’s firewall to block the IP address that was sending the abnormal number of SYN requests. You know that your IP blocking solution won’t last long, as an attacker can spoof other IP addresses to get around this block.

You need to alert your manager about this problem quickly and discuss the next steps to stop this attacker and prevent this problem from happening again.

===========================================================================

## Section 1: Identify the Type of Attack

Based on the connection timeout error and traffic logs, it is highly likely that the web server experienced a **Denial-of-Service (DoS)** attack, more specifically, a **SYN Flood Attack**.

The packet analysis revealed that the web server was being flooded with TCP SYN requests from an unfamiliar IP address. This volume of SYN packets caused the server to become unresponsive to legitimate connection attempts.

A SYN flood attack exploits part of the normal TCP three-way handshake process by sending a succession of SYN requests to a target's system in an attempt to consume enough server resources to make the system unresponsive to legitimate traffic.

===========================================================================


## Section 2: How the Attack Affects the Website

When users try to access the company website, the TCP protocol initiates a three-way handshake to establish a connection:

1. **SYN** — The client sends a SYN (synchronize) message to initiate a connection.
2. **SYN-ACK** — The server responds with a SYN-ACK message to acknowledge the request.
3. **ACK** — The client sends an ACK back to the server, and the connection is established.

During a SYN flood attack:

- The attacker sends a large number of SYN packets to the server.
- The server, trying to respond to each request, allocates resources and sends SYN-ACK messages back.
- The attacker never completes the handshake by sending the final ACK.
- This leaves the server with numerous half-open connections and quickly depletes its resources.

As a result, the server becomes incapable of handling new legitimate connections, leading to timeout errors for regular users and employees trying to access the website.

===========================================================================


## Resolution and Next Steps

- The server was temporarily taken offline to mitigate immediate impact and allow for recovery.
- The IP address generating the malicious traffic was blocked at the firewall level.
- However, this solution is temporary as IP spoofing can be used by attackers to bypass these restrictions.

## Recommendations:
- Implement SYN cookies to prevent resource exhaustion from incomplete handshakes.
- Configure intrusion detection/prevention systems (IDS/IPS) to detect anomalous traffic patterns.
- Consider rate limiting or TCP connection timeout tuning to reduce the impact of SYN floods.
- Explore cloud-based DDoS protection services for scalable defense.



