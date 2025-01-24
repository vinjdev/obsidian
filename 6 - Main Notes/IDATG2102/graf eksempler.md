17/10/24 15:29
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# graf eksempel 1

![[Pasted image 20241017154807.png]]

matrise som inneholder nabo noder.
- de er naboer hvis det er et tall (int) mellom to noder

```c++
bool muligVei(const int fra, const int til, const int hoyde)  {
    int i = 0;                    //  Løkkevariabel - nullstilles!
    bool funnetFrem = false;      //  Funnet/nådd 'til' eller ei.

//    cout << fra << '\n';          //  Enhver node som blir besøkt.
    gKryssSett[fra] = true;       //  Nå er 'fra' besøkt (for godt).

    if (fra != til) {                          //  IKKE nådd fram, og fortsatt
        while (!funnetFrem  &&  i < ANTKRYSS)  {  //  naboer å besøke:
          if (i != fra  &&                     //  Ikke en selv,
              gGatenett[fra][i] != 0  &&       //     er naboer,
              (!gKryssSett[i])  &&             //     naboen er IKKE besøkt
              hoyde <= gGatenett[fra][i])      //     og høyt nok i gata:
                funnetFrem = muligVei(i, til, hoyde); //  Besøker nabokrysset.
          i++;                                 //  Neste nabo.
        }
    } else
      funnetFrem = true;                    //  Funnet fram til aktuelt kryss.

    if (funnetFrem) cout << fra << "  ";    //  Skriver nodeindeks på vei
                                            //    tilbake i rekursjonen.
    return funnetFrem;                 //  Returnerer om funnet frem eller ei.
}
```

har en liste som sjekker om det er besøkt, siden matrisen er symmetrisk

# graf eksempel 2


# Referanse
