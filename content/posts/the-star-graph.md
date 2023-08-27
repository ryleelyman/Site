---
title: "The Star Graph"
date: 2022-04-02T15:15:42-04:00
math: true
---
In an [earlier post][ideal edges] we introduced the concept of an *ideal edge*
in a graph of groups and described how to *blow up* ideal edges
to construct new graphs of groups.
To prove that (the reduced spine of) Outer Space for a virtually free group
is contractible, [Krstić and Vogtmann][equivariant outer space]
define what is essentially a combinatorial analogue of a non-singular Morse function
on Outer Space and show that for a well-chosen function,
the set of minimal vertices of the complex is actually the star of a single reduced marked graph of groups,
which is contractible.
A key tool to that end is the *star graph,*
and the purpose of this post is to describe the star graph (for conjugacy classes)
in a virtually free group and describe its usefulness.

## The reduced spine of Outer Space

Before we describe the star graph, let's define the complex we're working with.
Given a virtually (non-abelian, to keep things interesting) free group {{< katex >}}$F${{< /katex >}},
we'll call the reduced spine of Outer Space {{< katex >}}$L(F)${{< /katex >}}.
In tree language, a vertex of {{< katex >}}$L(F)${{< /katex >}}
is an action of {{< katex >}}$F${{< /katex >}} on a simplicial tree {{< katex >}}$T${{< /katex >}} with finite stabilizers and finite quotient
with the property that every edge of {{< katex >}}$T${{< /katex >}} is *surviving,* see [the post on shelters][shelters]
for a definition.
Two tree actions {{< katex >}}$T${{< /katex >}} and {{< katex >}}$T'${{< /katex >}} are *equivalent* if there is an equivariant homeomorphism between them.
The set of equivalence classes is partially ordered under *forest collapse,*
and the *reduced spine of Outer Space* is the geometric realization of this poset.

In graphs of groups language, 
a vertex of {{< katex >}}$L(F)${{< /katex >}} is a finite graph of finite groups {{< katex >}}$\mathcal{G}${{< /katex >}}
which is a union of *shelters*
together with a *marking,* which we can think of as an identification of {{< katex >}}$\pi_1(\mathcal{G})${{< /katex >}} with {{< katex >}}$F${{< /katex >}},
well-defined up to inner automorphism,
or as a *homotopy equivalence* in the sense of [my paper][traintracks]
{{< katex >}}$\sigma\colon \mathbb{G} \to \mathcal{G}${{< /katex >}}
from a fixed graph of finite groups {{< katex >}}$\mathbb{G}${{< /katex >}}.
Two marked graphs of groups {{< katex >}}$\tau = (\mathcal{G},\sigma)${{< /katex >}} and {{< katex >}}$\tau' = (\mathcal{G}',\sigma')${{< /katex >}}
are *equivalent* if there is an isomorphism of graphs of groups
{{< katex >}}$h \colon \mathcal{G} \to \mathcal{G}'${{< /katex >}} such that {{< katex >}}$h\sigma${{< /katex >}} is homotopic to {{< katex >}}$\sigma'${{< /katex >}}.
There is also a notion of *forest collapse* in graphs of groups,
which partially orders the set of equivalence classes of marked graphs of groups.
A marked graph of groups {{< katex >}}$\tau = (\mathcal{G},\sigma)${{< /katex >}} is *reduced* if it is minimal in this partial order.
The complex {{< katex >}}$L(F)${{< /katex >}} is the geometric realization of this poset.
We will adopt the graphs of groups language in this post.

## The norm

Let {{< katex >}}$\tau = (\mathcal{G},\sigma)${{< /katex >}} be a marked graph of groups in {{< katex >}}$L(F)${{< /katex >}},
and let {{< katex >}}$W${{< /katex >}} be a finite set of infinite order elements of {{< katex >}}$F${{< /katex >}}.
These elements are hyperbolic in some and hence every tree action in {{< katex >}}$L(F)${{< /katex >}},
so we may measure {{< katex >}}$\ell(w)${{< /katex >}}, their hyperbolic translation length,
and we define a *norm* on {{< katex >}}$\tau${{< /katex >}} as

{{< katex >}}$ \|\tau\| = \sum_{w \in W} \ell(w). ${{< /katex >}}

We can represent each conjugacy class {{< katex >}}$\sigma_\sharp(w)${{< /katex >}} in {{< katex >}}$\pi_1(\mathcal{G})${{< /katex >}}
as a cyclically reduced graph-of-groups *edge path*

{{< katex >}}$ \gamma_w = g_0e_1g_1\ldots e_kg_k. ${{< /katex >}}

We have {{< katex >}}$\ell(w) = k${{< /katex >}}, the number of edges in {{< katex >}}$\gamma_w${{< /katex >}}.
Recall that for each vertex {{< katex >}}$v${{< /katex >}} of {{< katex >}}$\mathcal{G}${{< /katex >}} we have the set of *directions at {{< katex >}}$v${{< /katex >}}*

{{< katex >}}$ D_v = \coprod_{e\in\operatorname{st}(v)} \mathcal{G}_v/\iota_e(\mathcal{G}_e) \times \{e\}. ${{< /katex >}}

There is an obvious left action of {{< katex >}}$\mathcal{G}_v${{< /katex >}} on {{< katex >}}$D_v${{< /katex >}}
which descends to an action on the set of pairs of directions at {{< katex >}}$v${{< /katex >}}.
A *turn* is an orbit under this action.
A turn is *degenerate* if every pair of directions representing it are identical
and is *nondegenerate* otherwise.
The vertex group elements of the path {{< katex >}}$\gamma_w${{< /katex >}} are not quite well-defined
if the edge groups of {{< katex >}}$\mathcal{G}${{< /katex >}} are nontrivial,
but the *turns* $$[\{(\iota_{\bar e_i}(\mathcal{G}_{\bar e_i}),\bar e_i),
(g_i\iota_{e_{i+1}}(\mathcal{G}_{e_{i+1}}),e_{i+1})\}]$$
for {{< katex >}}$1 \le i \le k-1$$ and ${{< /katex >}}[\{(g_k^{-1}\iota_{\bar e_k}(\mathcal{G}_{e_k}),e_k),
(g_0\iota_{e_1}(\mathcal{G}_{e_1}),e_1)\}]$$
are well-defined.
We say that {{< katex >}}$\gamma_w${{< /katex >}} *crosses* these turns, which are nondegenerate
because {{< katex >}}$\gamma_w${{< /katex >}} is cyclically reduced.

## The star graph

We define the *star graph* of a marked graph of groups {{< katex >}}$\tau = (\mathcal{G},\sigma)${{< /katex >}}
with respect to {{< katex >}}$W${{< /katex >}}.
Its vertex set is the union of the sets {{< katex >}}$D_v${{< /katex >}} as {{< katex >}}$v${{< /katex >}} varies over the vertices of {{< katex >}}$\mathcal{G}${{< /katex >}}.
For each turn crossed by some {{< katex >}}$\gamma_w${{< /katex >}},
the star graph contains {{< katex >}}$|\mathcal{G}_v|${{< /katex >}} edges,
each one connecting a pair of directions representing this turn.
Since the turns crossed by {{< katex >}}$\gamma_w${{< /katex >}} are nondegenerate, the star graph contains no loop edges.

![A star graph](/img/stargraph.jpeg)

In the above example we have

{{< katex >}}$F = C_4*_{C_2} C_4 * C_3 = \langle s, t, u \mid s^4 = t^4 = u^3 = 1,\ s^2 = t^2 \rangle,${{< /katex >}}

and the marked graph of groups {{< katex >}}$\tau = (\mathcal{G},\sigma)${{< /katex >}} is the "obvious"
graph of groups presentation of {{< katex >}}$F${{< /katex >}}.
There are three vertices with vertex groups {{< katex >}}$\langle s\rangle${{< /katex >}},
{{< katex >}}$\langle t\rangle${{< /katex >}} and {{< katex >}}$\langle u\rangle${{< /katex >}}.
There are two edges {{< katex >}}$a${{< /katex >}} and {{< katex >}}$b${{< /katex >}}.
The vertex {{< katex >}}$v${{< /katex >}} with vertex group {{< katex >}}$\langle t\rangle${{< /katex >}} has valence two;
both {{< katex >}}$a${{< /katex >}} and {{< katex >}}$b${{< /katex >}} are incident to it in the positive orientation.
The edge {{< katex >}}$a${{< /katex >}} connects {{< katex >}}$v${{< /katex >}} to the vertex with vertex group {{< katex >}}$\langle s\rangle${{< /katex >}}
and has {{< katex >}}$C_2${{< /katex >}} edge group, while {{< katex >}}$b${{< /katex >}} has trivial edge group.
The set {{< katex >}}$W${{< /katex >}} is the singleton {{< katex >}}$\{stu^2t^2\}${{< /katex >}}.
The star graph of of {{< katex >}}$\tau${{< /katex >}} with respect to {{< katex >}}$W${{< /katex >}}
has eleven vertices.
The component corresponding to {{< katex >}}$\langle s\rangle${{< /katex >}} has two vertices,
and there are four edges corresponding to the turns in the orbit 
{{< katex >}}$[\{(\langle s^2\rangle,\bar a),(s\langle s^2\rangle,\bar a)\}]${{< /katex >}}.
The component corresponding to {{< katex >}}$\langle u\rangle${{< /katex >}} has three vertices,
and there are three edges corresponding to the turns in the orbit
{{< katex >}}$[\{(1,\bar b),(u^2,\bar b)\}]${{< /katex >}}.
The component corresponding to the vertex {{< katex >}}$v${{< /katex >}} has six vertices,
two for directions with underlying oriented edge {{< katex >}}$a${{< /katex >}} and two with underlying oriented edge {{< katex >}}$b${{< /katex >}}.
This subgraph of the star graph is complete bipartite
corresponding to the turns in the orbits
{{< katex >}}$[\{(\langle t^2\rangle,a),(t,b)\}]${{< /katex >}} and {{< katex >}}$[\{(1,b),(\langle t^2\rangle,a)\}]${{< /katex >}}.

We can compute the norm of {{< katex >}}$\tau${{< /katex >}} from the star graph by summing up

$$ \|\tau\| = \frac{1}{2}\sum_{v \in \mathcal{G}}\sum_{d \in D_v} 
\frac{\operatorname{valence}(d)}{|\mathcal{G}_v|}.$$

So in this example we see that we have {{< katex >}}$\|\tau\| = 4${{< /katex >}}.

## Dot product and absolute value

Following Culler and Vogtmann,
given subsets {{< katex >}}$S${{< /katex >}} and {{< katex >}}$T${{< /katex >}} of the vertex set of a graph,
define the *dot product* {{< katex >}}$S\cdot T${{< /katex >}} to be the number of (unoriented) edges in the graph
with one vertex in {{< katex >}}$S${{< /katex >}} and the other in {{< katex >}}$T${{< /katex >}}.
The *absolute value* {{< katex >}}$|S|${{< /katex >}} of {{< katex >}}$S${{< /katex >}}  is the dot product of {{< katex >}}$S${{< /katex >}} with its complement.
An [*ideal edge*][ideal edges] {{< katex >}}$\alpha${{< /katex >}} is in particular a subset of the vertex set of the star graph,
so we may compute {{< katex >}}$|\alpha|${{< /katex >}}.
If {{< katex >}}$\alpha' = g.\alpha${{< /katex >}} under the action of {{< katex >}}$\mathcal{G}_v${{< /katex >}} on {{< katex >}}$D_v${{< /katex >}},
then {{< katex >}}$|\alpha| = |\alpha'|${{< /katex >}}.
Similarly a direction {{< katex >}}$d \in D_v${{< /katex >}} is a singleton subset of the vertex set of the star graph
and we may compute {{< katex >}}$|d| = |\{d\}|${{< /katex >}}.
If {{< katex >}}$d' = g.d${{< /katex >}}, then {{< katex >}}$|d| = |d'|${{< /katex >}}.
Put another way, the absolute value of {{< katex >}}$d${{< /katex >}} is a property of the underlying oriented edge {{< katex >}}$e${{< /katex >}}
and we may sometimes write {{< katex >}}$|e|${{< /katex >}} for {{< katex >}}$|d|${{< /katex >}}.

In the above example, the ideal edge {{< katex >}}$\alpha = \{(\langle t^2\rangle,a),(t,b),(t^3,b)\}${{< /katex >}}
has absolute value {{< katex >}}$|\alpha| = 4${{< /katex >}},
while the direction {{< katex >}}$d = (\langle t^2\rangle,a)${{< /katex >}} also has absolute value {{< katex >}}$4${{< /katex >}}.
Both {{< katex >}}$d${{< /katex >}} and {{< katex >}}$\alpha${{< /katex >}} have edge group isomorphic to {{< katex >}}$C_2${{< /katex >}},
so we have

{{< katex >}}$\frac{|d|}{|\mathcal{G}_a|} = \frac{|\alpha|}{|\mathcal{G}_\alpha|} = 2.${{< /katex >}}

If we blow up the ideal edge {{< katex >}}$\alpha${{< /katex >}} obtaining {{< katex >}}$\tau^\alpha = (\mathcal{G}^\alpha,\sigma^\alpha)${{< /katex >}},
the original {{< katex >}}$\gamma_w${{< /katex >}} was {{< katex >}}$as\bar atb u^2\bar b t^2${{< /katex >}} and
the new {{< katex >}}$\gamma_w${{< /katex >}} is {{< katex >}}$as\bar ab tu^2t^{-1}\bar b \bar\alpha t\alpha t^2${{< /katex >}},
which has {{< katex >}}$2${{< /katex >}} more edges.
If we then collapse the collapsible edge {{< katex >}}$a${{< /katex >}} corresponding to the direction {{< katex >}}$d \in D(\alpha)${{< /katex >}}
to obtain {{< katex >}}$\tau^\alpha_a${{< /katex >}},
the new {{< katex >}}$\gamma_w${{< /katex >}} is {{< katex >}}$sbtu^2t^{-1}\bar b\bar\alpha t\alpha s^2${{< /katex >}},
which has {{< katex >}}$2${{< /katex >}} fewer edges.

![The marked graphs of groups obtained by blowing up and then collapsing](/img/blowupanddown.jpeg)

This illustrates a general principal:

**Proposition** (Krstić–Vogtmann). If {{< katex >}}$\Phi = \{\alpha_1,\ldots,\alpha_k\}${{< /katex >}}
is a set of pairwise compatible ideal edges in a reduced marked graph of groups {{< katex >}}$\tau = (\mathcal{G},\sigma)${{< /katex >}}
and {{< katex >}}$\{e_1,\ldots,e_k\}${{< /katex >}} are a set of oriented edges in {{< katex >}}$\mathcal{G}${{< /katex >}} which form a forest in
{{< katex >}}$\tau^{\alpha_1,\ldots,\alpha_k}${{< /katex >}}, we have

{{< katex >}}$$ \|\tau^{\alpha_1,\ldots,\alpha_k}_{e_1,\ldots,e_k}\| = \|\tau\| 
+ \sum_{i=1}^k \frac{|\alpha_i|}{|\mathcal{G}_{\alpha_i}|} - \sum_{i=1}^k \frac{|e_i|}{|\mathcal{G}_{e_i}|}.$${{< /katex >}}

## Wrapping up

The *star* of a reduced marked graph of groups {{< katex >}}$\tau${{< /katex >}} is the set of marked graphs of groups {{< katex >}}$\tau'${{< /katex >}}
which collapse onto {{< katex >}}$\tau${{< /katex >}}.
The *ball of radius {{< katex >}}$r${{< /katex >}}* is the union of the stars of reduced marked graphs of groups {{< katex >}}$\tau${{< /katex >}}
with {{< katex >}}$\|\tau\| \le r${{< /katex >}}.
What Krstić–Vogtmann show is that 
as long as the ball of radius {{< katex >}}$r' < r${{< /katex >}} is nonempty,
the ball of radius {{< katex >}}$r${{< /katex >}} deformation retracts onto the ball of radius {{< katex >}}$r'${{< /katex >}}.
They show that for well-chosen {{< katex >}}$W${{< /katex >}}, there is a single reduced marked graph of groups
of minimal norm, thus proving that {{< katex >}}$L${{< /katex >}} is contractible.
To do both of these steps, they make extensive use of the star graph to analyze
the effect of blowing up and collapsing edges in marked graphs of groups.

[shelters]: {{< ref "shelters-in-graphs-of-groups.md" >}}
[ideal edges]: {{< ref "ideal-edges.md" >}}
[equivariant outer space]: https://www.researchgate.net/publication/226534036_Equivariant_outer_space_and_automorphisms_of_free-by-finite_groups/link/5762c70508aee61395bef5dc/download
[traintracks]: https://arxiv.org/abs/2102.02848
