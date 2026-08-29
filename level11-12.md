## Level 11 > Level 12

The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions (`ROT13`).  
Use the translate (`tr`) command to decode the password.  

### Command
```bash
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
```

- `tr`: Translator, used to swap/delete specific characters
- `A-Za-z`: Original alphabets (A-Z and a-z)
- `N-ZA-Mn-za-m`: Target alphabet, shifted by 13 positions (A + 13 = N, hence we check `N to A` and then `A to M`)
Basically, it swaps the original alphabets with ROT13 alphabets in the file.

### Password for next level
`GROozWPO8QyN0mGrjUkID0WCYkZiQxrN`
