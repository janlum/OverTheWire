# OverTheWire Bandit Level 12

## Credentials
username: bandit12
password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

## Writeup
The password was stored inside a file which was a hexdump of a binary which had been compressed multiple times.
I used the `file` command to determine the file type and then used an assortment of decompression techniques to obtain the flag.
The commands I used are shown below.

```bash
# Hexdump reverse
xxd -r data.txt

# gzip and bzip2 decompression
gzip -d file.txt
bzip2 -d file.txt

# tar archive extraction
tar -x -f [archive file]

```

## Flag
Level 13 Password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
