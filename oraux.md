---
title: Oraux de la MPX1 de Chaptal
lang: fr
mathtools: true
homework-assignment: true
toc: true
---

## (Centrale, Python, Aymane) --- Actions de groupes planquées et permutations

Soit $A$ partie de $E$, on note $\sigma \cdot A = \sigma(A)$ pour $\sigma$ une permutation.

On note $B_n$ le nombre de partitions à $n$ éléments.

(1) Calcul de $B_1, B_2, B_3$.

(2) Montrer que: $\forall n \in \N, B_{n + 1} = \sum_{k=0}^n \binom{n}{k} B_k$.

(3) Écrire `B(n)` qui renvoie la liste $(B_k)_{k \in [[0, n]]}$. Vérifier que $B_6 = 203$.

(4) À l'aide de Python, calculer: $B_{p + m} - B_m - B_{m + 1}$ pour $m \in [[0, 50]], p \in \{2,3,5,7\}$.

(5) Pour $P, Q$ deux partitions, on introduit la relation: $P \sim Q$ si $\exists k \in \Z, Q = c^k \circ P$ où $c = (1, \ldots, p)$ permutation de $[[1, p + m]]$.

Montrer que $\sim$ est une relation d'équivalence.

(6) Soit $P$ partition, supposons $P \neq cP$, montrer alors: $\{ P, cP, \ldots, c^{p - 1} P \}$ est une classe d'équivalence pour $\sim$.

(7) Si $P = cP$, montrer qu'il y a une alternative (?).

(8) En déduire $B_{p + m} = B_m + B_{m + 1} \pmod {p}$.

## (Centrale, Python, Paul) --- Complexité moyenne d'un tri rapide

Soient $X_1, \ldots, X_n$ des VA d'un espace probabilisé ($\Omega, \tau, \PR$).

On pose $M_n = \max_{i \in [[1, n]]} X_i$ et $H_n$ la $n$-ième somme partielle de la série harmonique.

L'objectif est de déterminer l'espérance de $M_n$. ^[Contexte et intérêt: calculer des complexités moyennes, évaluer des coûts amortis dans des algorithmes qui reçoivent en entrée des données suivant une loi uniforme, gaussienne, …]

(1) Dans cette partie, supposons que les $(X_i)_i$ suivent une loi uniforme et sont à valeurs dans $[[1, N]]$.

a. Coder `EspU(n, N)`$ qui renvoie l'espérance de $M_n$ pour $n, N$ donnés. ^[Question orale: Résultat mathématiques justifiant la démarche utilisée ?]

b. Calculer l'espérance de $M_n$ pour $N \in \{50,100,200\}$ et $n = 100$. Comparer à $N \dfrac{n}{n + 1}$. Conjectures ?

(2) Dans cette partie, supposons que les $(X_i)_i$ suivent une loi géométrique de paramètre $p$.

a. Coder `EspG(n, p)` qui renvoie $\E(M_n)$.

b. Supposons que $p = 1/2$, calcul de $\E(M_n)$ pour $n \in \{100,200,500\}$. Calculer $\dfrac{-H_n}{\ln(1 - p}$ et $1 - \dfrac{H_n}{\ln(1 - p)}$. Conjectures ?

(3) Soit $X$ une VA admettant un moment d'ordre 2.

Montrer:

\begin{equation*}
        \E(X) = \sum_{k=0}^{+\infty} \PR(X > k)
\end{equation*}

et

\begin{equation*}
        \E(X^2) = \sum_{k=0}^{+\infty} (2k + 1) \PR(X > k)
\end{equation*}

**Annexe Python fournie** : `import numpy.random as rnd` et donc il sera possible de s'en servir pour simuler les lois.
Voici la documentation: <https://docs.scipy.org/doc/numpy/reference/routines.random.html>

## (Centrale, Python, Momo) --- Autour de la concentration de la mesure

Soit $M \in S_n(\R)$ à diagonale nulle et telles que:

\begin{equation*}
        \forall i < j, m_{ij} \sim \mathcal{B}\left(p_n = \dfrac{\lambda \ln(n)}{n}\right) \text{ (indépendantes)}
\end{equation*}

(1) Construire $M$ à l'aide d'une fonction: `def mat(\lambda, n)`

(2) Définir une fonction `def prob(\lambda, n)` qui renvoie la probabilité de quelque chose… ^[À clarifier.]

(3) On prend $\lambda \in \left\{ \left. \dfrac{1}{2} + \dfrac{2k}{10} \right\rvert k \in [[0, 5]] \right\}$ et $n \in \{ 50 + 100k \mid k \in [[0, 5]] \}$.

Calculer $\left(\textrm{Prob}(\lambda, n)\right)_{(\lambda, n)}$ avec Python et les mettre dans une liste.

(4) Soit $X_n$ le nombre de coefficients non nuls de $M$, déterminer la loi de $\dfrac{X_n}{2}$, puis $\E(X_n)$ et enfin $\V(X_n)$.

Soit $Z_n$ le nombre de « je m'en rappelle plus ». ^[Verbatim.] (pas grave, ça n'importe pas trop)

(5) Montrer que: $\PR(Z_n \geq 1) \leq \E(Z_n)$ et $\PR(Z_n = 0)\E(Z_n)^2 \leq \V(Z_n)$. ^[Ce qu'est $Z_n$ n'est pas très important, mais on peut supposer qu'elle est au moins de moment d'ordre 2.]

## (Centrale, Python, Cécile) --- Autour de la fonction $\Gamma$ et ses représentations

Posons $I_n = \int_0^{+\infty} t^n e^{-t} \dt, n \geq 0$.

(1) Montrer que $I_n$ converge et donner sa valeur.

On pose $v_n = \int_0^{+\infty} \left(1 + \dfrac{t}{n}\right)^n e^{-t} \dt, n \geq 0$.

(2) Montrer que $v_n$ converge.
(3) Conjecturer un équivalent de $v_n$ à une constante près à l'aide de Python.
(4) Démontrer qu'il s'agit bien d'un équivalent de $v_n$ et déterminer la constante.

On pose $S_n = e^{-n} \sum_{k=0}^n \dfrac{n^k}{k!}$.

(5) Analyser le comportement de $S_n$ au voisinage de l'infini, à l'aide de Python.
(6) Démontrer ce que vous voyez. ^[Indication: Montrer que la limite aperçu par Python est bien celle vers laquelle $S_n$ tend quoi.]

## (Centrale, Cécile) --- Autour de $\SL_n(\K)$

On pose $\SL_n(\K) = \{ M \in \M_n(\K) \mid \det(M) = 1 \}$, dans la suite: $\K$ est un surcorps commutatif de $\R$, ie: $\K = \R$ ou $\C$.

- On sait que $\SL_n(\K)$ est un sous groupe fermé de $\GL_n(\K)$ pour le produit matriciel, en effet: $\SL_n(\K) = \Ker \det = \det^{-1}(\{ 1 \})$, où : $\det : (\GL_n(\K), \times) \to (\K^{*}, \times)$ est un morphisme de groupe multiplicatif.

- On prend $\norm{\cdot}$ sous multiplicative, i.e. $\forall A, B \in \M_n(\K), \norm{AB} \leq \norm{A}\norm{B}$.

(1) Montrer que pour tout $M \in \SL_n(\K)$, $\norm{M} \geq 1$.
(2) Montrer que pour tout $M \in \SL_2(\K)$, $M$ est semblable à une matrice de la forme:

\begin{equation*}
        \begin{bmatrix}
                \lambda & 0 \\
                0 & \frac{1}{\lambda}
        \end{bmatrix},
        \begin{bmatrix}
                \pm 1 & \lambda \\
                0 & \pm \lambda
        \end{bmatrix},
        \begin{bmatrix}
                \cos \theta & \sin \theta \\
                -\sin \theta & \cos \theta
        \end{bmatrix}
\end{equation*}

Pour $\lambda \in \K$ et $\theta \in \R$.

(3) Pour tout $M \in \SL_2(\K)$, en déduire qu'il existe $B \in \M_n(\K)$ de trace nulle telle que: $M^2 = \exp(B)$.

## (Mines Télécom, Robert) --- Une série et une intégrale

On regarde $f : x \mapsto \sum_{n \geq 0} \dfrac{x^n}{(n!)^2}$ définie sur $\mathcal{D}$ son domaine de convergence.

(1) Déterminer $\mathcal{D}$ (rayon de convergence)
(2) Comparer avec $\displaystyle \int_{-\dfrac{\pi}{2}}^{\dfrac{\pi}{2}} \exp\left[2\sqrt{\pi} \sin(t)\right] \dt$

## (Mines Télécom, Robert) --- Condition suffisante de diagonalisabilité

Soit $A \in \M_n(\C)$, supposons que:

(1) $A^2$ soit diagonalisable dans $\M_n(\R)$
(2) $\Sp(A^2) \subset \R_{+}^{*}$

Montrer que $A$ est diagonalisable.

## (Mines Télécom, Paul) --- Série avec une bonne tronche d'arctangente

Définissons, pour tout $x \in \R_{+}^{*}$, $f : x \mapsto \sum_{n=1}^{+\infty} \dfrac{1}{n + xn^2}$.

(1) Convergence de $f$ ? Montrer que $f$ est continue sur son domaine de convergence.

(2) Équivalent de $f$ en $0$ et $+\infty$.

## (Mines Télécom, Paul) --- Espaces stables mais pas sur leurs appuis

Soit $u \in \LinearApps(\R^3)$.

On a: $u^3 = 0$ et $u^2 \neq 0$.

Décrire les sous espaces stables par $u$.

## (Mines Télécom, Arthur) --- Le bon vieux trick $\log-\exp$ et la DES

Montrer la convergence de $\sum \ln \dfrac{(2n + 1)n}{(2n - 1)(n + 1)}$ et calculer sa somme.


## (Mines Télécom, Arthur) --- Endomorphisme de moyennage

Soit $E$ l'espace vectoriel des fonctions continues de $[0, 1]$ dans $\R$.

Posons:

\begin{equation*}
        \application{\varphi}{E}{E}{f}{\left\{\application{F(f)}{[0,1]}{\R}{x}{
                \left\{
                \begin{aligned}
                        & f(0) \text{ si } x = 0 \\
                        & \dfrac{1}{x} \int_0^x f(t) \dt \text{ si } x \in ]0, 1]
                \end{aligned}
                \right.}\right.}
\end{equation*}

(1) Justifier que $\varphi$ est bien définie.

(2) Donner les valeurs propres de $\varphi$ et ses vecteurs propres.

## (Mines-Ponts, Ali) --- Équation fonctionnelle (opérateurs de somme)

Trouver toutes les fonctions continues de $\R$ dans $\R$ vérifiant:

\begin{equation*}
        \forall (x, y) \in \R^2, f(x + y) = f(x) + f(y)
\end{equation*}

## (Mines-Ponts, Ali) --- Équation fonctionnelle (morphisme de l'addition vers la multiplication)

Trouver toutes les fonctions continues de $\R$ dans $\C$ vérifiant:

\begin{equation*}
        \forall (x, y) \in \R^2, f(x + y) = f(x)f(y)
\end{equation*}

## (Mines-Ponts, Ali) --- Dimension et diagonalisabilité

Soit $A, B \in \GL_n(\C)$ telles que $AB + BA = 0$. ^[Dites aussi: anticommutantes.]

(1) Montrer que $n$ est pair.
(2) Si $n = 2$, montrer que $A$ et $B$ sont diagonalisables.

## (Mines-Télécom, Aymane) --- Autour des racines de $P$ et $P'$

Soit $P \in \R[X]$ scindé à racines simples.

(1) Exprimer $\dfrac{P'}{P}$ ^[t'as dead ça chakal.]
(2) Pour $a \in \R$, une racine de $P + aP'$ peut-elle être une racine de $P$ ?
(3) $P + aP'$ est-il scindé à racines simples?

## (Mines-Télécom, Aymane) --- Nature d'une série dont le terme général est l'inverse d'une somme partielle divergente

Soit $a_n = \left[\sum_{k=1}^n \ln^2(k)\right]^{-1}$.

Nature de $\displaystyle \sum_{n \geq 2} a_n$.

## (CCP, Aymane) --- Un peu de projection

Soit $(E, \norm{\cdot})$ euclidien, $u \in O(E)$.

On pose $v = u - \Id_E$.

(1) Montrer que $\Ker v = (\im v)^{\perp}$.

Soit $x \in E$.

On pose, pour tout $n \in \N^{*}$, $u_n(x) = \dfrac{1}{n} \sum_{k=0}^n u^k(x)$.

(2) Montrer que $(u_n(x))_n$ tend vers la projection orthogonale de $x$ sur $\Ker v$. ^[Indication de l'énoncé: utiliser 1 pour décomposer $x$ judicieusement.]

## (CCP, Mathilde) --- Calcul de distance à un hyperplan

Posons $E = \R_2[X]$ en tant que $\R$-espace, muni du produit scalaire canonique ^[Penser $\sum a_i b_i$ pour $(a_i), (b_i)$ les suites de coefficients respectifs].

On pose $F = \{ P \in E \mid P(1) = 0 \}$.

(1) Montrer que $F$ est un sous espace vectoriel de $E$ et en donner une base.
(2) Soit $P = X$, calculer la distance de $P$ à $F$. ^[Indication donnée par l'examinateur: Se mettre dans une base orthonormée de $F$.]

## (CCP, Paul) --- Suites de noyaux qui passent par une année de prépa

Soit $E$ un $\K$-espace vectoriel de dimension finie.

Soit $u \in \LinearApps(E)$.

On note $N = \bigcup_{i \geq 1} \Ker u^i$.

Montrer que $E = \im u \oplus \Ker u \iff N = \Ker u$. ^[Indication donnée par l'examinateur: « On pourra prouver d'abord $E = \Im u \oplus \Ker u \iff \Ker u = \Ker u^2$ ».]

## (CCP, Samy) --- Opérateur de translation

Soit $\mathcal{S}$ l'espace des suites à valeurs complexes.

Soit $L \in \LinearApps(\mathcal{S})$ tel que $\forall u \in \mathcal{S}, L(u) = u'$ où $\forall n \i n\N, u'_n = u_{n + 1}$. ^[Soit donc, un opérateur de translation.]

(1) Déterminer, pour tout $\lambda \in \C$, $\Ker(L - \Lambda \Id)$ et $\Ker(L - \Lambda \Id)^2$.

Soit $\mathcal{F}$ l'ensemble des suites vérifiant la relation suivante:

\begin{equation*}
        (*) \qquad \forall n \in \N, u_{n + 4} = \dfrac{1}{2} u_{n + 3} + 3 u_{n + 2}- \dfrac{7}{2} u_{n + 1} + u_n
\end{equation*}

(2) Montrer que: $\mathcal{F} = \Ker\left(L - \dfrac{1}{2} \Id\right) \oplus \Ker(L + 2\Id) \oplus \Ker(L - \Id)^2$

(3) En déduire la dimension et une base de $\mathcal{F}$.

Soit $\mathcal{S}_B$ l'ensemble des suites bornées vérifiant $(*)$.

(4) Déterminer la dimension et une base de $\mathcal{S}_B$.

---

## (ENS LCR, Charles) --- Étude probabiliste des records

On travaillera dans $\mathcal{S}_n$ l'ensemble des permutations sur $[[1, n]]$, on munit $\mathcal{S}_n$ de la probabilité uniforme $\PR$. ^[On pioche aléatoirement $\sigma$ une permutation.]

Pour $k \in [[1, n]]$, on dit que $k$ est un record de $\sigma \in \mathcal{S}_n$ si $k$ maximise $\sigma$ sur $[[1, k]]$, autrement dit:

\begin{equation*}
        k = \max_{1 \leq i \leq k} \sigma(i)
\end{equation*}

On note $\mathcal{R}(\sigma)$ l'ensemble des records.

On note $X_k = \Ind_{k \in \mathcal{R}(\sigma)}$ la variable aléatoire indicatrice de records, i.e. $1$ si $k$ est un record ou $0$ sinon.

(1) Donner la loi des $X_k$, $k \in [[1, n]]$.
(2) $X_k$ et $X_{k - 1}$ sont elles indépendantes pour $k \in [[2, n]]$
(3) Montrer l'indépendance mutuelle de la famille $(X_k)_{k \in [[1, n]]}$ ^[Requiert une indication selon Charles.]
