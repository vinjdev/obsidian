03/09/24 14:00
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# intro to pointers in c

i assembly finnes ikke variabel - bare addresser til hvor data skal ligge

litt samme med pekere. Peker til en adresse der data ligger

```c
int a = 7
int *p = NULL
printf("%d",a);
printf("%d",p);

```

peker til ingenting (god practice)

printf vil være 0.

hvis
```c
printf("%d",*p);
```
dette er en segmentation fault
*ACCESEREER EN NULL POINTER*

```c
// pekere må peke på en adresse

p = &a
```


# Referanse
https://www.youtube.com/watch?v=4cZn-5i31sI