## Finding hosts on subnet  
### Find alive hosts with fping
`fping -a -g x.x.x.x/24 2>/dev/null > hosts.txt`  
### Remove own IP (should be first line - verify before executing)
`sed -i '1d' hosts.txt`
### Run nmap scan on alive hosts | Top 1k
`nmap -AT4 -iL hosts.txt -oN namp-1k.nmap` 
### Run nmap scan on alive hosts | all ports
`nmap -AT4 -iL hosts.txt -p- -oN namp-all.nmap` 
### nmap vul scan on alive hosts
`nmap --script vuln --script-args=unsafe=1 -iL hosts.txt`

---
---