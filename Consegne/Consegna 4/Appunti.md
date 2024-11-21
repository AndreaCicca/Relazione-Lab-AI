# Consegna 4 Manipolazione di espressioni simboliche utilizzando le regole dell'algebra.

Calcolatore simbolico in grado di manipolare espressioni, partendo almeno dalle stressioni polinomiali a più variabili :somma, prodotti, divisioni, sotrazioni, elevamenti a potenza manipolandoli in maniera simbilica.

## Somma, prodotti e derivate polinomi con coefficienti interi in variabile X.

### Versione Densa

poly(x, 4, [4,7,0, 0, 9]) -> poliniomio 4 + 7X + 9X^4

### Versione Sparsa

poly(x, 4, [ k(0,4), k(1,7), k(4,9)]) -> polinomio  in variabile x, di grado 4 : 4 + 7X + 9X^4

'+'(X, Y) =  ...
'*'(X, Y) =  ...

diff(X, x) = ... # derivata rispetto a x


## Step successivi

ord([x,y,z])

diff/((x^3+5*y-1), y)

x^3+5*y-1 -> poly(x, [-1, poly(y, 1, [0,5]), 0, 1])
z^4+7*x+y -> poly(x, [poly(y, [poly(z, [0,0,0,0,1]), 1]), 7])


# Cosa fare

- polinomi in x coefficenti interi , somme e prodotti
- polinomi in x,,y,z ... (con funzioni ord/1) con coefficienti interi somme e prodotti
- quello di prima con le derivate
---
- numeri razionali 

-3/4 -> rat(-3,4)

- gcd tra polinomi
- sintassi latex portray

N/D = rat(N, D)