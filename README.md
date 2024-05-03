# EJPTv2_Notes

## SETTING UP METASPLOIT

### First run

1. make sure postgres is running 

```bash
sudo systemctl start postgresql
```

2. initialize metasploit database

```bash
sudo msfdb init
```

3. launch metasploit console

```bash
msfconsole
```

### After first run

```bash
sudo service postgresql start && msfconsole
```

### Setting global variable in msf

```bash
setg RHOSTS 10.10.10.10
```