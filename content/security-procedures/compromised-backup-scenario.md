## The compromised backup problem

### Definition
- The compromised backup problem is defined by me as having backups that contain some level of persistence by hackers. AKA you have backups as far back as August and at some point during that time frame you were compromised and either a backdoor was introduced or malware was deployed. In that time there are backups of your infrastructure that are taken. 

### Solutions
- There is really one direct solution to this problem as I see it and that is to have backups that are older than the point where the persistence or malware was dropped. 
- To figure that out you need to be able to look back on forensics and figure out where and when the attack began. Having good backup policy, location, and data retention is crucial. 


- The smart/preventative solution is to have defense in depth. Having secure boundaries, firewall and network segmentation and patched systems. IDS and IPS, SIEM. Wazuh and an elk stack. Heuristic and signature based analysis. Be able to have enough telemetry and walls up that you know quicker when an attack is happening and you can search back on the events  
