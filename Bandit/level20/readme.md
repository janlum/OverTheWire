# OverTheWire Bandit Level 20

## Credentials
username: bandit20
password: VxCazJaVykI6W36BkBU0mJTCM8rR95XT

## Writeup
There was a suid file which allowed us to connect to any port on localhost and read a line from the port. If the port returns the password of the current level, the next level's password is then given.
I used netcat to open a listener port which would print the current level's password when connected. Then I backgrounded the process and connected to the port using the suid file to obtain the flag.

```bash
# Opening a listener port, any free ports can be used
echo "[level password]" | nc -l localhost 6991 &

# Connecting to listener port
./suconnect 6991
```

## Flag
Level 21 Flag: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
