09/09/24 12:36
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# Interlude process API

*interlude = mellomspill*

Unix system use alot fork() and exec() and wait()


## Fork system call

```c
#include <unistad.h>

```
this is for fork() and getpid()

see p1.c from cpu-api

PID = process identifier
name so unix can identify

fork make an copy of the process. it only comes alive *from WHERE fork()* is called

FORK = *a new process*

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int
main(int argc, char *argv[])
{
    printf("hello world (pid:%d)\n", (int) getpid());
    int rc = fork();
    if (rc < 0) {
        // fork failed; exit
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        // child (new process)
        printf("hello, I am child (pid:%d)\n", (int) getpid());
    } else {
        // parent goes down this path (original process)
        printf("hello, I am parent of %d (pid:%d)\n",
	       rc, (int) getpid());
    }
    return 0;
}

```

parent runs before child process. Its up to the *CPU scheduler*

rc = *return code* or return value
## wait() system call
some times should wait for child, since partent runs first
need wait(). so parent wait for child process to run

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

int
main(int argc, char *argv[])
{
    printf("hello world (pid:%d)\n", (int) getpid());
    int rc = fork();
    if (rc < 0) {
        // fork failed; exit
        fprintf(stderr, "fork failed\n");
        exit(1);
    } else if (rc == 0) {
        // child (new process)
        printf("hello, I am child (pid:%d)\n", (int) getpid());
	sleep(1);
    } else {
        // parent goes down this path (original process)
        int wc = wait(NULL);
        printf("hello, I am parent of %d (wc:%d) (pid:%d)\n",
	       rc, wc, (int) getpid());
    }
    return 0;
}

```

## exec() system call
for WHEN we want to run a program
fork() in p2.c is useful to run same COPIES of program

exec() is for *different* programs

reinitialize the code as a new process for the stack and the heap
os just simply runs the program passing in arguments from the argv.

*DOES NOT CREATE A NEW process* - just transform old currently running

## Why do this??
this is good since:
seperation of fork and exec
- can run code AFTER fork and BEFORE exec
- makes it possible to alter enviroment

## other parts of API

kill(), signals to kill process



# Referanse
p1.c
