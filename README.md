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