# Nicht-Lineare Arithmetik (in VL: Quantorenelimination)

* (Un)gleichungen von univariaten Polynomen (Tarski Formeln)
    * Multivariate Polynome nicht behandelt

* Reelle Zahlen allg. nicht axiomatisierbar, daher approximieren mit _reel abgeschlossenen Körpern_

1. Formeln in pränexe Normalform
2. Allquantoren in Existenzquantoren umwandeln ($\forall x, t \Rightarrow \lnot\exists x, \lnot t$)

3. Existenzquantoren eliminieren:
    * Finde eine endliche Menge $T \in \mathbb{R}$
    $$
        \exists x : G \equiv \bigvee_{t\in T} G[x / t]
    $$
    * Das Vorzeichen zwischen zwei aufeinanderfolgenden Nullstellen ist invariant.
    * $\mathbb{R}$ kann in $2 d + 1$ Vorzeichen-invariante Intervalle aufgeteilt werden.
    * Finde einen Testpunkt für jedes Interval, mithilfe Sturmscher Ketten, um Quantor zu eliminieren.
    

# Sturmsche Kette

Vorraussetzung: Das Polynom muss quadratfrei sein. \
Für ein Polnom $p$ hat $q = \frac{p}{gcd(p, p')}$ dieselben Nullstellen wie $p$ und ist quadratfrei.

Zu einem univariaten Polynom $p(x)$ ist die Sturmsche Kette definiert als:
* $P_0 = p$
* $P_1 = p'$
* $P_{i+1} = -rem(P_{i-1},P_i)$

Bezeichne $V(\xi)$ für $\xi \in \R$ die Anzahl an Vorzeichenwechsel der Sturmschen Kette $P_0(\xi),P_1(\xi),\dots$

Für ein quadratfreies, univariates Polynom $p(x)$ und $a<b$, gibt
$V(a)-V(b)$ die Anzahl der paarweise verschiedenen Nullstellen im Intevall $(a,b\ ]$.
