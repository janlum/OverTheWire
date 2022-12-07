# OverTheWire Bandit Level 11

## Credentials 
username: bandit11
password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Writeup
The flag was encoded using ROT13. I used tr and the following command to obtain the flag.

`cat data.txt| tr 'A-Za-z' 'N-ZA-Mn-za-m'`

This command replaces all the characters in the first set with the second set, which are characters 13 indexes away from the characters in the first set.


## Flag
Level 12 Password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
