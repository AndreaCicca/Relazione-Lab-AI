# Interprete di un linguaggio logico

Sequenza di fatti e regole, fatto vero a prescindere e regola che si può dimostrare vera o falsa (congiunzione di altre affermazioni).

-- argomento 1 testa, argomento 2 corpo --

### Fatti perchè manca il corpo
clause(arc(1,2), []) 
clause(arc(1,3), [])
clause(arc(2,4), [])
clause(arc(3,4), [])

### Regole, il corpo è non vuoto.
clause(path(X,Y, [X, Y]), [arc(X,Y)])
clause(path(X,Y, [X | R]), [arc(X,Z), path(Z,Y,R)]) 

Il percorso lo chiamo R.

clause(member(X, [X | _]), [])
clause(member(X, [_ | T]), [member(X, T)])
clause(append([], R, R), [])
clause(append([H | T], L, [H | R]), [append(T, L, R)]) 

-> goal([member(2, [1,2,3])])
-> goal([append([1,2], [3,4], R)])

Sequenza di cose che devono essere vere per ritenere vera la testa.

Linguaggio senza il cut, dopo dovremmo aggiungere anche il cut!

## Funzione di interrogazione
Solo corpo di una regola

goal([arc(1,2)]) 

goal([arc(1,X), path[X, 4, P]])

### Per vedere le fuzioni delle variabili

[goal([arc(1,X), path[X, 4, P]]), X, P]

## Cut?

Nel momento in cui mettiamo 'cut' nel corpo

clause(path(X,Y, [X | R]), [arc(X,Z), path(Z,Y,R), cut])

Non possiamo tornare indiero e non possiamo andare alla prossima scelta non deterministica, quindi siamo bloccati orizzontalmente e verticalmente.

tutte le path dentro ad una lista (mi muovo in verticale) e li potremo tagliare.

[
clause(arc(1,2), []),
clause(arc(1,3), []),
clause(arc(2,4), []),
clause(arc(3,4), []),
clause(path(X,Y, [X, Y]), [arc(X,Y)]),
clause(path(X,Y, [X | R]), [arc(X,Z), path(Z,Y,R)]) 
]