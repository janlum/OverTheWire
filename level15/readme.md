# OverTheWire Bandit Level 15

## Credentials
username: bandit15
password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt


## Writeup
The flag could be obtained by establishing an SSL connection with port 30001 on localhost and passing in this level's password. I used ssl and s\_client to start a connection.

`ssl s_client -connect localhost:30001 -ign_eof`

The `-ign_eof` flag will not shut down the connection after end of file is reached, allowing us to pass the password to the port.


## Flag
level 16 Password: JQttfApK4SeyHwDlI9SXGR50qclOAil1
