---
created: 2025-06-30T02:35:00
---
----

# Nmap Flags 

### SYN Scan
	-sS
	Performs a TCP SYN scan (stealthy and fast). This is often the default 
	scan type when run as root.

### Connect Scan
	-sT
	Performs a full TCP connect scan (slower and more detectable).

### UDP Scan
	-sU
	Scans UDP ports instead of TCP.

### Xmas Scan
	-sX
	Sends packets with FIN, PSH, and URG flags set to test firewall/IDS responses.

### FIN Scan
	-sF
	Sends packets with only the FIN flag set to try to evade detection.

### Null Scan
	-sN
	Sends packets with no flags set to probe how the system responds.

### Ping Scan (No Port Scan)
	-sn
	Only pings the host(s) to determine if they are up, no port scanning.

### OS Detection
	-O
	Attempts to detect the operating system of the target.

### Service Version Detection
	-sV
	Detects service version numbers running on open ports.

### Traceroute
	--traceroute
	Performs a traceroute to discover network paths.

### Script Scanning (NSE)
	-sC
	Runs a default set of Nmap Scripting Engine (NSE) scripts.

### Run Specific NSE Script
	--script <script-name>
	Runs a specific script from the Nmap Scripting Engine.

### Run All "vuln" Scripts
	--script=vuln
	Runs all scripts in the "vuln" category to check for common 
	vulnerabilities.

### Fragment Packets
	-f
	Fragments packets into smaller pieces (used to try to evade firewalls/IDS).

### Decoy Scan
	-D <decoy1,decoy2>
	Sends scans from spoofed IPs in addition to your real one to hide the true source.

### Spoof Source IP
	-S <IP>
	Spoofs the source IP address of your scan traffic.

### Specify Source Port
	-g <port>
	Sets the source port number for the scan.

### Verbose Output
	-v
	Increases verbosity level (shows more detailed output).

### Verbosity Level 2
	-vv
	Maximum verbosity for more in-depth scan details.

### Aggressive Scan
	-A
	Performs OS detection, version detection, script scanning, and traceroute.

### Timing Template (0–5)
	-T<0–5>
	Sets the scan speed/aggressiveness (0 = paranoid, 5 = insane/fastest).

### Timing Template Level 5
	-T5
	Sets the scan speed to the fastest level (very noisy, can cause detection).

### Scan Single Port (e.g., port 80)
	-p 80
	Scans only port 80.

### Scan Port Range (1000–1500)
	-p 1000-1500
	Scans ports from 1000 to 1500.

### Scan All Ports
	-p-
	Scans all 65535 TCP ports.

### Exclude Host(s)
	--exclude <host>
	Skips scanning specific host(s).

### Input from File
	-iL <filename>
	Scans all targets listed in the input file.

### Output in All Formats
	-oA <filename>
	Saves the scan output in 3 formats: normal (.nmap), XML (.xml), and grepable (.gnmap).

### Output in Normal Format
	-oN <filename>
	Saves output in standard readable format.

### Output in Grepable Format
	-oG <filename>
	Saves output in a format suitable for `grep`.

### Output in XML Format
	-oX <filename>
	Saves output in XML format.
