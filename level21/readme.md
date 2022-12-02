# OverTheWire Bandit Level 21

## Credentials
username: bandit21
password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

## Writeup
We were directed into the /etc/cron.d/ directory to look for a program being run at regulat intervals by cron. We found that the bandit22 cron file was running a shell script on startup. Catting the shell script gives us the location to a file which stores the flag.

## Flag
Level 22 Password: WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
