# OverTheWire Bandit Level 7

## Credentials
username: bandit7
password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Writeup
The password was stored in the text file next to the word **millionth**. I used awk to obtain the password: `awk '$1 ~ /millionth/ {print $2}'`

## Flag
Level 8 Password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP
