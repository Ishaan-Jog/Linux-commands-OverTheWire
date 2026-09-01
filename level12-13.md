## Level 12 > Level 13

The password for the next level is stored in the file `data.txt`, which is a hexdump of a file that has been repeatedly compressed.  
We need to decompress the contents of the file to obtain the password.  

### Steps
1. Create a temporary working directory using `mkdir /tmp/bandit_lv12` and navigate to it.
2. Copy the file to the directory using `cp ~/data.txt .`
3. Revert the hexdump of the file to binary using `xxd -r data.txt > data.bin`  
   The `xxd` command is used to create and analyze hexadecimal dumps of files.
4. Use the `file` command to check the file type, which would be useful for further decompression.
   ```bash
   $ file data.bin

   # Sample output:
   data.bin: gzip compressed data, was "data2.bin", last modified: Wed Jun 24 14:58:46 2026, max compression, from Unix, original size modulo 2^32 580
   ```
5. As the format of the file is `gzip`, change the extension of the file to `.gz` and use the `gunzip` command to decompress the file.
   ```bash
   mv data.bin data.gz  # rename extension
   gunzip data.gz  # decompress file -> produces a file named 'data'
   ```
6. Run the file command for every decompressed file (output file) until a plaintext ASCII file is obtained.  
   For gunzip (`.gz`): `gunzip filename`  
   For bunzip (`.bz2`): `bunzip2 filename`  
   For POSIX tar archive: `tar -xf filename`  
   Note: The extension of the file needs to be changed only for gunzip files. Not required for other filetypes.  

### Commands executed
```bash
mkdir /tmp/bandit_lv12
cd /tmp/bandit_lv2
cp ~/data.txt .
xxd -r data.txt > data.bin
file data.bin  # gzip output
mv data.bin data.gz
gunzip data.gz  # output file: data
file data  # bzip2 output
bunzip2 data
file data.out  # gzip output
mv data.out data.gz
gunzip data.gz
file data  # POSIX tar archive output
tar -xf data  # output file: data5.bin
file data5.bin  # POSIX tar archive
tar -xf data5.bin  # output: data6.bin
file data6.bin  # bzip2 file
bunzip2 data6.bin  # output: data6.bin.out
file data6.bin.out  # POSIX tar archive
tar -xf data6.bin.out  # output: data8.bin
file data8.bin  # gzip file
mv data8.bin data8.gz
gunzip data8.gz  # output: data8
file data8  # ASCII text
cat data8  # get password
```


### Password for next level
`qQYQiHOBPR8zR61qxYqX45quvihF2uzk`
