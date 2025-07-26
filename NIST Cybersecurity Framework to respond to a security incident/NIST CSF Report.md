# NIST Cybersecurity Framework Response: DDoS Incident Report
______________________________________________________________

## Overview of the Incident
Recently, our company experienced a two-hour service disruption caused by a DDoS attack. The attack came through a flood of ICMP packets, which overwhelmed our internal network. As a result, none of our internal systems could communicate properly. After the incident was resolved, we found that the root cause was an unconfigured firewall that allowed unrestricted ICMP traffic.

In this report, I’ve used the NIST Cybersecurity Framework to break down how we handled the incident and how we plan to strengthen our systems moving forward.

===============================================================

## 1. Identify
This stage is all about figuring out what went wrong and where we were vulnerable.

- We discovered that our firewall didn't have any rules in place to handle or limit ICMP traffic.
- There wasn’t a system for verifying the origin of incoming traffic.
- We hadn’t been regularly auditing the configuration of network devices or reviewing who has access to what.
- From this, it's clear we need to start doing regular internal security audits and better keep track of what services and systems are exposed to the internet.

===============================================================

## 2. Protect
Here we looked at what we can put in place to protect our systems going forward.

- We added firewall rules to limit how much ICMP traffic can get through.
- Source IP address verification was turned on, so spoofed packets should be easier to catch.
- We’re now segmenting the network better to keep critical services isolated.
- Our IT staff got a quick refresher on firewall configurations and DDoS threats.
- We’re also reviewing our general policies around keeping the network hardened (e.g., disabling unused services).

===============================================================

## 3. Detect
We had some tools, but they weren’t enough to catch this in time.

- We've now installed traffic monitoring software that can catch abnormal spikes in traffic.
- IDS/IPS tools are in place to catch suspicious ICMP traffic.
- We’re setting up alerts in our logs to catch unusual patterns.
- Routine log reviews are going to become part of our weekly workflow.
- We've also started using automated scanners to check for weak points.

===============================================================

## 4. Respond
Once we figured out what was happening, we had to act fast.

- We blocked incoming ICMP traffic at the firewall.
- Non-essential services were taken offline so the network wasn’t overloaded.
- Our response team worked to identify the attack vector.
- Everything was documented so we can learn from the event.
- We updated our response procedures to include ICMP-based attacks.

===============================================================

## 5. Recover
Getting back to normal was a priority after things settled.

- Services were brought back online in phases to make sure they were stable.
- We checked that there were no backdoors or lingering issues.
- A short meeting was held to discuss lessons learned.
- Our disaster recovery plan was updated to include this kind of incident.
- We’re planning to simulate similar attacks to test how we respond next time.

===============================================================

## 6. Notes / Personal Thoughts
- This incident showed how even one small misconfiguration can have a big impact.
- It’s clear we need to be more proactive with audits and updates.
- Investing in better tools and training will help us stay ahead of future threats.
- Everyone on the team responded well, but we can definitely tighten up our coordination and detection.

===============================================================

## Final Thoughts
While this was a tough experience, it gave us a chance to seriously improve our defenses. By following the NIST framework, we’re turning a reactive fix into a longer-term strategy for network security.


