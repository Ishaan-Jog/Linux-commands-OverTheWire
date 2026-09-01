## Level 15 > Level 16

The password for the next level can be retrieved by submitting the password of the current level to port `30001` on `localhost` using SSL/TLS encryption.  
We can use the `openssl` command to achieve this.  

### Steps
1. Login as `bandit15`.
2. Execute the following command:
   ```bash
   openssl s_client connect localhost:30001 -quiet
   ```
   `s_client` is a TLS/SSL client built into OpenSSL. It helps make the terminal an encrypted connection.
3. Enter the password obtained in the previous level.

### Password for next level
`pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7`
