# Uninterpretierte Funktionen

## Kongruenzabschluss

Berechne Kongruenzabschluss von $ \{s_i=t_i,...,s_n=t_n\} $ auf der Teiltermmenge $S_\varphi$\
Prüfe für allen Ungleichheiten $ \neg(s_i' = t_i') $:\
Falls $ s_i' \sim t_i' $ gebe UNSAT aus.\
Andernfalls SAT


## Ackermann Reduktion auf Gleichheitslogik

Jeder Teilterm bekommt eine eigene Variable zugewiesen.
z.B. $f(x)$ wird zu $f_x$

$flat^E$ ersetzt maximale Teilterme der Formel durch ihre Variablen.

$FC^E$ kodiert alle auftretenen Kongruenzen: $x = y \to f_x = f_y $

# Gleichheitslogik

## Äquivalenzabschluss

Im Prinzip wie Kongruenzabschluss


## Reduktion auf SAT

Die Belegung jeder Variable wird durch $N := \lceil log\:n \rceil$ Bits kodiert.

Jede Gleichung $x = y$ wird durch die Formel $(x_i \leftrightarrow y_i)$ für jedes $i \in [0, n]$ kodiert.