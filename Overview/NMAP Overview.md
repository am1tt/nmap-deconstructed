---
created: 2025-07-01T14:41:00
---
---

## 🟢 Port Scanning with Nmap
---
> when scanning a port , remember these are three basic scan *types*

* ### Three Basic Scans in NMAP
	* TCP Connect Scan : `-sT`
	* SYN "Half-open" Scans : `-sS`
	* UDP Scans : `-sU`



## ©️ TCP Connect Scans
---
* TCP scan `-sT` consist of a *three way handshake*

![[Pasted image 20250701150459.png]]

* ### Three Way handshake 
	* three way handshake consist of 3 *stages*
	* 1 : `attacking machine (our)` sends `target server` a *SYN* flag set
	* 2 : the server then acknowledges the packet with a TCP response containing `SYN`flag as well as the sending `SYN/ACK` flag
	* 3 : our terminal `machine` completes the handshake by sending a TCP request with a `ACK` flag set 


## Checking if Port is Closed
---
![[Pasted image 20250701150626.png]]

* NMAP sends a TCP request with *SYN* flag set *Closed port*
* the `target server` respond with a TCP packet called *RST*(reset) flag set 
* by this response , NMAP can establish that the port is closed

> however if the request is sent to an `open port` the target will respond wit ha tcp packet of SYN/ACK flags , nmap then mark this port as being `open` and completes the tcp handshake


## PORT is Open but behind a firewall ? 
---
> what if the port is open but behind a firewall what ? 

* many firewalls are configured to **drop** incoming packets 
* Nmap sends TCP SYN request , and *recieves nothing back*
* this indicates that port is `protected by a firewall` and is filtered
