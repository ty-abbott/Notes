#python

simple POC for an IDS function to predict port scanning
```
from scapy.all import sniff, TCP, IP
ip_connections = {}
scan_threshold = 10
def packet_callback(packet):
    if packet.haslayer(IP) and packet.haslayer(TCP):
        src_addr = packet[IP].src
        d_port = packet[TCP].dport
        
        if src_addr not in ip_connections:
            ip_connections[src_addr] = set()

        ip_connections[src_addr].add(d_port)

        if len(ip_connections[src_addr]) > scan_threshold:
            print(f"Possible port scanning from {src_addr}")
            ip_connections[src_addr] = set()

sniff(prn=packet_callback, store=0)
```
scapy is pretty easy, I think I may use it for capturing on geoblocker instead
