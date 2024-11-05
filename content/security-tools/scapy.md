https://scapy.net/

researching this to create simulated network traffic for my geoblocker project(IP information)

this will be good as it will help with learning of the tcp/ip network stack and implementing it. 

scapy looks incredibly powerful - https://scapy.readthedocs.io/en/latest/routing.html
```
from scapy.all import *

# Define a callback function to process each sniffed packet
def packet_callback(packet):
    print(f"Packet captured: {packet.summary()}")

# Sniff packets and apply the callback
sniff(iface="eth0", filter="ip", prn=packet_callback, count=5)
```
might be the way to work on each captured packet 
