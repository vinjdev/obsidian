04/09/24 09:43
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# Tretraversering og backtracking
![[Pasted image 20240904095339.png]]
besok printer bare ut
bare å følge de reglene i [[Trær]]


rekursiv 
```c++
void skrivStjerner(int antStjerner, int antBlanke) {
    int i;                               //  Løkkevariabel.

    if (antStjerner >= 1) {              //  Skal fortsatt skrive stjerner:

                                         //  Skriver halvparten så mange
                                         //    stjerner, STARTENDE I SAMME 
                                         //    KOLONNE SOM EN SELV (samme
        skrivStjerner(antStjerner/2, antBlanke);   //  antall blanke):

        for (i = 1;  i <= antBlanke;  i++)   //  Skriver innledende blanke:
            cout << "  ";

        for (i = 1;  i <= antStjerner;  i++) //  Skriver rett antall stjerner:
            cout << "* ";
        cout << '\n';                        //  Skriv linjeskift.

                                             //  Skriver halvparten så mange
                                             //   stjerner ETTERPÅ, STARTENDE       
        skrivStjerner(antStjerner/2,         //   RETT ETTER EGET MIDTPUNKT: 
                      antBlanke + (antStjerner/2));
    } 
}
```

DET ER IKKE EN EVIG REKUSRIV LOOP PGA. første IF setning
vil fortsette etter det.

# Referanse
