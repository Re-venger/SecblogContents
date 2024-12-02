

1. Passive - no direct interaction with the target
2. Active - direct interaction with the target




##### Passive
- whois details lookup
- DNS lookup
- Shodan
- gaining public information available such as website , article, news etc.




#### Active
- Physical Access
- social Engineering 
- network infiltration
- scanning 


Nmap - tool for active recon



#### Advanced Port Scan

*Scenario* - these are efficient when used under the stateless firewalls as these only check for the packets with syn flag set in order to make connection attempts.these can fool the firewall but not stateful firewalls 

- Null Scan(sN) - *(Root Prev)* all flags are set to 0. No Response -> port Open or firewall has blocked. Response -> closed Port.
- Fin Scan(sF) - *(Root Prev)* Fin flags is set. No Response -> port Open or firewall has blocked. Response -> closed Port.
- Xmas Scan(sX) - *(Root Prev)* FIN, PSH, URG flags are set simultaneously. 
  No Response -> port Open or firewall has blocked. Response -> closed Port.
- Ack Scans(sA) - *(Root Prev)*  