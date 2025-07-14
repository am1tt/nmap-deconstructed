---
created: 2025-07-14
time: 13:40pm
---
----



## 🗒️Local Storage ( Attacking Machine )
---
> Nmap stores its script on linux at `/usr/share/nmap/scripts`


* ### 🔍 Two ways to search for installed *scripts*

	 #### [Directory Approach](screenshots/directory.png)
	
	* 1 : using `/user/share/nmap/scripts`


	 #### [Grep approach](screenshots/grep.png)
	 
	* 2 : using a grep command to find the respective *script*
	  tip : the same technique can be used to find with a `category` of script
		  `grep "ftp" /user/share/nmap/scripts/script.db`

     #### [List Approach](screenshots/list.png)
      
      * 3 : using a list approach 
	    `ls -al /usr/share/nmap/scripts/*ftp*`


