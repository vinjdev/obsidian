12/12/24 12:06
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___
# algmet eksamen 2022

# 1
### a

5 7 + 4 4 * 8 2 + * * 3 6 + * 

### b
1 2 3 4 5 6 7 8 9 10
B A N A N B I L D E
    S           M  

B A D A N B I L N E
        S M      
        
B A D A B E I L N N
B A D A B
S     M
A A B B D
          I L N N
	      I L


### c
1 2 3 4 5 6 7 8 9 10
B A N A N B I L D E

             N
          L       N
        D    E   B    I
       A  B  A    
NLNDEBIABA

# 2
### a

 1. E-0
 2. D-1 A-1 G-2 F-2 (D i MST)
 3. A-1 G-2 F-2     (A i MST) 
 4. F-1 G-2         (Ny F og F i MST)
 5. B-1 C-2 G-2     (B i MST)
 6. G-1 C-1         (G i MST)
 7. C-1             (C i MST)

### b
4  F = 8      G=2 H=6
13 F =10      G=3 H=7
15 F =10      G=5 H=5
25 F =10      G=5 H=5
33 F =10      G=8 H=2

### c

E A D C F B
E A D F C B
E A C D F B

# 3

### a
```c++
bool skrivNivaa(const Node* t, const int n, const int nivaa) {
	if (!t) return false;
	if (n == nivaa) {
		cout << t->ID << "\n";
		return true;
	}
	return (skrivnivaa(t->left,n+1,nivaa)||skrivnivaa(t->right,n+1,nivaa));
}
```

### b
```c++
Node* bygBalansertBST(const int arr[], const int start, const int slutt) {
	Node* nyKode;
	int midt = (start+slutt) / 2;

	if (start <= slutt) {
		nyKode = new Node(arr[midt]);
		nyKode->left = bygBalansertBST(arr,start,midt-1);
		nyKode->right = bygBalansertBST(arr,midt+1, slutt);
		return nyNode;
	}
	else 
		return nulllptr;
}
```

# 4
```c++
int tallene[1000000];
int i,tall, antall,sum;
int storst = -1;
for (i=0; i < 1000000; i++) {
	tall = tallene[i];
	if (tall >= storst) {
		antall++;
		sum += tall;
		storste = tall;
	}
}

cout << sum;
cout << antall;
```

# Referanse
