# Modulare Arithmetik

* $\sum_{i=1}^{n} a_i x_i \equiv b \;(mod\;m) \Leftrightarrow gcd(a_1,...,a_n,m) \mid b$ 
* $a$ hat mul. Inv. $(mod\;m)$ gdw. $gcd(a,m) = 1$ (berechnen mit EEA)


* Beschriebene Verfahren nur für quantorenfreies Fragment.
* Nur Kongruenzen mit mod $2^k$

## Lineare Kongruenzen $(mod\ 2^k)$ (Ganesh)

Algorithmus für Formeln $E_j: \sum_{i = 1}^n a_{ji}x_i \equiv b_j \: (mod\:2^k)$

1. Für ungeraden Koeffizienten $a_{ji}$ löse nach $x_i$ und ersetze in allen anderen Gleichungen.
    Falls diese Gleichung nicht gelöst werden kann ($gcd(a_{j1},\dots,a_{jn}, m) \nmid b_j$) ist es unlösbar.
2. Falls alle Koeffizienten gerade, dividiere um 2 und verkleinere $k$ um eins.
3. Wiederhole bis nur noch eine Gleichung übrig ($\Rightarrow$ SAT) oder eine Gleichung unlösbar ist ($\Rightarrow$ UNSAT)

* Wie können alle Lösungen bestimmt werden?

* Polynomielle Laufzeit

## (univariate) Polynom Kongruenzen $(mod\ 2^k)$ Hensel-Lifting

Algorithmus:
1. $[K=1]$: Prüfe, ob $p(x) \equiv 0 \;(mod\;2)$ eine Lösung hat. Falls nicht, UNSAT 
2. $[k\rightarrow k+1]$: Seien ${x_i}$ die Lösungen für $p(x) \equiv 0 \;(mod\;2^k)$:
    * Falls $p'(x_i) \equiv 0 \:(mod\: 2)$ 
        1. Falls $p(x_i) \not\equiv 0 \:(mod\:2^{k + 1})$, $x_i$ kann nicht gelifted werden.
        2. Sonst gibt es zwei Lösungen: $x_i^* = x_i + t \cdot 2^k, t \in \{0, 1\}$
    * Falls $p'(x_i) \not\equiv 0 \:(mod\: 2)$\
    $x_i^* = x_i - p(x_i) \;(mod\; 2^{k+1})$

* Für multivariate Polynome NP-Vollständig