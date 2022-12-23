# OverTheWire Leviathan Level 6

## Credentials
username: leviathan6
password: YZ55XPVk2l

## Writeup
This challenge was a basic brute-forcing challenge which required a 4 digit-code to open a bash shell for the next level. I used the following bash commands to crack the shell.

```
for CODE in echo {0..9}{0..9}{0..9}{0..9}; do ./leviathan6 $CODE; done;

```

## Flag
Level 7 Password: 8GpZ5f8Hze
