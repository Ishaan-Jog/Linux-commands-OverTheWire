## Level 12 > Level 13

The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed.  
We need to decompress the contents of the file to obtain the password.  

### Steps
1. Create a temporary working directory using `mkdir /tmp/bandit_lv12` and navigate to it.
2. Copy the file to the directory using `cp ~/data.txt .`
3. Revert the hexdump of the file to binary using `xxd -r data.txt > data.bin`
4. <add more>

### Password for next level
`qQYQiHOBPR8zR61qxYqX45quvihF2uzk`
