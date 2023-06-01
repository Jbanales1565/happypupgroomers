
import socket
from scapy.all import Ether, IP, UDP, sendp

def send_udp_packet(source_ip, source_mac, source_port, dest_ip, dest_mac, dest_port, message):
    ether = Ether(src=source_mac, dst=dest_mac)
    ip = IP(src=source_ip, dst=dest_ip)
    udp = UDP(sport=source_port, dport=dest_port)
    payload = message.encode()

    packet = ether / ip / udp / payload
    sendp(packet, iface='eth0')  # Replace 'eth0' with the appropriate network interface

# Example usage
source_ip = '192.168.1.100'
source_mac = '00:11:22:33:44:55'
source_port = 1234
dest_ip = '192.168.1.200'
dest_mac = 'AA:BB:CC:DD:EE:FF'
dest_port = 5678
message = 'Hello, Mellanox!'

send_udp_packet(source_ip, source_mac, source_port, dest_ip, dest_mac, dest_port, message)
