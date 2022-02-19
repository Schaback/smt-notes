# Linear Integer Arithmetic

## Gauss            (Gleichungen über $\mathbb{Q}$)

* Schulverfahren
* Polynomielle Laufzeit

## Ad-Hoc-Verfahren (Gleichungen über $\mathbb{Z}$)

Algorithmus:
1. Gibt es eine unerfüllbare Gleichung $\Rightarrow$ UNSAT
2. Wähle Gleichung mit $|a_k| = 1$ und eliminiere sie durch Einsetzen von $x_k$
3. Sind alles Gleichungen eliminiert $\Rightarrow$ SAT
4. Wiederhole 1. solange wie möglich.
5. Reduziere Koeffizienten von Gleichung mit betragsmäßig kleinstem Koeffizienten (siehe VL)
6. Wiederhole Schritt 1.

* Polynomielle Laufzeit (aber Koeffizienten werden sehr groß)

## Fourier Motzkin  (Ungleichungen über $\mathbb{Q}$)

Algorithmus:
0. Eliminiere alle Gleichungen mit Ad-Hoc-Verfahren 
1. Wähle zu elminierendes $x_k$
2. Bilde alle Kombinationen aus oberen und unteren Schranken für $x_k$
3. Ersetze $$ \frac{\beta_l}{a_k} \le x_k \le \frac{\beta_u}{a_k'}$$
   Durch: $$ \frac{\beta_l}{a_k} \le \frac{\beta_u}{a_k'}$$
4. Wiederhole für alle Variablen

* Exponentielle Laufzeit (Jede Iteration quadriert die Anzahl Ungleichungen)

## Omega-Test       (Ungleichungen über $\mathbb{Z}$)

Algorithmus:

**Phase 1: Real Shadow**\
Analog zu Fourier Motzkin
1. $\beta_l \le a_k x_k \land a_k' x_k \le \beta_u \Rightarrow \beta_l \le a_k a_k' x_k \le \beta_u \Rightarrow \beta_l \le \beta_u$
2. Wenn es keine Lösung dafür gibt, dann ist das ursprüngliche Problem unerfüllbar

**Phase 2: Dark Shadow**\
Falls es ganzzahlige Lösung für alle $\beta_l \le a_k a_k' x_k \le \beta_u$ gibt muss diese ein Vielfaches von $a_k a_k'$ sein.

Prüfe $\beta_u a_k - \beta_l a_k' \ge (a_k - 1) (a_k' - 1)$

Wenn wahr, dann gibt es eine ganzzahlige Lösung

**Phase 3: Exakte Elimination (Grey Shadow)**\
Wähle den größten Koeffizienten $a_k'$ für $x_k$\
Prüfe für alle $0 \le i \le (a_k a_k' - a_k - a_k')/a_k'$
ob eine Lösung mit der Bedingung $ a_k x_k = \beta_l + i$ gibt.

### Übersicht
![](/omega.svg)