# WINDOWS PRIVELEGE ESCALATION

- start from initial foothold.

## Windows Kernel Exploit

### use Windows-Exploit-Suggester

- scan for exploit :
    https://github.com/AonCyberLabs/Windows-Exploit-Suggester

- exploit Kernel :
    https://github.com/SecWiki/windows-kernel-exploits

## METASPLOIT
### Local Exploit Suggester
for enumerating vulnerabilities on windows system.
1. Have a meterpreter session.
2. send session to `background`
3. run the following command:  `use multi/recon/local_exploit_suggester`
4. `set SESSION  <session id>` (replace `<session id>`).
5. `run`.
6. It will show you all possible exploits that can be used with this session, and what they do.

## User Account Control - UAC Bypass

### UACMe

https://github.com/hfiref0x/UACME


## DUMPING WINDOWS PASSWORD HASHES