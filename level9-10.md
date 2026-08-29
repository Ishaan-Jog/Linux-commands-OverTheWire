## Level 9 > Level 10

The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several `=` characters.  

### Command
```bash
strings data.txt | grep "=="
```

The `strings` command extracts printable (human-readable) character sequences.  

### Password for next level
`B0s2khmbT9u0geKuOoVGW3JZKhndE3BG`
