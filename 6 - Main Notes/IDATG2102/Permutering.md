17/09/24 10:21
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# Permutering
rekursiv funksjon som printer ut alle mulig  permutasjoner for en liste
Permutasjon er antall kombinasjoner en tall rekke kan fremstå


bytter to tall fra en array
```c++
void bytt(int & tall1, int & tall2) {
    int temp = tall1;           //  Midlertidig (temporary) unnalagring.
    tall1 = tall2;
    tall2 = temp;
}
```

```c++
void roterVenstre(int arr[], const int i, const int n) {
    int venstreVerdi = arr[i];            //  Tar vare på første.
    for (int k = i+1;  k < n;  k++)       //  Roterer (flytter alle ned
        arr[k-1] = arr[k];                //     ETT hakk/indeks).
    arr[n-1] = venstreVerdi;              //  Legger første inn bakerst.
}
```
flytter alt et hakk til venstre

```c++
void permuter(int arr[], const int i, const int n) {
//                       cout << "Permuter: " <<  i << ", " << n << '\n';
    if (i == n-1)                       //  Nådd en ny permutasjon:
        display(arr, n);                //  Skriver ut arrayens innhold.
    else {                              //  Skal permutere:
        permuter(arr, i+1, n);          //  Beholder nåværende nr.'i'.
                                        //    Permuterer resten.
        for (int t = i+1;  t < n;  t++) {
            bytt(arr[i], arr[t]);       //  Bytter nr.'i' etter tur med
                                        //    ALLE de andre etterfølgende.
//                       cout << "Bytt: " << i << " <-> " << t << '\n';
            permuter(arr, i+1, n);      //  For hver av ombyttene: permuterer
        }                               //     resten av de etterfølgende.
//                       cout << "Roter venstre: " <<  i << ", " << n << '\n';
        roterVenstre(arr, i, n);        //  Gjenoppretter opprinnelig array!!!
    }
}
```

all tall skal flyttes



# Referanse
