# Consegna 2 Pianificazione

Partiamo dallo stato del mondo iniziale e vogliamo arrvare allo stato del mondo Goal.

Plan(StatoIniziale, Goal, Azioni)

## Azioni
Azioni:
- Prendo il blocco 3 e lo metto sul tavolo
- Prendo il blocco 2 e lo metto sul blocco 3
- Prendo il blocco 1 e lo metto sul blocco 2
- Rilascio tutto e ho la mano libera -> Condizione finale perchè ho 3 blocchi in pila e la mano libera.

Caratteristiche:
- Nome
- Precondizione (sottoinsieme stato del mondo)
- Postcondizione (sottoinsieme stato del mondo dove andremo a finire)
  - Quello che togliamo allo stato del mondo perchè non sarà più vero
  - Quello che aggiungiamo allo stato del mondo perchè sarà vero

Alcune azioni:
- Grab
- Move per appoggiare un blocco su un altro blocco o sul tavolo (forse 2 aioni differenti)

### Grab X

- X è un blocco
- Precondizioni
- Post condizioni delete (quello che togliamo)
- Post condizioni add (quello che aggiungiamo)

grab(X)
PRE         empty, clear(X)
POST DEL    empty
POST ADD    holding(X)

put(X,Y)
PRE         holding(X), clear(Y)
POST DEL    holding(X), clear(Y)
POST ADD    empty, clear(X), on(X,Y)

putOnTable(X)
PRE         holding(X)
POST DEL    holding(X)
POST ADD    emoty, clear(X), onTable(X)

Lista output azioni:
[grab(b3), putOnTable(b3), grab(b2), put(b2,b3), grab(b1), put(b1,b2)]

## Stati
Predicati per descrivere gli stati, dovranno essere delle liste: onTable(b1), on(b1,b2) holding(b1)

Descrizione:
- on(X,Y) -> X è appoggiato su Y
- onTable(X) -> X è sul tavolo
- empty -> il braccio è libero
- holding(X) -> il braccio ha in mano X
- clear(X) -> X è libero e quindi non ha nulla appoggiato sopra di lui

Per esempio stato iniziale:
    [empty, on(b3,b1), onTable(b1), onTable(b2), clear(b3), clear(b2)]

Per esempio stato finale:
    [empty, on(b1,b2), on(b2,b3), onTable(b3), clear(b1)]


# Funzione block

block(X) if X = b1
block(X) if X = b2
block(X) if X = b3

oppure 

block(b1)
block(b2)
block(b3)

https://en.wikipedia.org/wiki/Stanford_Research_Institute_Problem_Solver