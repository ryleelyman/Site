---
title: "A Nice Coincidence"
date: 2021-07-19T14:55:19-04:00
math: true
---
The other day I "proved" the Farrell–Jones conjecture for a family of groups.
The word "proved" is in quotes because actually there was nothing to prove,
I just happened to be primed to notice that all the conditions were already there.
The purpose of this post is to tell you the story of how this came to be
and give the sketch of the proof that requires zero input from me.

Here is the story.
The first full week of July,
I attended [Ruth Charney's birthday conference](https://homepages.warwick.ac.uk/~masmbe/Charney/).
It was wonderful to be around people doing math in person again!
At this conference, Mladen Bestvina gave a talk about the Farrell–Jones conjecture
for (virtually torsion-free) hyperbolic-by-cyclic groups.
I don't fully understand the statement of the conjecture,
which says that certain assembly maps (?) in {{< katex >}}$K${{< /katex >}}-theory (??) or {{< katex >}}$L${{< /katex >}}-theory (???) are isomorphisms.
However, I did learn a useful tool for proving the Farrell–Jones conjecture,
a relatively recent (as in 2017) theorem due to Knopf:
if a (countable) group {{< katex >}}$G${{< /katex >}} acts acylindrically (without inversions) on a (simplicial) tree 
and the vertex stabilizers satisfy the Farrell–Jones conjecture, then so does {{< katex >}}$G${{< /katex >}}.
Here *acylindrically* means that there exists {{< katex >}}$K \ge 0${{< /katex >}} such that the stabilizer
of any geodesic segment of length {{< katex >}}$K${{< /katex >}} is finite.

One of the things I worked on this past week after coming back was my first review for zbMath.
The paper I reviewed studied high-dimensional graph manifolds,
which were introduced by Figerio, Lafont and Sisto.
A high-dimensional graph manifold is made of *pieces,*
each piece is a product of a torus and
a finite-volume hyperbolic manifold with toric cusps,
and the pieces are glued together by cutting off the cusps
into torus boundary components and gluing the tori.
As such, the fundamental group of a high-dimensional graph manifold is naturally
the fundamental group of a graph of groups
whose vertex groups are the pieces and whose edge groups are {{< katex >}}$\mathbb{Z}^{n-1}${{< /katex >}}.
Figerio, Lafont and Sisto prove that the high-dimensional graph manifold is
what's called *irreducible* if and only if the action of the fundamental group
on the Bass–Serre tree for the graph of groups is acylindrical (in fact, you can take {{< katex >}}$K${{< /katex >}} to be {{< katex >}}$3${{< /katex >}}).

Since CAT(0) groups (in particular, the fundamental groups of the pieces)
satisfy the Farrell–Jones conjecture,
the theorem above implies that irreducible high-dimensional graph manifold groups
satisfy the Farrell–Jones conjecture!
Not bad for no real work, eh?
