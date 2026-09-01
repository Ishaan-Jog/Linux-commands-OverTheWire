## Level 16 > Level 17

The credentials for the next level can be retrieved by submitting the password of the current level to a port on `localhost` in the range `31000` to `32000`.  
For this, we need to find out the open ports, find which of them use SSL/TLS, and send the previously obtained password to the correct TLS service to obtain next level's private SSH key.  

### Steps
1. Use the command `nmap -p 31000-32000 localhost` to get a list of open ports (`STATE open`) within the range 31000-32000.
2. Use `nmap`'s SSL detection to detect which ports use SSL/TLS.
   ```bash
   nmap -p 31046,31518,31691,31790,31960 --script ssl-enum-ciphers localhost
   ```
   - `-p` scans the specific ports provided to it.
   - `--script ssl-enum-ciphers`: `nmap` has NSE scripts that can perform special checks. `ssl-enum-ciphers` is one of them that investigates SSL/TLS support on a port.
   If the port supports SSL/TLS, it will return the cipher information.
3. The ports that support SSL/TLS will return their ciphers. Check for each of those ports by using the `openssl` command.
   ```bash
   openssl s_client -connect localhost:31790 -quiet
   ```
4. If it connects without any errors, enter the password obtained in previous level to get the private SSH key for logging-in to the next level.
5. Copy the entire key and create a file on the **local device** with the key.
   ```bash
   nano bandit17_key
   <paste>
   <save and exit>
   ```
6. Change the permissions so that only the Owner can read and write the file. (otherwise the key will be ignored)
   ```bash
   chmod 600 bandit17_key
   ```
7. Use the private SSH key file to log-in to the next level.
   ```bash
   ssh -i bandit17_key bandit17@bandit.labs.overthewire.org -p 2220
   ```

