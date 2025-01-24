27/08/24 14:01
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# 36 - Operating System and Processes
what do OS do?
- virtulized physical resources
- manages resources

## design goals
virtualizations - create abstraction
- gir illusjonen at programmet kjører samtidig
performance - minimize overhead
Security - protects
reliability - stability
energy efficient - environment friendly

virtualisere internminne - hver prosess vil få sin egen private adresserom

virtualisere lagring - å lagre filer i et filsystem


program ligger på disk som lastes i minne. En prosess kjører program.

vil søke gjennom alt i filstrukturen, for å finne "strcmp"
```bash
grep -rn strcmp
```

# review
1. 
	1. virtulize physical resources
	2. mangae resources
2. 
 ![[Pasted image 20240902134241.png]]
3. running more than one process simultaneously
4. structured mainteind by the OS. contains information about all active processes. Each process has its own state where details can be found in the table

*argc[0] is the program name itself*

```c
#include <stdio.h>
#include <stdlib.h>


int main(int argc,char *argv[]) {
    if (argc != 3) {
        fprintf(stderr,"wrong use of argc\n");
        exit(1);
    }

    printf("Yo, Im %s and Im at least %s years old", argv[1], argv[2]);
    

    return 0;
    
}

```




# Referanse
compendia ch 2
