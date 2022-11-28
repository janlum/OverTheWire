# OverTheWire Bandit Level 5

## Credentials 
username: bandit5
password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Writeup
The flag was hidden in a file which was human-readable, 1033 bytes in size and non-executable. 

I used the following command to obtain the location of the file. `ls -laR | awk 'if($1 !~ /x/ && $5 == 1033) print $0; else if(/^\//) print $0'`

Another method to do it after reading writeups was to use the `find` command: `find ./ -size 1033c ! -executable`

## Flag
Level 6 Password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
