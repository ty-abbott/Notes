## Difference between SYSMON and defualt windows logging

- By default, Windows logging capabilities via Event Viewer are pretty limited.

- Windows Event Viewer is clunky and doesnt quite give great visibility into the processes within your machines. Sysmon gives you that information and the ability to see the network connections happening within your environment. It produces a higher level of monitoring into certain events like process creation, network connections, and changes that may be happening to the file system. Sysmon can detect indicators of compromise, along with Powershell transcription command line logging(link here to other note) will provide enough visibility into processes and their lifecycle and identity. It provides a great breadcrumb trail for incident response  For siem solutions it is critical to have sysmon. 
