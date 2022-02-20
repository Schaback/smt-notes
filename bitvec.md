# Bitvektoren

* Beschriebene Verfahren nur für quantorenfreies Fragment.

## Reduktion auf SAT

* Einige Operationen (insb. Multiplikation) skalieren exponentiell.
    * Approximieren durch UF (mit Ackermann-Reduktion) wenn möglich.
* Boolsches Skelett kann direkt mitkodiert werden (kein DPLL(T) nötig)

## Reduktion auf LIA
 * Nur shift-konstante Bitvektor Formeln

Algorithmus:
1. $\varphi' := flat(\varphi)$
2. $\psi := \varphi'$
3. Für jedes Atom $a \in At(\varphi')$:
    - Sei $(\vartheta,\gamma) := bv2lia(a)$ in
    $$\psi = \psi[a/\vartheta] \land \gamma$$
4. Gib $\psi$ aus.