# OverTheWire Leviathan Level 5

## Credentials
username: leviathan5
password: EKKlTF1Xqs

## Writeup
Using `ltrace` on the provided executable, we can see that it opens a file and then prints the contents of the file to stdout. I used `ln -s` to make the file a symbolic link to the password file for the next level to obtain the flag. 


## Flag
Level 6 Password: YZ55XPVk2l

