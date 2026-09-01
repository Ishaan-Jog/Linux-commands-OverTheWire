## Level 17 > Level 18

There are 2 files in the home directory: `passwords.old` and `passwords.new`.  
The password for the next level is in `passwords.new` and is the only line that has been changed between `passwords.old` and `passwords.new`.  
The password can be obtained using the `diff` command.  

The `diff` command is used to compare two files line-by-line.  
It returns the lines which are unique/different in both the files.  

### Command
```bash
diff passwords.new passwords.old
```
The **first** string is the password for the next level.

### Password for next level
`OQxXZjELndr90zuhOTDYBEomI0SZITXI`

Note: If you see a `Byebye !` message when trying to log-in to `bandit18`, that is related to the next level.
