
# Kombination von Entscheidungsverfahren

**Nelson-Oppen-Bedingung:**
 * Beide haben theorien haben Aquivalenz (=) definiert.
 * Theorien sind _stably infinite_

**Stably Infinite:**\
    Eine Theorie ist _stably-infinite_ gdw. jede erfüllbare, quantoren-freie T-Formel ein Modell mit einem unendlichen Universum hat.

**Welche Theorien erfüllen was?**

| Nicht Stably-Inf. | Nicht Konvex | Konvex |
|-------------------|--------------|--------|
|                   | LIA          |        |
|                   |              | LRA    |
|                   |              | UF     |
| Bitvektoren       |              |        |
| Arrays (???)      | Arrays (???) |        | 
| Modulare Arithm.  |              |        |

Gegenbeispiele:\
$(0\le x\le 1)\Rightarrow x=0\lor x=1$ \
$read(write(a,i,v),j)=v \Rightarrow (i=j \lor read(a,j)=v)$

-----

**Satz von Nelson-Oppen:**\
Seien $T_0,T_1$ zwei Theorien so dass:
- die QFF von $T_0,T_1$ entscheidbar sind
- $T_0,T_1$ die Nelson-Oppen-Bedingung erfüllen

Dann ist auch das QFF von $T_0 + T_1$ entscheidbar,.

## Nichtdeterministische Nelson-Oppen
1. Variablenabstraktion:\
    Transformiere Formel, sodass
    - Jedes Literal ist entweder ein $T_0$-Literal oder ein $T_1$-Literal
    - Ausnahme: Literal $(\neg)x = y$ für Variablen $x,y$ sind $T_0$-Literale _und_ $T_1$-Literale
2. Rate-und-Prüfe:
    - Rate eine Äquivalenzrelation auf den gemeinsamen Variablen
    - Prüfe, ob die Teilformeln zusammen mit dieser Relation erfüllbar sind

Problem: Anzahl an mögichen Äquivalenzrelationen wächst exponentiell.

## Deterministische Nelson-Oppen für konvexe Theorien

**Konvexe Theorie:**\
Eine Theorie $T$ ist konvex wenn jede $T$-gültige Formel der Form
$$
    \varphi \to \bigvee_{i = 1}^n u_i = v_i
$$
ein $i \in {1,\dots,n}$ existiert so dass bereits
$$
\varphi \to u_i = v_i
$$

**Algorithmus:**
1. Variablenabstraktion wie beim Nichtdeterministischem 
gibt $\varphi_0, \varphi_1$
2. Prüfe ob $\varphi_0$ oder $\varphi_1$ unerfüllbar sind
3. Bilde Äquivalenzrelation "on-the-fly"
    - Wenn es gemeinsame Var. $u,v$ gibt, so dass für eine Teilformel $\varphi_i$ gilt: $$\varphi_i \to u = v$$\
    dann füge $u = v$ auch zu den anderen Formeln $\varphi_j$ hinzu bei denen $\varphi_j \to u = v$ nicht gilt.
    - Andernfalls gib ERFÜLLBAR aus
4. Wiederhole Schritt 2
    


## Deterministische Nelson-Oppen für nicht-konvexe Theorien
Wie für konvexe Theorien, aber rekursive Fallunterscheidung statt
direktes Erlernen von Gleichheiten