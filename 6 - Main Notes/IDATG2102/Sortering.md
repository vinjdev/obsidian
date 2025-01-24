19/09/24 12:13
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# Sortering

## selection sort
selection sort lager en list fra lav til høy
er IKKE STABIL


```c++
void selectionSort(int arr[], const int n) {
    int i, j,                      //  Løkkevariable
        minIndeks;                 //  Indeks for den MINSTE verdien
                                   //    i det intervallet det letes.
    for (i = 0;  i < n-1;  i++) {  //  Går til NEST siste element:
        minIndeks = i;             //  Initierer til FØRSTE av de gjenværende.
        for (j = i+1;  j < n;  j++)    //  Finner minste ETTER nr.'i':
            if (arr[j] < arr[minIndeks])  minIndeks = j;
        bytt(arr[minIndeks], arr[i]);  //  Flytter ned til plass nr.'i'.
    }
}
```
lager en indeks for den minste
sjekker bare to første tallene mot hverandre hele tiden
*tar ett og ett tall om gangen* i den første for loopen, og sjekker i den andre for loopen om det finnes noe mindre verdier

- ikke veldig effektiv, ettersom sjekker samme tall flere ganger

må alltid ha en "flag", derfor trenger man minIndeks, fordi vi FULLFØRER LOOPEN

## Insertion Sort
```c++
void insertionSort(int arr[], const int n) {
    int i, j,                      //  Løkkevariable.
        verdi;                     //  Verdien/elementet som evt.
                                   //    skal flyttes ned/stikkes inn.
    for (i = 2;  i < n;  i++) {    //  Går fra nr.2 og ut arrayen:
        verdi = arr[i];            //  Den som evt. skal flyttes ned.
        j = i;                     //  Initierer til aktuelt element.
        while (arr[j-1] > verdi) { //  Så lenge tidligere er større:
            arr[j] = arr[j-1];     //  Flytter de opp ETT hakk/indeks.
            j--;                   //  Minsker 'j', til støter på
        }                          //    SENTINEL key!
        arr[j] = verdi;            //  Smetter inn der 'j' stanset.
    }
}
```

indeks 0 er alltid mindre enn alle andre. er en SENTINEL KEY
den vi bruker til å sjekke alla andre

starter på indeks to, fordi vi sjekker forrige, og 0 er sentinel
## shellsort

ligner liit på insert sort

```c++
void shellSort(char arr[], const int n) {
    int  i, j, h;                   //  Løkkevariable.
    char verdi;                     //  Verdien/elementet som evt. skal
                                    //    flyttes bakover i subarrayen.
    for (h = 1;  h <= n/9;  h = (3*h)+1)  ;  //  NB: Tom for-løkke !!!
                                    //  Dvs. 'h' = 1, 4, 13, 40, 121, 364, ...
                                    //  Her: 21/9 = 2,  da blir 'h' lik 4 !!!
                                    //  Ved 36 elementer eller LITT flere:
                                    //    36/9 = 4, DA blir h lik 13.
//                                 char tegn;
    while (h > 0)  {                //  Så lenge det finnes subarrayer:

        for (i = h+1;  i < n;  i++) {   //  Går gjennom subarrayene:
            verdi = arr[i];    //  Den som evt. skal flyttes innen subarrayen.
            j  = i;            //  Initierer til aktuelt element.
//                                 skriv("Før", arr, i, j, h, verdi);
                               //  Så lenge er en i subarrayen 'h' plasser
                               //    lengre nede/tidligere og denne er større:
            while (j > h  &&  arr[j-h] > verdi) {
//                                 skriv("Inni - start", arr, i, j, h, verdi);
                arr[j] = arr[j-h]; // Flytter den opp 'h' plasser.
                j -= h;            // Indeks blir den 'h' plasser lengre nede.
//                                 skriv("Inni - slutt", arr, i, j, h, verdi);
            }
            arr[j] = verdi;        //  Smetter på plass der 'j' har stanset.
//                                 skriv("Etter", arr, i, j, h, verdi);
        }
//                             cout << "\n\nH = " << h << " er ferdig !!\n\n";
//                             cin >> tegn;
        h /= 3;               //  'h' minskes til en 1/3-del for hver looping.
    }
}
```

# Referanse
