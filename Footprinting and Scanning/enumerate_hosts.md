# Network Enumeration
## Finding hosts on subnet
### Nmap ping sweep
`sudo nmap -sn x.x.x.x/24`
### Find alive hosts with fping
`fping -a -g x.x.x.x/24 2>/dev/null > hosts.txt`  
### Remove own IP (should be first line - verify before executing)
`sed -i '1d' hosts.txt`
## scan of ports on live hosts
### Run nmap scan on alive hosts | Top 1k
`nmap -AT4 -iL hosts.txt -oN namp-1k.nmap` 
### Run nmap scan on alive hosts | all ports
`nmap -AT4 -iL hosts.txt -p- -oN namp-all.nmap` 
### nmap vul scan on alive hosts
`nmap --script vuln --script-args=unsafe=1 -iL hosts.txt`
## scan of ports to export for metasploit
### Generating file for metasploit.
`sudo nmap -sS -A -T4 -p- $IP -oX export_for_msf.xml`
### Then, import into metasploit framework
`db_import /home/kali/Desktop/export_for_msf.xml`
