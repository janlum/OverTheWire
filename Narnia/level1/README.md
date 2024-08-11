# OverTheWire Narnia Level 1

## Credentials
username: narnia1
password: WDcYUTG5ul


## Writeup
The C program code is shown:
```c
#include <stdio.h>

int main(){
    int (*ret)();

    if(getenv("EGG")==NULL){
        printf("Give me something to execute at the env-variable EGG\n");
        exit(1);
    }

    printf("Trying to execute EGG!\n");
    ret = getenv("EGG");
    ret();

    return 0;
}

```

## Flag
narnia2 password: 
