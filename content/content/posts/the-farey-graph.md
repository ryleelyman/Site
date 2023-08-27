---
title: "The Farey Graph"
date: 2021-06-27T14:48:02-04:00
math: true
---
The Farey graph, or Farey diagram,
is an object that appears in many guises throughout math.
For me, it appears several times as a complex related to
the outer automorphism group of a free group of rank two,
but it has connections to things like continued fractions as well.
The purpose of this post is introduce the Farey graph
and prove a couple of basic properties of it.

![The first four layers of the Farey graph](/img/FareyGraph.png)

The Farey graph has as vertices all rational numbers
expressed as fractions {{< katex >}}$\frac{p}{q}${{< /katex >}} in lowest terms with {{< katex >}}$q \ge 0${{< /katex >}},
together with a vertex for {{< katex >}}$\frac{1}{0}${{< /katex >}}.
Two vertices {{< katex >}}$\frac{a}{b}${{< /katex >}} and {{< katex >}}$\frac{c}{d}${{< /katex >}} span an edge
when the matrix {{< katex >}}$\begin{pmatrix} a & c \\ b & d \end{pmatrix}${{< /katex >}} has determinant {{< katex >}}$\pm 1${{< /katex >}}.
Above is a picture; thanks to StackExchange user [marchetto](https://tex.stackexchange.com/a/165845/212812)
for the TikZ code for producing the Farey diagram, to which I mainly added numbers.
I'd like to demonstrate that the visual properties of the Farey graph hold:
namely, that every edge belongs to exactly two triangles,
and that edges do not cross.

## Edges belong to two triangles

In this section we will show that every edge of the Farey graph belongs to two triangles.
The key tool will be a lemma I learned from
[Allen Hatcher's *Topology of Numbers*](http://pi.math.cornell.edu/~hatcher/TN/TNch1.pdf).

> **Lemma.** Suppose {{< katex >}}$a${{< /katex >}} and {{< katex >}}$b${{< /katex >}} are integers with no common divisor.
> If one integral solution of {{< katex >}}$ay - bx = n${{< /katex >}} is {{< katex >}}$(x,y) = (c,d)${{< /katex >}},
> then the general integral solution is {{< katex >}}$(x,y) = (c + ka, d + kb)${{< /katex >}} for integer {{< katex >}}$k${{< /katex >}}.

*Proof.* Consider a general solution {{< katex >}}$(x,y)${{< /katex >}}.
Given our known solution {{< katex >}}$(c,d)${{< /katex >}}, we see that {{< katex >}}$a(y-d) - b(x -c) = n - n = 0${{< /katex >}}.
Since {{< katex >}}$a${{< /katex >}} and {{< katex >}}$b${{< /katex >}} have no common factors, it follows that {{< katex >}}$a${{< /katex >}} divides {{< katex >}}$x-c${{< /katex >}} and {{< katex >}}$b${{< /katex >}} divides {{< katex >}}$y-d${{< /katex >}}.
In fact, we have {{< katex >}}$a(y-d) = abk = b(x-c)${{< /katex >}}, from which the result follows. {{< katex >}}$\blacksquare${{< /katex >}}

A variant on the proof shows that if {{< katex >}}$ac - bd = -n${{< /katex >}}, then the general integral solution for
{{< katex >}}$ax - by = n${{< /katex >}} is {{< katex >}}$(ka - c,kb - d)${{< /katex >}}.

> **Proposition.** Suppose that {{< katex >}}$\frac ab${{< /katex >}} and {{< katex >}}$\frac cd${{< /katex >}} are in the Farey graph,
> and that {{< katex >}}$ad > bc${{< /katex >}}. If {{< katex >}}$\frac xy${{< /katex >}} is adjacent to both {{< katex >}}$\frac ab${{< /katex >}} and {{< katex >}}$\frac bc${{< /katex >}},
> then {{< katex >}}$\frac xy = \frac{a\pm c}{b\pm d}${{< /katex >}}.

*Proof.*
Suppose {{< katex >}}$\frac ab${{< /katex >}} and {{< katex >}}$\frac cd${{< /katex >}} are as in the statement.
Now suppose {{< katex >}}$\frac xy${{< /katex >}} is adjacent to both {{< katex >}}$\frac ab${{< /katex >}} and {{< katex >}}$\frac cd${{< /katex >}}.
Suppose first for definiteness that {{< katex >}}$ay - bx = 1${{< /katex >}}.
By the lemma, we have that {{< katex >}}$(x,y) = (ka + c, kb + d)${{< /katex >}} for some integer {{< katex >}}$k${{< /katex >}}.
By assumption, we have {{< katex >}}$cy - dx = \pm 1${{< /katex >}}, so the lemma shows that {{< katex >}}$(x,y) = (\ell c \mp a,\ell d \mp b)${{< /katex >}}
for some integer {{< katex >}}$\ell.${{< /katex >}}
Therefore we have {{< katex >}}$a(k \pm 1) = (\ell - 1)c${{< /katex >}} and {{< katex >}}$b(k \pm 1) = (\ell-1)d${{< /katex >}},
from which it follows that {{< katex >}}$(k \pm 1)(\ell - 1)(ad - bc) = 0${{< /katex >}}.
Therefore either {{< katex >}}$k = \mp 1${{< /katex >}} or {{< katex >}}$\ell = 1${{< /katex >}},
both of which imply {{< katex >}}$(x,y) = (c \mp a,d \mp b)${{< /katex >}}.
If instead we have {{< katex >}}$ay-bx = -1${{< /katex >}}, then the conclusion is the same.
We of course have {{< katex >}}$\frac{c \mp a}{d \mp b} = \frac{a \pm c}{b \pm d}${{< /katex >}}. {{< katex >}}$\blacksquare${{< /katex >}}

## The action of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}}

In this section we analyze the action of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}} on the Farey diagram,
proving that it is transitive on edges and triangles.

First let us define the action of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}} on the Farey diagram.
The action of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}} on {{< katex >}}$\mathbb{Z}^2${{< /katex >}}
restricts to an action on the vertex set of the Farey diagram.
Indeed, {{< katex >}}$a${{< /katex >}} and {{< katex >}}$b${{< /katex >}} are relatively prime if and only if there exists integers {{< katex >}}$x${{< /katex >}} and {{< katex >}}$y${{< /katex >}}
such that {{< katex >}}$ax + by = 1${{< /katex >}}
if and only if {{< katex >}}$(a,b)${{< /katex >}} is the first column of a matrix in {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}}
if and only if there is an element of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}} taking {{< katex >}}$(1,0)${{< /katex >}} to {{< katex >}}$(a,b)${{< /katex >}}.
In terms of fractions, if {{< katex >}}$z = \frac{p}{q}${{< /katex >}} is a vertex of the Farey diagram,
then the action of {{< katex >}}$\begin{pmatrix} a & b \\ c & d \end{pmatrix}${{< /katex >}} sends {{< katex >}}$z${{< /katex >}} to

{{< katex >}}$\frac{az + b}{cz + d} = \frac{ap + bq}{cp + dq}.${{< /katex >}}

This action preserves adjacency: the reader is encouraged to figure out why.
Indeed, the action is transitive on edges:
can you show that if {{< katex >}}$\frac ab${{< /katex >}} and {{< katex >}}$\frac cd${{< /katex >}} are adjacent in the diagram,
there is an element of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}} sending the edge between {{< katex >}}$\frac 01${{< /katex >}} and {{< katex >}}$\frac 10${{< /katex >}}
to the edge between {{< katex >}}$\frac ab${{< /katex >}} and {{< katex >}}$\frac cd${{< /katex >}}?

Finally, put a [cyclic order](https://en.wikipedia.org/wiki/Cyclic_order) on the vertex set of the Farey diagram
by taking the cyclic order induced by the linear order on {{< katex >}}$\mathbb{Q} \cup \{\infty\}${{< /katex >}}.
That is, given three distinct elements {{< katex >}}$p${{< /katex >}}, {{< katex >}}$q${{< /katex >}} and {{< katex >}}$r${{< /katex >}} in {{< katex >}}$\mathbb{Q}\cup\infty${{< /katex >}},
say {{< katex >}}$(p,q,r)${{< /katex >}} is *cyclically ordered* if
{{< katex >}}$a < b < c${{< /katex >}} or {{< katex >}}$b < c < a${{< /katex >}} or {{< katex >}}$c < a < b${{< /katex >}} holds.
For example {{< katex >}}$(\infty,-2,0)${{< /katex >}} is cyclically ordered.

> **Proposition.** Suppose {{< katex >}}$p${{< /katex >}}, {{< katex >}}$q${{< /katex >}} and {{< katex >}}$r${{< /katex >}} are the vertices of a triangle in the Farey diagram and that
> {{< katex >}}$(p,q,r)${{< /katex >}} is cyclically ordered.
> Then there is an element of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}} sending {{< katex >}}$(0,1,\infty)${{< /katex >}} to {{< katex >}}$(p,q,r)${{< /katex >}}.

*Proof.*
Suppose {{< katex >}}$p = \frac cd${{< /katex >}} and {{< katex >}}$r = \frac ab${{< /katex >}}.
Because {{< katex >}}$p${{< /katex >}} and {{< katex >}}$r${{< /katex >}} are adjacent in the Farey diagram,
the matrix {{< katex >}}$\begin{pmatrix} a & c \\ b & d \end{pmatrix}${{< /katex >}} has determinant {{< katex >}}$\pm 1${{< /katex >}}.

Assume first that {{< katex >}}$ad-bc = 1${{< /katex >}}, i.e. that {{< katex >}}$p < r${{< /katex >}}.
Then the claim is that {{< katex >}}$q = \frac{a+c}{b+d}${{< /katex >}},
which is the image of {{< katex >}}$\frac 11${{< /katex >}} under the matrix {{< katex >}}$\begin{pmatrix} a & c \\ b & d\end{pmatrix}${{< /katex >}}.
In other words, the claim is that {{< katex >}}$(p,\frac{a-c}{b-d},r)${{< /katex >}} is not circularly ordered,
for which we need to show that {{< katex >}}$p<\frac{a-c}{b-d}<r${{< /katex >}} is false.
Assume first that {{< katex >}}$b-d${{< /katex >}} is nonnegative.
Then {{< katex >}}$ad > bc${{< /katex >}} implies {{< katex >}}$ab - ad < ab - bc${{< /katex >}}, which implies {{< katex >}}$\frac ab < \frac{a-c}{b-d}${{< /katex >}}, and the claim follows.
Next assume that {{< katex >}}$b-d${{< /katex >}} is negative.
Then {{< katex >}}$ad > bc${{< /katex >}} implies that {{< katex >}}$ad - dc > bc - dc${{< /katex >}}, which implies {{< katex >}}$\frac{a-c}{b-d} < \frac cd${{< /katex >}},
and the claim follows (Note that we assume that {{< katex >}}$d${{< /katex >}} is nonnegative.)

Next assume that {{< katex >}}$ad - bc = -1${{< /katex >}}, i.e. that {{< katex >}}$r < p${{< /katex >}}.
Then the claim is that {{< katex >}}$q = \frac{a-c}{b-d}${{< /katex >}},
which is the image of {{< katex >}}$\frac 11${{< /katex >}} under the matrix {{< katex >}}$\begin{pmatrix} a & - c \\ b & -d\end{pmatrix}${{< /katex >}}
in {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}}.
In other words, the claim is that {{< katex >}}$(p,\frac{a+c}{b+d},r)${{< /katex >}} is not circularly ordered,
for which we need to show that it neither {{< katex >}}$\frac{a+c}{b+d} < r < p${{< /katex >}} nor {{< katex >}}$r < p < \frac{a+c}{b+d}${{< /katex >}} holds.
In fact, {{< katex >}}$ad < bc${{< /katex >}} implies {{< katex >}}$ab + bc > ab + ad${{< /katex >}} holds, which implies {{< katex >}}$\frac{a+c}{b+d} > \frac ab${{< /katex >}}.
But, {{< katex >}}$ad < bc${{< /katex >}} implies that {{< katex >}}$ad + dc < bc + dc${{< /katex >}}, which implies that {{< katex >}}$\frac{a+c}{b+d} < \frac cd${{< /katex >}},
and the claim follows. {{< katex >}}$\blacksquare${{< /katex >}}

In fact, the proof above shows that the matrix in {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}}
is unique up to multiplication of all the entries by {{< katex >}}$-1${{< /katex >}}.
This corresponds to the matrix {{< katex >}}$\begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix}${{< /katex >}},
which generates the *center* of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}}.

> **Corollary.** The stabilizer of a triangle is isomorphic to {{< katex >}}$C_3 \times C_2 \cong C_6${{< /katex >}}.

An explicit generator for the cyclic group of order {{< katex >}}$6${{< /katex >}} stabilizing the triangle spanned by {{< katex >}}$(0,1,\infty)${{< /katex >}}
is {{< katex >}}$\begin{pmatrix} 1 & -1 \\ 1 & 0 \end{pmatrix}${{< /katex >}}.

The proposition also yields an element of {{< katex >}}$\operatorname{SL}_2(\mathbb{Z})${{< /katex >}} interchanging {{< katex >}}$0${{< /katex >}} and {{< katex >}}$\infty${{< /katex >}}:
this element is {{< katex >}}$\begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}${{< /katex >}}.
This element is unique up to multiplication by {{< katex >}}$-1${{< /katex >}} and has order {{< katex >}}$4${{< /katex >}}, so we have proven the following.

> **Corollary.** The stabilizer of an edge is isomorphic to {{< katex >}}$C_4${{< /katex >}}.

## Edges do not cross

We finish this post by proving that edges of the Farey diagram do not cross,
in the sense that if {{< katex >}}$p${{< /katex >}} and {{< katex >}}$q${{< /katex >}} are adjacent and {{< katex >}}$r${{< /katex >}} and {{< katex >}}$s${{< /katex >}} are adjacent
and {{< katex >}}$p${{< /katex >}}, {{< katex >}}$q${{< /katex >}}, {{< katex >}}$r${{< /katex >}} and {{< katex >}}$s${{< /katex >}} are all distinct,
then if {{< katex >}}$(p,r,q)${{< /katex >}} is cyclically ordered, then {{< katex >}}$(p,s,q)${{< /katex >}} is also cyclically ordered.
By results in the previous section, we may assume {{< katex >}}$p = 0${{< /katex >}} and {{< katex >}}$q = \infty${{< /katex >}}.
That is, if {{< katex >}}$r = \frac ab${{< /katex >}} is positive and {{< katex >}}$\frac cd${{< /katex >}} is adjacent to {{< katex >}}$\frac ab${{< /katex >}},
then {{< katex >}}$\frac cd${{< /katex >}} is also positive.
By swapping the roles of {{< katex >}}$r${{< /katex >}} and {{< katex >}}$s${{< /katex >}} if necessary, we may assume that {{< katex >}}$ad - bc = 1${{< /katex >}}.
Since we assume that {{< katex >}}$a${{< /katex >}}, {{< katex >}}$b${{< /katex >}}, and {{< katex >}}$d${{< /katex >}} are positive integers, then we must have {{< katex >}}$c \ge 0${{< /katex >}}
in order to satisfy {{< katex >}}$ad -bc = 1${{< /katex >}}.
