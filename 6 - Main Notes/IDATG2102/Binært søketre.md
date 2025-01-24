02/10/24 12:39
Fag: [[IDATG2102]]
Tags: [[NTNU]]
___

# søkeing

## sekvensiell søk (usortert søk)
```c++
int sokSekvensielt(const int arr[], const int verdi, const int n) {
    int indeks = n + 1;                       //  Initierer til ETTER arrayen!
                                              //  Så lenge innenfor arrayen og
                                              //    IKKE funnet, leter videre:
    while (indeks > 0  &&  verdi != arr[--indeks])  ;   //  NB:  TOM INNMAT !!
    return (indeks);                          //  Returnerer indeksen eller 0.
}
```

verdi er et tall vi sjekker er det. n er antall i array
looper til vi finner i en "skuff"

## binert søk  (sortert søk)
```c++
int sokBinert(const int arr[], const int verdi, const int n) {
    int venstre = 1,                       //  Initierer venstre og høyre
        hoyre = n,                         //    yttergrenser for søkeområdet.
        midten;                            //  MIDTEN av dette søkeområdet.

    while (venstre <= hoyre) {       //  Fortsatt noe å søke i, og IKKE funn:
        midten = (venstre + hoyre) / 2;    //  Regner ut/finner midtpunktet.
                                                     //  Er dette den søkte?
        if (verdi == arr[midten])  return midten;    //  Returnerer indeks.
                                     //  Befinner seg i venstre/høyre halvdel?
        if (verdi < arr[midten])  hoyre = midten - 1;  //  Oppdaterer aktuell
        else venstre = midten + 1;                     //    yttergrense.
    }
    return 0;                        //  Ikke funnet:  returnerer 0 (null).
}
```
når vi vet at er sortert. Kan vi kutte listen i 2
- vet at midten er større eller lik verdi

*halverer* hele tiden.

## Binært søketre

tre med map som datastruktur i en klasse. kan
```c++
template <typename Data, typename MerData>  //  Vanlig også med 'T', 'T2', ...
class BST {
  private:
      struct Node {                   //  Nodene i det binære søketreet.
          Data data;                  //  ID/key.
          MerData merData;            //  Tilleggsdata/-info til IDen/keyen.
          Node* left, * right;        //  Peker til venstre/høyre subtre/barn.
                                      //  Constructor:
          Node(const Data d, const MerData md)  {  data = d;  merData = md;
                                                   left = right = nullptr;  }
      };

      Node*  hode;       //  Dummy-hode, der 'hode->right' er treets rot !!!!!
                         //  Hensiktsmessig å ha når rota selv skal slettes.

      void traverserInorder(Node* node) const {
          if (node) {
             traverserInorder(node->left);
             cout << '\t' << node->data;    //  Skriver nodens data/ID/key.
                   if (node->left)          //  Skriver evt. venstre barn:
                           cout << "    V.barn: " << node->left->data;
                   if (node->right)         //  Skriver evt. høyre barn:
                           cout << "    H.barn:    " << node->right->data;
             cout << '\n';
             traverserInorder(node->right);
          }
      }

  public:
     BST() {                //  Initierer 'hode' - ut fra datatypene:
       hode = new Node(Data(), MerData());
     }

     ~BST()  {    /*  delete <hele treet>   */    }


     void display() const {                 //  Skriver inorder ut HELE treet:
        traverserInorder(hode->right);      //  Starter i den reelle roten.
    }

                  //  Setter inn 'verdi' med tilknyttet 'merData' inn i treet:
     void insert(const Data verdi, const MerData merData) {
       Node * mor = hode,            //  Mor til 'node' (henger hakket etter).
            * node = hode->right;

       if (node) {                   //  Er MINST en node/rot der allerede:
          while (node) {             //  Blar til der skal settes inn NEDERST:
             mor = node;             //  'mor' følger etter.
                                     //  'node' leter videre nedover:
             node = (verdi < node->data) ? node->left : node->right;
          }
          node = new Node(verdi, merData);          //  Lager ny som skal inn.
          if (verdi < mor->data)  mor->left = node; //  Hekter inn til v.
          else mor->right = node;                   //    eller h. ift. 'mor'.
       } else                        //  1.noden i treet (rota):
          hode->right = new Node(verdi, merData);
     }

                                          //  Fjerner og returnerer (om mulig)
     bool remove(const Data verdi) {      //    node med IDen 'verdi':
       Node *morFjernes, 	              //  "Mora" til 'fjernes'.
            *fjernes, 	                  //  Den som skal removes/slettes.
            *morEtterfolger,              //  "Mora" til 'etterfolger'.
            *etterfolger;		          //  Den SEKVENSIELT etterfølgende.

       morFjernes = hode;                 //  Initierer 2x pekere:
       fjernes = hode->right;
                                          //  Blar seg fram til 'verdi'(?):
       while (fjernes  &&  verdi != fjernes->data) {
           morFjernes = fjernes;          //  'morFjernes' hopper etter.
                                          //  'fjernes' blar venstre/høyre:
           fjernes = (verdi < fjernes->data) ? fjernes->left : fjernes->right;
       }

       if (!fjernes)  return false;       //  Noden ble IKKE funnet.

       etterfolger = fjernes;    //  'fjernes' ER noden som skal slettes !!!
                                 //  CASE 1: =================================
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

       return true;                    //  Noden funnet og fjernet.
     }

                                  //  Leter etter node med 'data' lik 'verdi'.
                                  //  Om mulig returneres dens 'merData':
     MerData search(const Data verdi) const {
         Node* node = hode->right;             //  Initierer til rota.
        while (node  &&  node->data != verdi)  //  Leter til funn eller bunns.
              node = (verdi < node->data) ? node->left : node->right;

        if (node) return node->merData;     //  Funnet - 'merData' returneres.
        else return hode->merData;          //  IKKE funnet!
    }
};
```

treverserer inorder. (venstre seg selv og høyre)

# Referanse
