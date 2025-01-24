30/09/24 11:16
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# Heap
en prooritetskø

fjerner den største

i en graf struktur
![[Pasted image 20240930111912.png]]
ville bli til MOR. hvis den er større
vil alltid fylle opp NIVÅ FØRST

![[Pasted image 20240930112042.png]]
leser i en level order. (leser nivå til nivå)


![[Pasted image 20240930112736.png]]
den vil fylle nivå. 


Når vi fjerner. ALLTID fjerner ROTA. Hvis LIKE alltid venstre
![[Pasted image 20240930112856.png]]
36 forsvinner, mens ny 36 dyttes opp



# Heapsort
array blir sortert bakfra
```c++
void heapSort(unsigned char arr[], int n)  {
    for (int keyNr = n/2;  keyNr >= 1;  keyNr--) //  Arrayen heap-ordnes: !!!
        gHeap.downHeap(arr, n, keyNr);
//                                       display(arr, N);  cout << "\n\n";

    while (n > 1) {                              //  Fortsatt igjen å sortere:
        bytt <unsigned char> (arr[1], arr[n]);   //  Flytter 1. der 'n' er !!!
        gHeap.downHeap(arr, --n, 1);             //  Heap-ordner igjen!
//                                       display(arr, N);
    }
}
```


# Referanse

