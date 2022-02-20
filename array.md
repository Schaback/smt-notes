# Theorie der Arrays

* Axiome der Index- und Elementtheorie
* read-over-write Axiom
$$
read(write(a, i, e), j) = \begin{cases}
  e, & \text{falls}\quad i = j, \\
  read(a, j), & \text{sonst}
\end{cases}
$$
* Extensionalitätsaxiom
$$
a = b \Leftrightarrow \forall i, a[i] = b[i]
$$

## Quantorenfreie Fragment
* Relativ eingeschränkt, keinerlei Quantoren, keine Gleichheit auf Arrays


Algorithmus (für Formel $F$):
1. Falls $F$ keine $write$-Terme enthält:
    - Führe für jede Arrayvariable $a$ ein neues Funktionssymbol $f_a$ ein
    - Ersetze jeden Term $read(a,i)$ durch $f_a(i)$.
    - Löse resultierende Formel mit Kongurenzabschluss oder Ackerman-Reduktion
2. Ansonsten: Wähle Term $read(write(a,i,e),j)$ und...
    - Ersetze $F[read(write(a,i,e),j)]$ durch $F' := (F[e] \land i = j)$
    - Rufe das EV mit $F'$ auf, falls __erfüllbar__ gib __erfüllbar__ aus.
    - Ersetze $F[read(write(a,i,e),j)]$ durch $F'' := (F[read(a,j)] \land i \ne j)$
    - Rufe das EV mit $F''$ auf, falls __erfüllbar__ gib __erfüllbar__ aus.
    - Ansonsten gib __unerfüllbar__ aus


## Array-Property Fragment

Einschränkungen:
* Atome der Form: $\forall i_1, \dots, i_k: F[i_1, \dots i_k] \Rightarrow G[i_1,\dots,i_k]$
* Im Index-Guard:
    * Keine logische Negation, Quantoren, Arithmetik mit all-quantifizierten Variablen
    * Keine Division
    * Keine Arrayzugriffe
* Im Value-Guard:
    * Array Zugriffe nur in Form von $a[i_j]$ wobei $i_j$ eine Index Variable ist.

**Idee:** Reduktion auf Quantorenfreies Fragment

1. Formel $F$ zu Negated Normal Form (nur $\land$, $\lor$ und Negation nur vor Atomen)
2. Eliminiere $write$ Ausdrücke.
$$
\frac{F[write(a, i, e)]}
{F[a'] \land a'[i] = e \land (\forall j: j \ne i \Rightarrow a[j] = a'[j])}
$$
3. Eliminiere Existenzquantoren
$$
\frac{F[\exists i_1,\dots,i_k: G[i_1,\dots,i_k]]}
{F[G[j_1,\dots, j_k]]}
$$

4. Berechne (endliche) Index-Menge $I$.
$$
I := \{t : \centerdot[t] \:\text{tritt in F auf, t keine univ. quant. Var}\} \\
    \cup \{t : t \:\text{tritt innerhalb einer pexpr im Index-Guard auf}\}
$$
* Falls $I = \empty$,setzte $I = \{0\}$

5. Eliminiere All-Quantoren
$$
\frac{H[\forall i_1,\dots,i_k : F[i_1,\dots,i_k] \Rightarrow G[i_1,\dots,i_k]]}
{H[\bigwedge_{i_1,\dots,i_k\in I^k} F[i_1,\dots,i_k] \Rightarrow G[i_1,\dots,i_k]]}
$$


