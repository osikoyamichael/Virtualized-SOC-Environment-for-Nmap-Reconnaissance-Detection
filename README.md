# Firewall Port scan Detection Lab (splunk + UFW)                                                                                  
## Overview
This project demostrates decttion of TCP SYN recconaissance activity using UFW firewall logs ingested into splunk. 
## Lab Environment 
- Ubuntu server (UFW enabled)
- Kali linux (attacker machine: nmap scan)
- splunk Enterprise (log analyzer)
- Log source: /var/log/ufw.log                                                                                                                                                                                                                                                                                                                  
## Attack Simulation
Nmap SYN scan executed from kali linux against ubuntu server
- Nmap -sS -Pn -T4 -Sv 192.168.58.101                                                                                  
## Detection Logic 
The detection identifies:
- Mutiple unique destination ports targeted by a single source IP.
- Repeated TCP SYN attemps within a short timeframe.                                                                                                                  
## MITRE ATT&CK Mapping
- Tackic: Discovery
- Techniques: Active Scanning (T1595)
## Outcome
Detection successfully identified reconnaissance activity and generated alert in splunk dashboard.                      
## Lessons Learned 
- Importance of threshold tuning in small lab environments.
- Firewall logs provide limited visibility without IDS
- Detection threshold must match traffic volume.                                                                                                                                                                                                                                                         
