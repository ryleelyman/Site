---
title: "A Mathematical Postcard"
date: 2021-06-09T14:22:55-04:00
math: true
---

I submitted a "mathematical postcard" (see below)
to the [Nearly Carbon Neutral Geometric Topology][NCNGT] conference.
The purpose of this post is to share the postcard
and offer a little more context and explanation for it.
I'm also giving a talk in said conference,
but I'll talk about that in a separate post.

Here is the postcard:

{{< pdf-embed "/pdfs/postcard.pdf" >}}

Let me say a little more about the space we're talking about.
Let

{{< katex >}}$F = A_1*\dotsb*A_n*F_k${{< /katex >}}

be a free product of the groups {{< katex >}}$A_1,\dotsc,A_n${{< /katex >}} with a free group of rank {{< katex >}}$k${{< /katex >}}.
It follows from elementary Bass--Serre theory
that {{< katex >}}$F${{< /katex >}} acts on a (simplicial) tree {{< katex >}}$T${{< /katex >}} with trivial edge stabilizers
and vertex stabilizers each conjugate to some {{< katex >}}$A_i${{< /katex >}}.
Let's assume that the action is *minimal,* i.e. that there is no proper invariant subtree.
Say two such trees {{< katex >}}$S${{< /katex >}} and {{< katex >}}$T${{< /katex >}} are *equivalent* if there is an {{< katex >}}$F${{< /katex >}}-equivariant homeomorphism from {{< katex >}}$S${{< /katex >}} to {{< katex >}}$T${{< /katex >}}.
It turns out that there are many inequivalent, minimal actions!

[Guirardel and Levitt][GuirardelLevitt] define an Outer Space to parametrize them all
(up to a finer notion of equivalence: isometry).
It is a topological space on which the group of those outer automorphisms of {{< katex >}}$F${{< /katex >}}
which preserve the conjugacy classes of the {{< katex >}}$A_i${{< /katex >}} acts.
If the {{< katex >}}$A_i${{< /katex >}} are *freely indecomposable,* for example, if they are finite,
then this is all of {{< katex >}}$\operatorname{Out}(F)${{< /katex >}}.
This Outer Space admits a *spine,*
a subspace which is a simplicial complex
and onto which it deformation retracts {{< katex >}}$\operatorname{Out}(F)${{< /katex >}}-equivariantly.
Vertices of the spine are equivalence classes of minimal actions as above.
Two vertices are connected by an edge when one can be obtained from the other by collapsing an orbit of edges.
When {{< katex >}}$n \ge 2${{< /katex >}}, the dimension of this spine is {{< katex >}}$n + 2k - 2${{< /katex >}}.

When each {{< katex >}}$A_i${{< /katex >}} is finite, the spine is locally finite,
and {{< katex >}}$\operatorname{Out}(F)${{< /katex >}} acts with finite stabilizers and finite quotient.
This is the bread-and-butter situation for geometric group theory,
so outer automorphism groups of free products of finite and cyclic groups are interesting to study as a class
because one can use the geometry of the spine of Outer Space to investigate them.

Again by Bass--Serre theory, one can think of vertices of the spine
via their quotient graphs of groups {{< katex >}}$\mathcal{G}${{< /katex >}},
as is happening in the postcard.
These quotient graphs of groups will have first Betti number {{< katex >}}$k${{< /katex >}}
and {{< katex >}}$n${{< /katex >}} vertices with nontrivial vertex group each isomorphic to one of the {{< katex >}}$A_i${{< /katex >}}.

The combinatorial types of the examples in the postcard play a particularly special role
in studying the spine of Outer Space.
I call vertices combinatorially equivalent to the first and last examples *thistles*
with {{< katex >}}$n${{< /katex >}} prickles and {{< katex >}}$k${{< /katex >}} petals (here {{< katex >}}$n = 3${{< /katex >}} and {{< katex >}}$k = 4${{< /katex >}}).
Vertices combinatorially equivalent to the middle examples are *bugs*
with a head, {{< katex >}}$n-1${{< /katex >}} legs and {{< katex >}}$k${{< /katex >}} wings.

One reason thistles and bugs are special is illustrated in the postcard:
*collapse Whitehead moves* along with their cousins *expand Whitehead moves,*
form a system of paths in the spine of Outer Space that connect any two thistles to each other.
[Collins and Zieschang][CollinsZieschang] prove a version of Whitehead's algorithm for free products
using in particular two families of *Whitehead automorphisms* that they call {{< katex >}}$S${{< /katex >}}-Whitehead automorphisms
and {{< katex >}}$J${{< /katex >}}-multiple Whitehead automorphisms.
The former correspond to expand Whitehead moves, and the latter to collapse Whitehead moves,
and their result says that any two thistles in the spine of Outer Space may be connected by a path of Whitehead moves
which has a very nice interplay with a *norm* one can put on thistles.

![An expand Whitehead move](/img/expandWhitehead.png)

Let me finish by indicating my interest in these paths:
[Vogtmann][Vogtmann] proved that the outer automorphism group of a free group of rank {{< katex >}}$k${{< /katex >}}
is what's called *simply connected at infinity* for {{< katex >}}$k \ge 5${{< /katex >}}.
Briefly, a space {{< katex >}}$X${{< /katex >}} is simply connected at infinity if it has one [end][ends] 
and for any compact subset {{< katex >}}$K${{< /katex >}},
there is a compact subset {{< katex >}}$L${{< /katex >}} with {{< katex >}}$L \supset K${{< /katex >}} such that
any loop in {{< katex >}}$X\setminus L${{< /katex >}} is nullhomotopic via a homotopy in {{< katex >}}$X\setminus K${{< /katex >}}.
A group is simply connected at infinity if some (and hence any) simplicial complex
on which it acts with finite stabilizers and finite quotient is simply connected at infinity.
So {{< katex >}}$\mathbb{R}${{< /katex >}} has two ends, {{< katex >}}$\mathbb{R}^2${{< /katex >}} has one end but is not simply connected at infinity,
and {{< katex >}}$\mathbb{R}^{n}${{< /katex >}} is simply connected at infinity for {{< katex >}}$n \ge 3${{< /katex >}};
therefore {{< katex >}}$\mathbb{Z}^n${{< /katex >}} is simply connected at infinity for {{< katex >}}$n \ge 3${{< /katex >}}.
Vogtmann's proof involves a careful understanding of the combinatorics of (expand) Whitehead moves
in the spine of Outer Space (for a free group).
I'm in the early stages of working on generalizing her result to free products of finite and cyclic groups.
The general strategy of the proof will follow hers,
but already I am seeing that the presence of collapse Whitehead moves will require their own analysis to handle.

[NCNGT]: https://www.ncngt.org
[GuirardelLevitt]: https://arxiv.org/abs/math/0501288
[CollinsZieschang]: https://link.springer.com/article/10.1007%2FBF01236258
[Vogtmann]: https://www.sciencedirect.com/science/article/pii/004093839400042J
[ends]: https://en.wikipedia.org/wiki/End_(topology)
