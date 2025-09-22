# Task 1 — Scan Your Local Network for Open Ports (Nmap)

## Objective
Discover open ports and services on devices in the local network to understand network exposure and potential security risks.

## Tools
- **Nmap** (required)
- **Wireshark** (optional, for packet capture)

## Safety Note
Only scan networks and devices you own or have explicit permission to test. Unauthorized scanning can be illegal.

## Environment / Example
- Replace the example network `192.168.1.0/24` with your own subnet if different.
- Commands below assume you run `sudo` when required (root privileges help for SYN/OS detection/UDP scans).

## Commands I used
1. Discover live hosts on the network (host discovery)
nmap -sn 192.168.1.0/24 -oN scan_results/hosts_alive.txt

2. Quick TCP SYN scan across LAN (shows open TCP ports)
sudo nmap -sS -T4 192.168.1.0/24 -oN scan_results/lan_syn_scan.nmap

3. Detailed scan for a single IP (service/version detection + OS guess)
sudo nmap -sS -sV -O -T4 192.168.1.23 -oN scan_results/192.168.1.23_detailed.nmap

4. Full TCP port scan for a single host (all TCP ports)
sudo nmap -sS -p 1-65535 -T4 192.168.1.23 -oN scan_results/192.168.1.23_allports.nmap

5. UDP scan (slower; example ports)
sudo nmap -sU -p 53,67,123 192.168.1.23 -oN scan_results/192.168.1.23_udp.nmap

6. Save all output formats at once
sudo nmap -sS -sV -O 192.168.1.0/24 -oA scan_results/full_local_scan
