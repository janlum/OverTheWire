# OverTheWire Bandit Level 9

## Credentials
username: bandit9
password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t


## Writeup
The flag was stored in the text file with one of the few human-readable strings which was preceded by several "=" characters. I got the flag using this command:
`strings data.txt| awk '$1 ~ /=/ {print $2}'`

# Flag
Level 10 Password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
