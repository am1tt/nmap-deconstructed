---
created: 2025-07-04T13:16:00
---
---

##  ⚙️UDP Connections
---
* Unlike TCP , UDP Connections are *Stateless* 
	* means , rather than making a connection back and forth "handshake" 
	  
	* UDP Connections rely only on *sending packets* to the target (`hoping that they make it)
		* reffer to TCP vs UDP , UDP is Connection-less protocol while TCP is connection oriented

* This makes UDP faster for connections which rely on speed over *quality*
* but the lack of *Ackknowledgement* makes UDP significantly more difficult (and much slower) to scan 
 > Nmap UDP Scan is : -sU

## 📂 Open Filtered port
---
* When a packet is sent to an *Open UDP Port* and it doesn't send the *response*
	* nmap referes to the port as `open | filtered`
	* in other words , port is open , but it could be *Firewalled*

* if it gets a UDP response 
	* which is *unusual*, then the port is marked open , commonly there is no response ,
		* send request one more time , if there is no response then that port is `open | filtered`


## 🔒Closed UDP port 
---
> previously we saw , i some scenario we get , RST packet from server , if close in Tcp scan `-sT`

* in UDP when a packet is sent to a *closed* UDP port 
	* the target responds with an `ICMP (Ping)` packet containing a message that 
		* `PORT IS UNREACHABLE`
		* identifying a *closed port* which nmap marks and move on 



## 🟢 Scanning UDP ports 
---
* ###### when scanning a UDP port
	* nmap sends completely empty requests-- (raw UDP packets)
	* for ports ,which are occupied by well known services
		* it will instead send a protocol-specific *payload* which is more likely to elicit a response ,for which more accurate result can be drawn


## 😓 Remember 
---
`Closed Port Response` : ICMP protocol , (ping)
`Open Port Response (no resp)` : open | openfiltered