

# happypupgroomers
project
This is a readmy file on 5/8

from scapy.all import Ether, IP, UDP, sendp

# Define the source and destination MAC addresses
src_mac = "00:11:22:33:44:55"  # Replace with your source MAC address
dst_mac = "AA:BB:CC:DD:EE:FF"  # Replace with your destination MAC address

# Define the source and destination IP addresses
src_ip = "192.168.1.100"  # Replace with your source IP address
dst_ip = "192.168.1.200"  # Replace with your destination IP address

# Define the UDP source and destination ports
src_port = 12345
dst_port = 54321

# Create the Ethernet, IP, and UDP packets
ether_pkt = Ether(src=src_mac, dst=dst_mac)
ip_pkt = IP(src=src_ip, dst=dst_ip)
udp_pkt = UDP(sport=src_port, dport=dst_port)
data = b"Hello, Mellanox switch!"  # Replace with your desired payload

# Combine the packets
packet = ether_pkt / ip_pkt / udp_pkt / data

# Send the packet
sendp(packet, iface="eth0")  # Replace "eth0" with your network interface name
