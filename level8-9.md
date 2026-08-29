## Level 8 > Level 9

The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.  
We need to uniquely sort the contents of the file to obtain the password.  

### Command
```bash
sort data.txt | uniq -u
```

`sort`: Group identical lines together  
`uniq -u`: Filters lines that occur exactly once  

### Password for next level
`EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl`
