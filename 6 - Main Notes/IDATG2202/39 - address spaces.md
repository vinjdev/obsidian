24/09/24 11:03
Fag: [[IDATG2202]]
Tags: [[NTNU]]
___

# 39 - address spaces
multiprogrammering - flere programmer i minne samtidig

time sharing - pc må kunne dele fysiske resurssene
før et program om gangen

et addresse rom må være trasperang
operativ systemet, må sette dem på rikitg plass, vi ser dette som abstraksjon

globale variabler ligger mellom text og heap
![[Pasted image 20240924120817.png]]
heap er dynamisk
alt annet er statisk. er ferdig compilert


## API
vanlig varibler, blir lagt på stakken
LOKALE skjer dette med.


malloc allokerer minne, spør om størrelsen på datatypen.
malloc returner en *void pointer*

DERFOR VI BRUKER CAST
```c
(int *) malloc (sizeof(int));
```


må manuelt bruke free()

```c
int *x = (int *) malloc (sizeof(int));
...
free(x);
```


brukes 48 bits av 64 bits på addresser. bare 12 hexdeciamel tall. OS tar en del av dette. derfor ser vi også at processer starter på tallet 7

heap er en god del lengre ned. vil nok starte på tallet 5 eller noe

gdb vil ikke se memory leaks her
```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[]) {
    printf("location of code : %p\n", main);
    printf("location of heap : %p\n", malloc(100e6));
    int x = 3;
    printf("location of stack: %p\n", &x);
    return 0;
}
```

bruk valgrind for dette
```bash
valgrind --leak-check=yes ./program
```


## segmenter minne
eget addresse rom for *text stakk og for heap*

har flere segmenter i minne





# reviews

### 4
VPN er lik page tallet

vpn = 20000/4096 = 4
offset = 20000%4096 = 3616

vpn = 32769/4096 = 8
offset 32769 % 1

20000/8192 = 2.44 = 2
20000%8192 = 3616

32769/8192 = 4
32769%8192 = 1

# Referanse
