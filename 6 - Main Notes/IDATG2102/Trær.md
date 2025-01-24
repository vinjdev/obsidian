29/08/24 10:27
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___
# Trær
- består av *noder*
- kant
- sti
- rot
- kun en sti
- over
- forelder - barn - barnebarn
- intern node - har minst et barn
- grad - antall barn hver node
- nivå (rot = nivå 1 eller 0)
- dybde - antall kanter fra rota til en node
- høyde - antall kanter fra en node til den fjerneste
- sti lengde - summen av alle stiene fra rot til enhver node
- ordnet/sortert vs ikke sortert
- subtre
- skog
- multiveis tre - flere blad noder fra en node
- binært tre - to barn
- fullt tre alle interne noder har eksakt to barn
- komplett tre - alle bladnodene slutter på samme nivå

har en høyre og venstre side, basert på antall barne en node kan ha
```c++
struct Node {
    char ID;
    Node *left, *right;                    //  Initierende constructor:
    Node(char id)  {  ID = id;  left = right = nullptr;  }
};
```


lese inn for trer
```c++
while ((tegn = cin.get())!= '\n') {         //  Ennå ikke slutt på input:
        while (tegn == ' ')  tegn = cin.get();  //  Skipper alle ' ' (blanke).
        nyNode = new Node(tegn);                //  Lager en ny node.
        if (tegn == '+' || tegn == '*') {       //  Om er INTERN node:
            nyNode->right = stakk.top();   stakk.pop(); //  Hekter på høyre og
            nyNode->left  = stakk.top();   stakk.pop(); //   venstre subtre.
        }
        stakk.push(nyNode);                     //  Push'er (rot)noden.
    }


```


## Preorder
- visit seg selv
- traverser venste
- traverser høyre

venste barn før høyre barn
![[Pasted image 20240829202549.png]]

## inorder
![[Pasted image 20240829202720.png]]
- treverser venste
- visit (seg selv)
- traverser høyre

## Postorder
![[Pasted image 20240829202909.png]]
- traverser venste
- traverser høyre
- visit seg selv
alle barn må være sjekket først

## levelorder
visit alle på nivået
fra øverst
![[Pasted image 20240829203019.png]]




# Referanse
