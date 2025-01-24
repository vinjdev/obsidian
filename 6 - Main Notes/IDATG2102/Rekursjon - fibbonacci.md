03/09/24 11:00
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# rekursjon - fibbonacci
*kaller en funjsjon inne i en funksjon*

vanlig rekursjons funksjoner

fakultet

```c++
int fakultet(const int n) {
    if (n <= 1)  return 1;                    //   0!  =  1!  =  1
    return  n * fakultet(n-1);                //   n!  =  n * (n-1)!
}
```


fibbonacci
```c++
int fibonacci(const int n) {
    if (n <= 1)  return 1;                    //  fib(0) = fib(1) = 1
    return (fibonacci(n-1) + fibonacci(n-2)); //  fib(n) = fib(n-1) + fib(n-2)
}

```




# Referanse
