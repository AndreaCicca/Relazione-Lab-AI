# Ragionatore in logica proposizionale in avanti e indietro.

Certo un numero di regole
antecedente11 and antecedente12 and ... and antecedente1N -> tes1
antecedente21 and antecedente22 and ... and antecedente2N -> tes2

...

impl((p*q*(-t)),p)

# Check (model checking)

Nota una lista di regole [impl((p*q*(-r)),t), ...] siamo in grado di partire da una condizione iniziale [p,q,-t] siamo in grado di arrivare ad una condizione finale.

check([impl((p*q*(-r)),t), ...], [p,q,-t],[p])

## Forward

Partiamo dalle ipotesi che abbiamo e ingrandiamo l'insieme.

## Consigli

Creare una funzione di supporto in cui dato 2 liste si che controlli che una lista contenga un'altra nel senso insiemistico (subset).

Ci permette anche di verificare se 2 insiemi sono uguali.