## Level 13 > Level 14

The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by user `bandit14`. To go to the next level, there is a private SSH key instead of a direct password.  
The private SSH key is stored in `~/ssh.private` file in the `bandit13` server.  
We need to use this file to log into `bandit14`. However, OverTheWire no longer supports logging in to SSH via localhost. Hence, we need to copy the SSH key to our local computer and use it to log on to level 14.  

### Steps
1. Log-in to `bandit13` using normal SSH command and password obtained in previous level.
2. Do `cat ~/ssh.private` and copy the entire contents.
3. Type `exit` to return to local computer, and create a new file with the SSH key.
   ```bash
   nano bandit14_key
   <paste file>
   <save and exit>
   ```
4. The SSH file may not be accessible to us. Hence, change its permissions to allow the `Owner` to read and write the file.
   ```bash
   chmod 600 bandit14_key
   ```
   Command breakdown:
   ```
    600
    │││
    ││└── Others
    │└─── Group
    └──── Owner
    ```
   The `Owner` has the permissions `4 + 2`, representing `read + write`.
5. Use the SSH command to log-in as `bandit14` with the private SSH key.
   ```bash
   ssh -i bandit14_key bandit14@bandit.labs.overthewire.org -p 2220
   ```
   The `-i` option tells SSH which private key file to use for authentication.
6. Once logged in as `bandit14`, verify it using `whoami`.
7. As the user `bandit14` has full access to the password file, we can directly get the password using:
   ```bash
   cat /etc/bandit_pass/bandit14
   ```

### Password for next level
`aaWecNkG4FhxJQxz07uiwzVP6bJiYS65`
