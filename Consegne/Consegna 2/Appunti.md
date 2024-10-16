# Consegna 2 Pianificazione

Partiamo dallo stato del mondo iniziale e vogliamo arrvare allo stato del mondo Goal.

Azioni:
- Prendo il blocco 3 e lo metto sul tavolo
- Prendo il blocco 2 e lo metto sul blocco 3
- Prendo il blocco 1 e lo metto sul blocco 2
- Rilascio tutto e ho la mano libera -> Condizione finale perchè ho 3 blocchi in pila e la mano libera.

## Stati
Predicati per descrivere gli stati, dovranno essere delle liste: onTable(b1), on(b1,b2) holding(b1)

Descrizione:
- on(X,Y) -> X è appoggiato su Y
- onTable(X) -> X è sul tavolo
- empty -> il braccio è libero
- holding(X) -> il braccio ha in mano X

Per esempio stato iniziale:
    [empty, on(b3,b1), onTable(b1), onTable(b2)]

Per esempio stato finale:
    [empty, on(b1,b2), on(b2,b3), onTable(b3)]