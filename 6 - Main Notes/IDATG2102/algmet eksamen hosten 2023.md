12/12/24 15:14
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___
# algmet eksamen hosten 2023

# 1
### a
2 3 * 4 2 * 5 4 + 3 * + + 

### b

```bash
s k a r s n u t e n
1 2 3 4 5 6 7 8 9 10
S k a r S n u t e n
s K a r s N u t e n
s k A r s n U t e n
s k a R s n u T e n
E k a r S n u t S n
e K a r s N u t s N

E K a r s n u t s n
A E K r s n u t s n
A E K R s n u t s n
A E K R S n u t s n
```

### c
                   91
              73          73
            23  49       54  52
          7  19  36 42    49 

73 73 54 23 42 49 52 7 19 36 42
91 73 73 23 49 54 52 7 19 36 42 49

49 73 73 23 49 54 52 7 19 36 42

                    73
              49          73
            23  49       54  52
          7  19  36 42     


replace:
73  49  54  23  49  42  52  7  19  36
54  49  52  23  49  42  49  7  19  36


# 2
### a
S  K  U  R  S  N  U  T  E N
19 11 21 18 19 14 21 20 5 14

t N T N U R S S U t  E  K  t
0 1 2 3 4 5 6 7 8 9 10 11 12

### b
```bash
            A  B  C  D  E  F
     F D:   -  -  -  F  -  1
     A D:   F  -  -  F  -  2     Weight Balancing
     D B:   F  F  -  F  -  3
     C E:   F  F  1  F  C  3
     E B:   F  F  F  F  C  5     Weight Balancing
     A E:   F  F  F  F  F  5     Path Compression
```


    F 
A D B E C 

### c
```bash
     Vi har følgende bitmønster for bokstavene:
                  E     K     R     S     U
                 011   00    11    10   010


     Bitstrømmen utgjør derfor følgende tekst/melding:  "SKURRESKRUE"
```


# 3
## a
```c++
void speilvend(Node* n) {
	if (n) {
		Node* nn = n->left; n->left = n->right; n->right = nn;
		speilvend(n->left);
		speilvend(n->right);
	}
}

void settPosisjoner(Node* n, int p) {
	if (n) {
		Node* n = p;
		sett
	}
}

```

### b
```c++
void speilvend(Node* n, int p) {
	if (n) {
		Node* nn = n->left; n->left = n->right; n->right == nn;
		speilvend(n->left,2*p);
		speilvend(n->rigt,2*p+1);
	}
}
```

### c
```c++
Node* finnNode(int p) {
	Node* n = gRoot;
	if (n) {
		char intBinar[32];
		int slutt = -1;

		while(p) {
			intBinar[++slutt] = (p % 2) ? '1' : '0';
			p/=2;
		}
		slutt--;
		for(int i = slutt; n && i >= 0; i++)
		n = (intBinar[i] == '0') ? n->left : n->right;
	}
	return n;
}
```


# 4
```c++
int antSifre(int n) {
	int antall = 0;
	while(n > 0) {
		antall++;
		n/=10;
	}
	return antall;
}

main

float faktor;
int i,j,ii, forsteSiffer;
bool losning = false;

for (i=1; i <= SLUTT; i++) {
	if (faktor * i == int(faktor*i)) {
		ii ? i;
		for (j = 1; j < antallSifre(i); j++) ii/= 10;
		forsteSiffer = ii;
		for(j=i; j < antallSifre(i; j++) ii*= 10;
		ii = i - ii;
		ii*=10; ii+=forsteSiffer;
		if(faktor * i == 11) {
			cout << faktor << " * " << i << " " << ii << "\n";
			losning = true;
		}
	}
	if (!losning) cout  << "ingen losning\n";
}


```







# Referanse
