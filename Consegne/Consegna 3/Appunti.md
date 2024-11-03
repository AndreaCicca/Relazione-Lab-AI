# Consegna 3 Parser

 Linguaggio naturale dei micro mondi.

Linguaggio naturale -> AST -> Liste di termini (per esempio onTable(b1))

Partiamo da: "The yellow block is on the table" e dobbiamo ritornare una lista vuola se è comprensibile.

Grammatica dell'inglese?

b1 is on the table
tell([],[b1, is, on, the, table]) = [onTable(b1)]

b1 is on b2
tell([],[b1, is, on, b2]) = [on(b1, b2)]

where is b1?
ask(tell([], [b1, is, on, the, table, '.']), [where, is, b1, '?']) = [b1, is, on, the, table, '.']

where is b2?
ask([on(b1, b2)], [where, is, b2, '?']) = [b2, is, on, b1, '.']


--------------- PIU' COMPLICATO ----------------

The blue block is on the table.
tell([], [the, blue, block, in, on, the, table, '.']) = [onTable(b2)]

the small block is on the large block.
tell([],[the, block, that, is, on, the, small, block, is, on, the, large, block, '.']) = [on(b1, b3)]
tell([],[the, block, that, is, on, the, small, block, is, on, the, large, block, '.']) = [on(b2, b3)]

the blue block is over the large block.
tell([],[the, block, that, is, over, the, blue, block, is, large, '.']) = [over(b2, b3)]

the blue block is on top of the large block.
tell([],[the, block, that, is, on, top, of, the, blue, block, is, large, '.']) = [onTopOf(b2, b3)]

the block that is on the blue block is belowe the red block.
tell([onTable(b1), color(b3, red)],[the, block, that, is, below, the, red, block, is, on, the, table, '.']) = [on(b3, b1)]

tell([onTable(b1)],[the, block, that, is, on, the, table, is red, '.']) = [color(b1, red)]

Where is the large block?
Pos is the large block => the large block is Pos => onTable(b1)
ask([onTable(b1), on(b2, b1), size(b1, large)], [where, is, the, large, block, '?']) = 
        [b1, is, on, the, table, '.']

Where is the small block?
Pos is the small block => the small block is Pos => on(X, b1)
ask([onTable(b1), on(b2, b1), size(b1, large)], [where, is, the, large, block, '?']) = 
        [the, small, block, is, on, b1, '.']