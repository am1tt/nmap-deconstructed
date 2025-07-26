## Flowchart


```

                       [ Start ]
                           |
                    What is the goal?
                           |
   ------------------------------------------------
   |                                              |
 [Detect Live Hosts]                         [Scan for Services]
   |                                              |
 [Ping Scan (-sn)]                          What info do you need?
                                             /              \
                                  [Open Ports]         [Version & OS]
                                     |                     |
                          [TCP SYN Scan (-sS)]    [Aggressive Scan (-A)]
                                                       |
                                           [Version (-sV) + OS (-O)]
                                                       |
                                         Need Stealth or Firewall Bypass?
                                                       |
                                 ------------------------------------------
                                 |                                        |
                         [UDP Scan (-sU)]                       [Idle Scan (-sI)]
                                 |
                    Want full port range or top ports?
                       /                          \
            [-p- (All 65535)]           [--top-ports 100]

```
