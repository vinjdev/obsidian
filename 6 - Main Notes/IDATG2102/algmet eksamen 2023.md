09/12/24 15:12
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___
# algmet eksamen 2023


# 1
### a)
S M I T T E V E R N

h:4 i:5 -  SmitTevern   ingenting
h:4 i:6 -  sEittMvern
h:4 i:7 -  seIttmVern    ingenting
h:4 i:8 -  seiEtmvTrn
h:4 i:9 -  ReieSmvtTn
h:4 i:10 - reiesMvttN  inenting skejr

h:1 i:2 - ERiesmvttn
h:1 i:3 - EIResmvttn
h:1 i:4 - EEIRsmvttn
h:1 i:5 - EEIRsmvttn ingenting
h:1 i:6 - eeiRSmvttn
h:1 i:7 - eeimrSVttn ingenting
h:1 i:8 - eeimrSTVtn 
h:1 i:9 - eeimrSTTVn
h:1 i:10 - eeimNRSTTV

*HVIS DET ER PLASS TIL 4 NEDOVER, BLIR FLERE KYER INVOLVERT!!!!!!*


### b)
S M I T T E V E R N

		V
      T   T
    R    S  E    I
   E  M  N

VTTRSEIEMN



binært søketre
1 2 3 4 5 6 7 8 9 10
S M I T T E V E R N

                S
             M      T
            I  R      T
           E  N         V
            E
Bare husk at store skal til høytr og små skal til venstre


2 -3 -4 tre
				     M T
		     E E I   N R S   T T V
*Bare husk at du skal fylle barn først*

RED BLACK trEE

		    M
		  /       \\
		 E           T
        //\\         /     \
        E  I        R        T
				 //\\     // \\
				N    S    T    V

dobbel er lik mor

### C)
merkle tree???
==========

	Merkle-tre med 7 blokker:

                     H(1234+567)
                 /                 \
            H(12+34)            H(56+7)
           /       \           /       \
       H(1+2)    H(3+4)    H(5+6)    H(7)
       /    \    /    \    /    \    /
     H(1) H(2) H(3) H(4) H(5) H(6) H(7)
     ----------------------------------
      B1   B2   B3   B4   B5   B6   B7

## oppgave 2
 
 
 SMITTEVERNET
 ![[Pasted image 20241210171904.png]]
0123456789
-RST-EETEI-V-MNT-

6 - k%6

når det er den samme
hash1 + hash2

*dette er veldig lett
bare ha oversikt over hva bokstavene er i ints
start på 0 og avslutt med k -1*
 
## B
UNION FIND

FA DB DC FC BE CA

	A B C D E F
FA  F
DB 
DC
FC
BE
CA

		 F    
		A D E  
		   B C 

    D
    FBCEA
    
bare husk at hvis en node allerede har en mor, så skal den til den øverste noden som ikke har noe BARN

det skjer path ocmpression når en node skal under et barn
det skjer weight compression når noe skal over



### c)
F = G reel avstand + H euklids algorothme

F =9       G=3  H=6
F =9      G= 6  H=5
F=3       G=9    H=2
F= 11     G= 11 H = 0

# 3
```c++
bool erSosken(const Node* t, const Node* s1, const Node* s2) {
	if (t) {
		return (t->left == s1 && t->right == s2 ||
				t->left == s2 && t->right == s1 ||
				erSoken(t->left,s1,s2) || erSosken(t->right,s1,s2))
			
		else
			return false;
	}
	
}
```

```c++
void kappTreNedentil(Node* t const int verdi) {
	if (t) {
		if (t->left && t->ID >= verdi)
			t->left = nullptr;
		else
			kappTreNedetil(t->left,verdi);
			
		if (t->right && t->ID >= verdi)
			t->right = nullptr;
		else
			kappTreNedetil(t->right,verdi);
		
	}
}
```

# 4
```c++
char forsteSingleBokstav(const char tekst[],const int n) {
	int i,j;
	bool duplikat;

	for (i = 0; i < n; i++) {
		duplikat = false;
		for (j = 0; j<n;j++) {
			if (i !=j && tekst[i] == tekst[j]) {
				duplikat = true;
			}
			if(!duplikat) return tekst[i];
		}
	}
	return (' ');
}
```

```c++
char forsteSingleBokstav(const char tekst[],const int n) {
	int antall[26];

	for (int i = 0; i < 26; i++) antall[i] =0;

	for (int i = 0; i < 26; i++)
		antall[tekst[i]-'A']++;

	for (int i = 0; i < n; i++) {
		if (antall[tekst[i]-'A'] == 1) return tekst[i];
		
	return (' ');
}
```



# Referanse
