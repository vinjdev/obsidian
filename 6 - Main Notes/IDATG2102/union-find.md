31/10/24 13:03
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___
# union-find
*Er node A i samme komponent eller sub graf som node B?*

Har en node en mor, og den skal legge til.
SKAL DEN IKKE I NODE. MEN I ROTEN

![[Pasted image 20241031134753.png]]
J og I lagt til før lagt til i A

![[Pasted image 20241031134814.png]]
D skal på B, men B har en Mor, SÅ *D* GÅR UNDER *A*

H skal over A, fordi B *allerede HAR en MOR*

C ha ikke blitt koblet på enna. Siden D har mor og A har mor.
*skal under H*


Må sende inn grafkanter
"AB", "HG" etc
```c++
bool unionerOgFinn(int nr1, int nr2, const bool unioner) {
    int i = nr1, j = nr2;                         //  Initierer indekser.

    while (gForeldre[i] > 0)  i = gForeldre[i];   //  Finner rot for i/nr1.

    while (gForeldre[j] > 0)  j = gForeldre[j];   //  Finner rot for j/nr2.

    if (unioner && (i != j))  gForeldre[j] = i;   //  Hekter evt. sammen.

    return (i == j);     //  Returnerer om i samme komponent eller ei.
                         //    (Aktuelt KUN når 'unioner' er 'false'
}       

```


# Referanse

