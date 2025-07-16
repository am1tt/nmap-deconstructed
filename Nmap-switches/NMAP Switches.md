---
created: 2025-06-30T02:35:00
---
----

# Nmap Flags 

### SYN Scan
	-sS
	Performs a TCP SYN scan (stealthy and fast). This is often the default 
	scan type when run as root.

### UDP Scan
	-sU
	Scans UDP ports instead of TCP.

### OS Detection
	-O
	Attempts to detect the operating system of the target.

### Service Version Detection
	-sV
	Detects service version numbers running on open ports.

### Verbose Output
	-v
	Increases verbosity level (shows more detailed output).

### Verbosity Level 2
	-vv
	Maximum verbosity for more in-depth scan details.

### Output in All Formats
	-oA <filename>
	Saves the scan output in 3 formats: normal (.nmap), XML (.xml), and grepable (.gnmap).

### Output in Normal Format
	-oN <filename>
	Saves output in standard readable format.

### Output in Grepable Format
	-oG <filename>
	Saves output in a format suitable for `grep`.

### Aggressive Scan
	-A
	Performs OS detection, version detection, script scanning, and traceroute.

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

### Run Specific NSE Script
	--script <script-name>
	Runs a specific script from the Nmap Scripting Engine.

### Run All "vuln" Scripts
	--script=vuln
	Runs all scripts in the "vuln" category to check for common 
	vulnerabilities.
