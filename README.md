# SMT-Solving
## Alle Entscheidungsverfahren

* Aussagenlogik
    * DPLL, CDCL

* [Lineare Arithmetik](lia.md)
    * (Gauss)          (Gleichungen über $\mathbb{Q}$)
    * Ad-Hoc-Verfahren (Gleichungen über $\mathbb{Z}$)
    * Fourier Motzkin  (Ungleichungen über $\mathbb{Q}$)
    * Omega-Test       (Ungleichungen über $\mathbb{Z}$)

* [Uninterpretierte Funktionen](uf.md)
    * Kongruenzabschluss
    * Ackermann Reduktion auf Gleichheitslogik
        * Äquivalenzabschluss (Union-Find)
        * Reduktion auf SAT

* [Bitvektoren](bitvec.md)
    * Bitblasting (Reduktion auf SAT)
    * Reduktion auf LIA

* [Array-Theorie](array.md)
    * Ad-Hoc-Verfahren für QFF
    * Array-Property Fragment

* [Modulare Arithmetik](mod.md)
    * Lineare Kongruenzen $(mod\ 2^k)$ (Ganesh)
    * (univariate) Polynom Kongruenzen $(mod\ 2^k)$ Hensel-Lifting

* [Nicht-Lineare Arithmetik (in VL: Quantorenelimination)](quant.md)
    * Polynomungleichungen über _real closed field_ (~ axiomatisierbares $\R$)
      mit Sturmschen Ketten (CAD?)

* DPLL(T)

* [Kombination von Theorien](combs.md)
    * nichtdeterministische Nelson-Oppen
    * deterministische Nelson-Oppen für konvexe Theorien
    * deterministische Nelson-Oppen für nicht-konvexe Theorien


## Einordunung in die Tabelle

|             | $\mathbb{Z}$     | $\mathbb{R}$    | $\mathbb{Z}/2^k\mathbb{Z}$ |
|-------------|------------------|-----------------|----------------------------|
| Lin. Gl.    | Elimination      | Gauss           | Ganesh                     |
| Lin. Ugl.   | Omega-Test       | Fourier-Motzkin | Bitvektoren                |
| nichtl. Ugl | _unentscheidbar_ | CAD             | Hensel-Lifting             |
