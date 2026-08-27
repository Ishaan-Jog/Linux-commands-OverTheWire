## Level 6 > Level 7

The password for next level is stored in the server (`/`).  
The file is owned by user `bandit7` and owned by the group `bandit6`. It is 33 bytes in size.  
Use filters in the `find` command to filter out this file.

### Command
```bash
find / -user bandit7 -group bandit7 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```

`2>/dev/null` is used to ignore `Permission denied` errors in the output.  

### Password for next level
`Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3`
