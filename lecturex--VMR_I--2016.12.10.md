---
numbersections: false
---

# [TK: section heading]

## Bemerkung

Die elementaren Umformungen (III) und (IV) kann man durch Kombination der Umformungen (I) und (II) erhalten

## Lemma 4.4

Entsteht die Matrix $B$ aus der Matrix $A$ durch elementare Zeilenumformungen, so ist:

$$
ZR(B) = ZR(A)
$$

### Beweis

Nach der Bemerkung reicht es die Umformungen (I) und (II) zu betrachten:

$$
A = \begin{pmatrix}
a_{1}^T\\
\vdots \\
a_{m}^T
\end{pmatrix}
$$

#### 1) Sei $B = A_{I}$:

$$ \begin{aligned}
v &\in ZR(A) = span(a_{1}, \cdots, a_{m}) \\[3mm]
\implies v &= \alpha_{1} a_{1} + \cdots + \alpha_{i} a_{i} + \cdots + \alpha_{m} a_{m} \\
&= \alpha_{1} a_{1} + \cdots + \frac{\alpha_{i}}{\alpha} \alpha a_{i} + \cdots + \alpha_{m} a_{m} \in ZR(B)
\end{aligned} $$

Entsprechend folgt für $v \in ZR(B) = span(a_{1}, \cdots , \alpha a_{i}, \cdots , a_{m})$:

$$ \begin{aligned}
v &= \alpha_{1} a_{1} + \cdots + \alpha_{i} (\alpha a_{i}) + \cdots + \alpha_{m} a_{m} \\
&= \alpha_{1} a_{1} + \cdots + (\alpha_{i} \alpha) a_{i} + \cdots + \alpha_{m} a_{m} \in ZR(A)
\end{aligned} $$

Also ist $ZR(B) = ZR(A)$ .

#### 2) Sei $B = A_{II}$:

$$ \begin{aligned}
v &\in ZR(A) = span(a_{1}, \cdots, a_{m}) \\[3mm]
\implies v &= \alpha_{1} a_{1} + \cdots + \alpha_{i} a_{i} + \cdots + \alpha_{j} a_{j} + \cdots + \alpha_{m} a_{m} \\
&= \alpha_{1} a_{1} + \cdots + \alpha_{i} (a_{i} + a_{j}) + \cdots + (\alpha_{j} - \alpha_{i}) a_{j} + \cdots + \alpha_{m} a_{m} \in ZR(B)
\end{aligned} $$

und

$$ \begin{aligned}
v &\in ZR(B) \in span(a_{1}, \cdots, a_{i} + a_{j},\cdots, a_{j}, \cdots, a_{m}) \\[3mm]
\implies v &= \alpha_{1} a_{1} + \cdots + \alpha_{i} (a_{i} + a_{j}) + \cdots + \alpha_{j} a_{j} + \cdots + \alpha_{m} a_{m} \\
&= \alpha_{1} a_{1} + \cdots + \alpha_{i} a_{i} + \cdots + (\alpha_{j} + \alpha_{i}) a_{j} + \cdots + \alpha_{m} a_{m}
 \in ZR(A)
\end{aligned} $$

Also ist $ZR(A) = ZR(B)$.

## Satz 4.5

Jede Matrix $A$ kann durch elementare Zeilenumformungen in eine Matrix $\tilde{A}$ in Zeilenstufenform überführt werden.

### Beispiel

$$ \begin{aligned}
a_{1} &= \begin{pmatrix}
0 \\
0 \\
0 \\
2 \\
1
\end{pmatrix},
a_{2} = \begin{pmatrix}
0 \\
1 \\
2 \\
2 \\
0
\end{pmatrix},
a_{3} = \begin{pmatrix}
0 \\
-1 \\
2 \\
1 \\
-1
\end{pmatrix},
a_{4} = \begin{pmatrix}
0 \\
0 \\
0 \\
1 \\
2
\end{pmatrix} \\[3mm]
U &= span(a_{1}, a_{2}, a_{3}, a_{4})
\end{aligned} $$

\begin{align*}
A &= \begin{gmatrix}[p]
0 & 0 & 0 & 2 & -1 \\
0 & 1 & -2 & 1 & 0 \\
0 & -1 & 2 & 1 & -1 \\
0 & 0 & 0 & 1 & 2
\rowops
	\swap{0}{1}
\end{gmatrix}
\to
\begin{gmatrix}[p]
0 & 1 & -2 & 1 & 0 \\
0 & 0 & 0 & 2 & -1 \\
0 & -1 & 2 & 1 & -1 \\
0 & 0 & 0 & 1 & 2
\rowops
	\add[1]{0}{3}
\end{gmatrix} \\[3mm]
&\to
\begin{gmatrix}[p]
0 & 1 & -2 & 1 & 0 \\
0 & 0 & 0 & 2 & -1 \\
0 & 0 & 0 & 2 & -1 \\
0 & 0 & 0 & 1 & 2
\rowops
	\swap{1}{3}
\end{gmatrix}
\to
\begin{gmatrix}[p]
0 & 1 & -2 & 1 & 0 \\
0 & 0 & 0 & 1 & 2 \\
0 & 0 & 0 & 2 & -1 \\
0 & 0 & 0 & 2 & -1
\rowops
	\add[-2]{1}{2}
	\add[-2]{1}{3}
\end{gmatrix} \\[3mm]
&\to
\begin{gmatrix}[p]
0 & 1 & -2 & 1 & 0 \\
0 & 0 & 0 & 1 & 2 \\
0 & 0 & 0 & 0 & -5 \\
0 & 0 & 0 & 0 & -5
\rowops
	\add[-1]{2}{3}
\end{gmatrix}
\to
\begin{gmatrix}[p]
0 & 1 & -2 & 1 & 0 \\
0 & 0 & 0 & 1 & 2 \\
0 & 0 & 0 & 0 & -5 \\
0 & 0 & 0 & 0 & 0
\end{gmatrix}
= B
\end{align*}

Also ist $(b_{1}, b_{2}, b_{3})$ mit:

$$ \begin{aligned}
b_{1} &= \begin{pmatrix}
0 \\
1 \\
2 \\
1 \\
0
\end{pmatrix},
b_{2} = \begin{pmatrix}
0 \\
0 \\
0 \\
1 \\
2
\end{pmatrix},
b_{3} = \begin{pmatrix}
0 \\
0 \\
0 \\
0 \\
5
\end{pmatrix}
\end{aligned} $$

eine Basis von $U = span(a_{1}, a_{2}, a_{3}, a_{4})$.

## Korollar 4.6

Für Vektoren $v_{1}, \cdots, v_{n} \in K^n$ sind folgende Aussagen äquivalent:

1) $(v_{1}, \cdots, v_{n})$ ist Basis von $K^n$.
2) Die Matrix $A = \begin{pmatrix} v_{1}^T \\ \vdots \\ v_{n}^T \end{pmatrix}$ lässt sich durch elemntare Zeilenumformungen in eine obere Dreiecksmatrix überführen und alle Einträge auf der Hauptdiagonalen sind $\neq 0$.

# 5. Lineare Gleichungssysteme

Nach [Lemma 1.8] definiert jede Matrix $A: K^n \to K^m$ durch $x \mapsto Ax$.

## Defininition 5.1

Ist $A = (a_{ij}) \sim (m, n)$ eine Matrix und $b = \begin{pmatrix} b_{1} \\ \vdots \\ b_{m} \end{pmatrix} \in K^m$, so heißt:

$$
Ax = b \iff
\begin{matrix}
a_{11} x_{1} + \cdots + a_{1n} x_{n} = b_{1} \\
\vdots \\
a_{m1} x_{1} + \cdots + a_{mn} x_{n} = b_{m}
\end{matrix}
$$

ein **lineares Gleichungssystem** mit $m$ Gleichungen und $n$ Unbekannten.

Ist $b \neq 0$, so heißt das lineare Gleichungssystem **inhomogen**, andernfalls **homogen**. $Ax = 0$ heißt, dass zu dem inhomogenen System gehörende homogene lineare Gleichungssystem.

Die Menge $\mathbb{L}(A,b) = \{x \in K^n | Ax = b\} \subset K^n$ heißt der Lösungsraum des linearen Gleichungssystems $Ax = b$ ($b = 0$ oder $b \neq 0$).

$A$ heißt die **Koeffizientenmatrix**, die Einträge $a_{ij}$ **Koeffizienten** des linearen Gleichungssystems. Die Matrix $(A|b)$ heißt die **erweiterte Matrix des linearen Gleichungssystems** $Ax = b$.

### Bemerkung

Bezeichnet $f: K^n \to K^m$ mit $f(x) = Ax$ die durch $A \sim (m,n)$ definiertes lineare Abbildung, so gilt:

$$ \begin{aligned}
\mathbb{L}(A, b) &= f^{-1}(b)\ \text{(Menge der Urbilder von b unter f)} \\
\mathbb{L}(A, 0) &= Ker f
\end{aligned} $$

### Beispiel

$$ \begin{aligned}
&\begin{matrix}
2 x_1 - 3 x_2 + x_3 &= 5 \\
- x_1 + 2 x_2 + 4 x_3 &= 1 \\
x_1 - x_2 &= 2
\end{matrix}
\ \ \ \hat{=} \ \
\begin{pmatrix}
2  & -3 & 1 & \BAR & 5 \\
-1 & 2  & 4 & \BAR & 1 \\
1  & -1 & 0 & \BAR & 2
\end{pmatrix} \text{erweiterte Matrix } (A|b) \\[3mm]
&\begin{pmatrix}
2  & -3 & 1 \\
-1 & 2  & 4 \\
1  & -1 & 0
\end{pmatrix}
\begin{pmatrix}
x_1 \\
x_2 \\
x_3
\end{pmatrix}
=
\begin{pmatrix}
5 \\
1 \\
2
\end{pmatrix} \\
&\text{Koeffizientenmatrix}
\end{aligned} $$
