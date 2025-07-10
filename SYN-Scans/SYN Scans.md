---
created: 2025-07-03T12:13:00
---
---


## ®️ TCP port range ( target )
---
> first before proceeding to SYN scan we have to understand tcp port range of target

* TCP port range of target can be anything between `0 - 65535`
* categorized in to *three ranges*
	* well known : `0 - 1023`
	* registered ports : `1024 - 49151`
	* private ports : `49152 - 65535`

## 🟢 SYN Scans 
---
* As with TCP scans , SYN scans `-sS` are used to TCP *port range* of a `target` or `targets`
* SYN scan is a bit different than TCP Scans
* SYN scans are sometimes referred to as *"Half open"* scans or *"stealth"* scans
---
* where TCP scans performs a `full three-way handshake` with *target*
* SYN Scans sends back a `RST TCP packet` after receiving a `SYN/ACK` from the target server 
  > this prevents the server from repeatedly trying to make a request
----

#### the sequence for scanning an open port looks like this
---
[SYN Scan](SYN-SCAN.png)

* ### ❓why it prevents server from sending request again ?
	* the reason is `RST` tcp packet .
	* when you send an `RST` TCP packet , it abruptly *terminates* a `TCP Connection`
	* it is a way to signal , that the connection is no longer *valid* and should be
	  `Closed immediatly`
	* This contrast with `FIN` (Finish) packet , which gracefully closes the connection after `data is been exchanged`

		can be used for 
			`security` : closing incomming packets
			`error handling` : system crashes and unexpected behavior from server
			`Abrupt connection` : gracefull shutdown `FIN` packet



## 🤔 Why even use SYN Scans ?
---
* Bypass older intrusion detection systems ( `as they are looking for a three way handshake i.e (TCP Scans) -tS)` no longer required due to modem IDS solutions and this why SYN scans are referred as *Stealth* Scans
  
* SYN Scans are often not *logged by* applications listening of `open ports` , because its an `standard practice to log connection after its been established` again , this plays into idea , of SYN Scan being *Stealthy*

	> without having to bother of completing (and disconnecting from) a three way handshake of every port , SYN scans are significantly *faster* than TCP connect scan


## 😓 Disadvantages of SYN Scans 
---
> here we will look the disadvantages of SYN scans
* They require `SUDO permissions` , in order to work correctly in *linux*
	* because SYN scans require an ability to create *raw packets* ( as opposed to full TCP handshake which is a privilege only to a `root user has by default` )

* Unstable services : are sometimes brought down by *SYN scans* , which could prove problematic , if client has provided a `production envoirment` for the test 
---

## 🔄️ Without Sudo permissions
---
> altough pros of syn scan out perform the cons , and that is why it is commonly used than tcp scans

* However if one does not have `sudo permissions` 
	* NMAP defaults to TCP connect scan , because default is SYN Scan , if sudo permissions you have


