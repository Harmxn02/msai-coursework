# LE 2 - Exercises

## 1. Syntax van ASP-programma's

### Opgave 2.1

$\mathcal{O} = \set{\text{modelBAI, keyTopicsInAI, drAdams, ProfGobelijn}}$

$\mathcal{F} = \emptyset$

$\mathcal{P} = \set{\text{course/1, teacher/1, teaches/2}}$

$\mathcal{V} = \set{X,Y}$

#### A - construeer alle termen op basis van de bovenstaande signatuur

```lp
modelBAI, keyTopicsInAI, drAdams, ProfGobelijn, X, Y
```

#### B - construeer alle atomen op basis van de bovenstaande signatuur

```lp
course(modelBAI).
course(keyTopicsInAI).

teacher{drAdams}.
teacher{ProfGobelijn}.
...
```

In principe gewoon elke $\mathcal{P}$ met er in elke mogelijke term. Dus bijvoorbeeld ook `teacher{modelBAI}`

#### C - construeer een regel met een disjunctie bestaande uit drie literalen en een lichaam met minstens een default negatie op basis van de bovenstaande signatuur

```lp
teaches(drAdams, modelBAI)
```

### Opgave 2.2

\

### Opgave 2.3

Betract het volgende programma

```lp
c(1,2).
a(X) or b(Y) <- c(X,Y).
```

#### A - bepaal de signatuur van dit programma

$\mathcal{O} = \set{\text{1, 2}}$

$\mathcal{F} = \emptyset$

$\mathcal{P} = \set{\text{a/1, b/1, c/2}}$

$\mathcal{V} = \set{X,Y}$

#### B - Grondeer dit programma

```lp
c(1,2).
a(1) or b(1) <- c(1,1).
a(1) or b(2) <- c(1,2).
a(2) or b(1) <- c(2,1).
a(2) or b(2) <- c(2,2).
```

### Opgave 2.4

Betracht de volgende verzameling literalen

$$
S = \set{c(1,2), b(1), a(2)}
$$

#### A - voldoet deze verzameling aan het programma $\Pi$ uit opgave 2.3?

`c(1,2)` is mogelijk. Vanuit de grondering van programma $\Pi$ moet dan kloppen dat `a(1)` en `b(2)`, maar dat is niet het geval

#### B - voldoet deze verzameling aan het literaal `not a(1)`?

Ja, geen enkele van de elementen uit de verzameling zijn `a(1)`

#### C - voldoet deze verzameling aan de regel `c(1,2) <- b(1), not a(1)`?

Ja, denk ik

## 2. Informele semantiek van logische programma's

### Opgave 2.5

Zij get volgende programma $\Pi$ gegeven:

$p(a) \larr q(a).$

$\neg q(a).$

```
p(a) :- q(a).
     :- -q(a).
```

#### A - is de de verzameling $\set{\neg q(a), q(a)}$ een answer set?

Nee. Vanuit de regel zien we dat $\neg q(a)$ altijd waar moet zijn en dat is inderdaad het geval hier. Maar als $q(a)$ waar is dan moet $p(a)$ ook waar zijn maar die ontbreekt uit de verzameling

> Trouwens als $\neg q(a)$ altijd waar moet zijn, dan kan $q(a)$ nooit kloppen, dus dat is een tweede reden

#### B - is de de verzameling $\set{q(a)}$ een answer set?

Nee, want als $q(a)$ waar is dan moet $p(a)$ ook waar zijn maar die ontbreekt uit de verzameling. Ook zit $\neg q(a)$ er niet in

#### B - is de de verzameling $\set{q(a), p(a)}$ een answer set?

Nee, want $\neg q(a)$ moet er altijd in zitten

### Opgave 2.6

Zij het volgende programma $\Pi$ gegevenL

$p(a) \text{ or } p(b).$

$ \larr p(a), p(b).$

#### A - is de verzameling $\emptyset$ een answer set

Nee, want ofwel $p(a)$ of $p(b)$ moet er in zitten, en dat is niet het geval

#### B - is de verzameling $\set{p(a), p(b)}$ een answer set

Nee, want het is ofwel $p(a)$ of $p(b)$, niet beiden (de tweede regel verbiedt dat ze er beiden in zitten)

### Opgave 2.7

### Opgave 2.8

Zij het volgende programma gegeven:

$p(a) \larr q(a).$

$\neg q(a).$

#### Bereken alle answer sets voor dit programma

Het minimaal model is $\set{\neg q(a)}$

### Opgave 2.9

todo

### Opgave 2.10

todo

## 3. Formele semantiek van positieve logische programma's

## 4. Formele semantiek van logische programma's met negatie
