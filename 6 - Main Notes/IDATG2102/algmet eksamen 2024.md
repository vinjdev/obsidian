11/12/24 15:17
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___
# algmet eksamen 2024

# 1
### a)

1 2 3 4 5 6 7 8 9 10
S T R O G A N O F F
S               M
F T R O G A N O S F
  S       M
F A R O G T N O S F
    S     
F A F O G T N O S R
A F
          S   M    
	  O G O N T S R
	  O G O N R S T
      G N O O          
                S T
	
Den er ferdig etter piviot!!!!!

selection sort på 
1 2 3 4 5 6 7 8 9 10
S T R O G A N O F F

Selection finner bare minste verdi, står fast på indeksen sin, og sjekker i med resten av listen
tenk, en for loop for å sjekke minste verdi fra den indeks man er på

insertion sort
1 2 3 4 5 6 7 8 9 10
S T R O G A N O F F

start med t og sjekk om den er "vandre forbi", BAKOVER. tenk at det er ferdig sortert og man inserter


### b)
Heap
		   T
		S     R
      O   G  A   N
    O  F  F

TSROGANOFF
Bare T omtrent som var større

binært tre
		   S
		R	 T
	   O 
	  G O
	 A  N
	 F
	 F                  
	 
                        O
					G       S 
                 AFF   N  OR   T

red black tre
                   O
                 /   \
                G          S
	           / \        / \
	           F  N     O    T
	          //\\\     //
	        A    F     R


## C
OPPGAVE C:
==========
     
    6 stk:
                          C - E
                        /
                      F
                    /   \
              B - A       E - C
            /       \
          /           E - F - C
        D
          \           E - F - C
            \       /
              A - B       C - E
                    \   /
                      F 
                        \
                          E - C

## 2

når W skal fjernes
ingen av to situasjonene gjelder


                  S     
                U    X
			  ...		  Y
		                Z

når d fjernes skal E med blad node legges der

k byttes med H og l skal settes på N

```c++
		if (!fjernes->right)      //  Har ingen HØYERE/STØRRE etterfølger!
          etterfolger = etterfolger->left; // Etterfølger er VENSTRE subtre!
                                 //  CASE 2: =================================
       else if (!fjernes->right->left) {
          etterfolger = etterfolger->right; // Etterfølger er HØYRE subtre!
          etterfolger->left = fjernes->left; //Overtar v.subtre fra 'fjernes'.
       }
                                 //  CASE 3: =================================
       else {                    // MÅ lete MER etter SEKVENSIELL etterfølger:
          morEtterfolger = etterfolger->right; // Initierer 'morEtterfolger'.

          while (morEtterfolger->left->left)   //  Blar til NEST nederste
              morEtterfolger = morEtterfolger->left; //  venstre node:

          etterfolger = morEtterfolger->left;  //  'etterfolger' er noden
                                               //     HELT nede til venstre.
                                               //  Overfører evt høyre subtre:
          morEtterfolger->left = etterfolger->right;  // Har jo IKKE v.subtre!

          etterfolger->left = fjernes->left;   // 'etterfolger' tar 'fjernes'
          etterfolger->right = fjernes->right; //    sin plass.
       }

       delete fjernes;	               	//  'fjernes' removes/slettes/fjernes.

                                        //  Flyttet node ('etterfolger')
                                        //  hektes korrekt under 'morfjernes':
       if (verdi < morFjernes->data) morFjernes->left = etterfolger;
       else morFjernes->right = etterfolger;
```

### b
BF CA CD BA EG GF

		 b      
		f  C    
		G   AD
   C    
  BADE  
  F  G 

"gForeldre"-arrayen etterhvert:

                A  B  C  D  E  F  G
         B F:   -  1  -  -  -  B  -
         C A:   C  1  1  -  -  B  -
         C D:   C  1  2  C  -  B  -
         B A:   C  C  4  C  -  B  -     Weight Balancing
         E G:   C  C  4  C  1  B  E
         G F:   C  C  6  C  C  B  E     Weight Balancing

### C
OPPGAVE C:
==========

    SPURS SNIKER SEG SAKTE ETTER ARSENAL


    Har bokstavfrekvensen:
                    ' '   A   E   G   I   K   L   N   P   R   S   T   U
                k    0    1   5   7   9  11  12  14  16  18  19  20  21
       frekvens[k]   5    3   6   1   1   2   1   2   1   4   6   3   1



    Dette medfører følgende forelder-array:
                    ' '   A   E   G   I   K   L   N   P   R   S   T   U
                k    0    1   5   7   9  11  12  14  16  18  19  20  21
       frekvens[k]   5    3   6   1   1   2   1   2   1   4   6   3   1
       forelder[k]  -34 -32  36  29 -28  31  28 -30 -27 -33 -35  32  27  

                k   27  28  29  30  31  32  33  34  35  36  37  38
       frekvens[k]   2   2   3   4   5   6   8  10  12  14  22  36
       forelder[k]  30 -29 -31  33  34  35 -36  37 -37  38 -38   0


 
    Tegnet som et tre/en trie:                38
                                       /               \
                                   36                      37
                                /      \               /        \
                               E        33            34        35
                                       /  \         /    \     /  \
                                      30   R     31      ' ' 32    S
                                     /  \       /  \        /  \
                                    27   N     K   29      T    A
                                   /  \           /  \
                                  U    P         G   28
                                                     / \
                                                    L   I



    Vi får altså følgende bitmønster:
                 ' '   A  E     G      I    K      L    N     P   R   S    T   U
       freks[k]   5    3  6     1      1    2      1    2     1   4   6    3   1
       bits     101 1101 00 10010 100111 1000 100110 0101 01001 011 111 110 01000
       kode[k]    5   13  0    18     39    8     38    5     9   3   7   12    8
       len[k]     3    4  2     5      6    4      6    4     5   3   3    4    5



    Totalt antall bit i kodet melding blir:
        (5*3) + (3*4) + (6*2) + (1*5) + (1*6) + (2*4) + (1*6) +
        (2*4) + (1*5) + (4*3) + (6*3) + (3*4) + (1*5)   =   124 bits
                                                            ========

# 3
## a
```c++
Node* neste(Node* node) {
	if (node) {
		if (node->left) return node->left
		else return node->right
	}
	else return nullptr;
}
```

## b
```c++
void settNeste(Node* node) {
	if (node) {
		if (gForrige) {
			if (!gForrige->left) {
				gForrige->right = node;
				gForrige->nesteIPreorder = true;
			}
		}
		gForrige = node;
		
		settNeste(Node->left);
	
		if (!node->nesteIPreorder) settNeste(node->right);
	}
	
}
```
preorder  - seg selv venste høyre
postorder - venstre høyre seg selv
inorder   - venstre seg selv høyre


# 4
```c++
void skrivDato(const int dagNr) {
	int dagPerMnd[] = {31,28,31,30,31,30,31,31,30,31,30,31};
	int dag, mnd = 0, sum = 0;

	if (dagNr >= 1 && dagNr <= 365) {
		while(sum + dagerdagPerMnd[mnd] < dagNr)
			sum += dagerdagPerMnd[mnd++];

		dag  = dagNr - sum;
		cout << "datoen er: " << dag << "/" << mnd+1 << "\n";
	}
	else {
		cout << "\nDag nr ikke i intervall\n";
	}
}
```



# Referanse
