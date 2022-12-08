# OverTheWire Leviathan Level 1

## Credentials
username: leviathan1
password: PPIfmI1qsA

## Writeup
There is a suid shell executable in the home directory for leviathan2. However, it requires a password to launch the shell. After reading some writeups, I learned that I have to use `ltrace` to read the function calls. After using ltrace on the program, I see that a `strcmp` function is called with the password "sex". Entering this into the executable launches a suid bash shell for leviathan2 for me to obtain the flag. 

## Flag
Level 2 Password: mEh5PNl10e
