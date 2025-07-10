---
created: 2025-07-10
tags:
  - fundamentals
  - essentials
  - documentation
time: 14:28pm
---
---



## 0️⃣ Mapping the network structure
---
> meaning , we want to see which ip addresses contain active hosts and which do not

* to do this , using Nmap to perform called : `ping sweep`
	
	* Nmap sends ICMP packet to each possible IP addresses for the specified *network*
	
	*  when it receives a response , it marks the IP address that responded as `being alive`
	  



* ### ▶️ Performing ping sweep
	* use : `-sn`
	* `nmap -sn 192.168.100.1-254` -or-
	* `nmap -sn 192.168.100.0 / 24` CIDR


* ### ❌ Post ping sweep
	* `-SN` tells nmap not to scan any *ports*
	  
	* forcing it to rely only on **ICMP** echo packets (*to identify targets*)
	  
	* `-sn` switch also cause nmap to send `TCP SYN` packet to port 443 of target (HTTPS)
	  
	* as well as a `TCP ACK` packet to port 80 (HTTP)




## 💁‍♂️Conclusion ?
---
* `-sn` sends ICMP packets to the target , and tags the responded hosts as being alive 
  
* it tells nmap to only rely on ICMP packets 
  
* also sends `TCP SYN` and `TCP ACK` as well depending on the port

* can also include cidr notations 
	* `nmap -sn 172.168.2.1 / 16`
	* the above *Ip address* is **class b** address and usually class b addresses consist cidr of `16`
