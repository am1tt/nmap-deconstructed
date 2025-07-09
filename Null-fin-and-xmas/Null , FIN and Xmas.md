---
created: 2025-07-09T15:28:00
tags:
  - nmap
  - fundamentals
  - essentials
---
---


## 0️⃣ Null Scans 
---
> to usen ull scans use : `-sN`

- remember , that when a packet is sent or received it should consist of flag 
  
- the following flags we learned such as  : `SYN , ACK , SYN/ACK , RST , FIN`

* ### [no-flags](screenshots/no-flag.png)  
  
	* `sN` are when TCP request is sent with *no flags* set at all
	  
	* as per RFC , the target host , **should respond wiht a RST flag if port is closed***
	
	  * the above image is an example of it 

---


## 🏁 Fin Scans
---
> for Fin scans the : `-sF`

* ### [Fin-flag](screenshots/fin-flag.png)
  
	* the above screenshot , describes [ FIN ] flag / packet 
	  
	* as said before , usually it happens after sending an *RST packet*
	  
	* `[FIN]` Gracefully close an *active* connection
	  
	* once again **Nmap expects a RST if port is close**


---


## 🎄Xmas Scans
---
> for Xmas scans : `-sX` 

* ### [Xmas scans](screenshots/xmas-scan.png)
	
	 * Xmas send a *malformed* TCP packet and expects an **RST** response for *closed ports*  
	   
	* Xmas scan contains the flag of `( PSH , URG , FIN )` , as mentioned in the above *screenshot*
	
	* expected response from the open ports are as same as the UDP scans 
	  
	* as learned before as well , if the port is *open* but there is no response its same as UDP scans , the port is *open | filtered*
	
	* if the port is filtered by one of these scans , the target responds with ICMP , as same as the closed port
	




## 💁‍♂️Conclusion 
---
* `NULL, FIN, XMAS` TCP port scans are less commonly used though 
  
* all three of them are interlinked
  
* used primarily to **Firewall Evasion**

* they tend to be even stealthier than SYN scans
