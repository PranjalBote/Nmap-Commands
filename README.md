# Nmap-Commands

WHAT IS NMAP
----------------------------------
Nmap (Network Mapper) is a network scanning tool used for network discovery,
port scanning, service detection, OS detection, and vulnerability assessment.
It is widely used in cybersecurity, SOC operations, penetration testing,
and network administration.

----------------------------------
BASIC SCANNING
----------------------------------
nmap 192.168.1.1
Use: Scans the top 1000 common TCP ports and checks if the host is reachable.

nmap example.com
Use: Scans a domain name and performs DNS resolution.

----------------------------------
MULTIPLE TARGETS AND SUBNET SCAN
----------------------------------
nmap 192.168.1.1 192.168.1.2
Use: Scans multiple specific IP addresses.

nmap 192.168.1.1-50
Use: Scans a range of IP addresses.

nmap 192.168.1.0/24
Use: Scans an entire subnet.

nmap -iL targets.txt
Use: Scans targets listed inside a file.

----------------------------------
HOST DISCOVERY (PING SCAN)
----------------------------------
nmap -sn 192.168.1.0/24
Use: Finds live hosts only without scanning ports.

nmap -Pn 192.168.1.1
Use: Skips host discovery and scans even if ICMP is blocked.

----------------------------------
PORT SCANNING
----------------------------------
nmap -p 22,80,443 192.168.1.1
Use: Scans specific important ports.

nmap -p 1-65535 192.168.1.1
Use: Scans all TCP ports.

nmap -F 192.168.1.1
Use: Fast scan of top 100 common ports.

----------------------------------
TCP SCAN TYPES
----------------------------------
nmap -sS 192.168.1.1
Use: TCP SYN (stealth) scan, fast and commonly used in penetration testing.

nmap -sT 192.168.1.1
Use: TCP connect scan, used when SYN scan is not permitted.

nmap -sA 192.168.1.1
Use: ACK scan to detect firewall rules.

----------------------------------
UDP SCANNING
----------------------------------
nmap -sU 192.168.1.1
Use: Detects UDP services such as DNS, SNMP, and NTP.

----------------------------------
SERVICE AND VERSION DETECTION
----------------------------------
nmap -sV 192.168.1.1
Use: Detects running services and their versions.

nmap -sV --version-all 192.168.1.1
Use: Performs aggressive version detection.

----------------------------------
OPERATING SYSTEM DETECTION
----------------------------------
nmap -O 192.168.1.1
Use: Detects the operating system of the target.

nmap -O --osscan-guess 192.168.1.1
Use: Attempts OS guessing when detection is difficult.

----------------------------------
AGGRESSIVE SCAN
----------------------------------
nmap -A 192.168.1.1
Use: Enables OS detection, service detection, script scanning, and traceroute.
Note: Very noisy and easily detectable.

----------------------------------
NMAP SCRIPTING ENGINE (NSE)
----------------------------------
nmap --script default 192.168.1.1
Use: Runs default safe scripts.

nmap --script vuln 192.168.1.1
Use: Scans for known vulnerabilities.

nmap --script http-enum 192.168.1.1
Use: Enumerates web directories and files.

nmap --script ftp-anon 192.168.1.1
Use: Checks for anonymous FTP login.

nmap --script smb-os-discovery 192.168.1.1
Use: Detects Windows OS and SMB information.

----------------------------------
FIREWALL AND IDS EVASION
----------------------------------
nmap -f 192.168.1.1
Use: Fragment packets to evade firewalls.

nmap --mtu 24 192.168.1.1
Use: Sets custom MTU size for evasion.

nmap -D RND:10 192.168.1.1
Use: Uses decoy IP addresses to hide the real scanner.

nmap --data-length 200 192.168.1.1
Use: Appends random data to packets to evade detection.

----------------------------------
TIMING AND PERFORMANCE
----------------------------------
nmap -T0 192.168.1.1
Use: Paranoid scan (very slow, stealthy).

nmap -T3 192.168.1.1
Use: Normal scan speed (default).

nmap -T4 192.168.1.1
Use: Fast and commonly used scan.

nmap -T5 192.168.1.1
Use: Very fast and noisy scan.

----------------------------------
OUTPUT AND REPORTING
----------------------------------
nmap -oN output.txt 192.168.1.1
Use: Saves scan output in normal text format.

nmap -oX output.xml 192.168.1.1
Use: Saves scan output in XML format.

nmap -oG output.gnmap 192.168.1.1
Use: Saves scan output in grepable format.

nmap -oA scan_results 192.168.1.1
Use: Saves output in all formats.

----------------------------------
VERBOSE AND DEBUGGING
----------------------------------
nmap -v 192.168.1.1
Use: Shows detailed scan progress.

nmap -vv 192.168.1.1
Use: Shows very detailed output.

nmap -d 192.168.1.1
Use: Debugging mode.

----------------------------------
IPV6 SCANNING
----------------------------------
nmap -6 target
Use: Scans IPv6-enabled hosts.


AUTHOR
----------------------------------
Pranjal Bote
Cybersecurity Learner | Networking | Linux | SOC Fundamentals
