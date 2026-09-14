# DoS Incident Analysis — NIST Cybersecurity Framework

## Summary

The company experienced a Denial-of-Service (DoS) attack that caused network services to become unavailable for two hours. During the attack, the network was overwhelmed by a flood of incoming ICMP packets, preventing normal internal traffic from accessing network resources. The investigation determined that a malicious actor sent the ICMP flood through an unconfigured firewall, which allowed the attacker to overwhelm the network.

## Identify

The cybersecurity team investigated the security event and identified an unconfigured firewall as a security gap that allowed a malicious actor to send a flood of ICMP packets into the company’s network. Regular security audits and configuration reviews can help identify similar vulnerabilities before they are exploited.

## Protect

The network security team implemented additional security controls to reduce the risk of similar attacks. These included a firewall rule to limit the rate of incoming ICMP packets and source IP address verification to identify potentially spoofed IP addresses.

## Detect

The company implemented network monitoring software to detect abnormal traffic patterns. An IDS/IPS system was also implemented to identify and filter some ICMP traffic based on suspicious characteristics. These controls can improve the organization's ability to detect similar attacks more quickly.

## Respond

During the incident, the incident management team blocked incoming ICMP packets, took non-critical network services offline, and restored critical network services. These actions helped contain the attack and restore essential network functionality.

## Recover

After containing the incident, affected network services should be restored in a controlled manner while monitoring network traffic for signs of continued malicious activity. The organization should also review the incident and update its security controls and procedures to reduce the likelihood and impact of similar incidents in the future.
