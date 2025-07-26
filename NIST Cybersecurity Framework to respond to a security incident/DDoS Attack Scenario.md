# DDoS Attack Scenario 
_______________________

## What Happened
The company was hit by a **DDoS attack** that lasted for two hours. During the attack, our internal network stopped working because it was flooded with ICMP packets (basically, a lot of fake network traffic). This made it impossible for employees to use internal systems.

=============================================================================

## How We Reacted
Our incident response team acted quickly:
- We blocked all incoming ICMP packets.
- Shut down any non-essential services to reduce load.
- Brought the important services back online first.

=============================================================================

## What Caused It
After we looked into it, we found the problem was an **unconfigured firewall**. This allowed a hacker to send a flood of ping requests (ICMP packets) and crash our network.

=============================================================================

## What We Did to Fix It
To prevent this from happening again, we made the following changes:
- Added a **firewall rule** to limit ICMP traffic.
- Enabled **IP address checks** to stop fake addresses from getting in.
- Installed **network monitoring software** to alert us about weird traffic.
- Set up an **IDS/IPS system** to detect and block harmful ICMP traffic.

=============================================================================

## Why It Matters
This event showed us that small misconfigurations can cause big problems. Now, we’re more prepared, and we’ve improved our systems to catch and stop this kind of attack faster in the future.



