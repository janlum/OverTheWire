# OverTheWire Bandit Level 6

## Credentials
username: bandit6
password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Writeup
The flag was located somewhere on the server in a file that was owned by bandit7 and owned by group bandit6 which was 33 bytes in size.

The command I used to obtain the location of the flag utilized awk and recursive ls. Like this: 

`ls -laR var | 
awk '/:$/&&f{s=$0;f=0} 
/:$/&&!f{sub(/:$/,"");
s=$0;f=1;next} NF&&f{ print s"/"$0 }' | 
awk '{if($3 ~ /bandit7/ && $4 ~ /bandit6/ && $5==33) print $0}'`

The middle awk section was obtained from a thread from stack overflow which i don't understand.

After reading some writeups, I found a neater way to do it:
`find / -user bandit7 -group bandit6 -size 33c 2>/dev/null`

The code `2>/dev/null` directs the output from the stream with file descriptor 2 (stderr) into /dev/null which is used to throw away input. Therefore, we can get rid of all the error messages.

## Flag
Level 7 password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
