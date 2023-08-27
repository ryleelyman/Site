---
title: "The Train Track Algorithm for Graphs of Groups"
date: 2020-12-21T14:00:50-04:00
math: true
---
Train track maps, which also come in "relative" and other flavors,
are particularly nice homotopy equivalences of graphs
used as tools to reason about outer automorphisms of free groups.
I wrote a paper extending train track maps (as well as relative train track maps and "CTs")
to graphs of groups (with trivial edge groups for CTs).
In this post I want to talk a little about how to think about train track maps
and ("tame" in some sense) homotopy equivalences of graphs of groups more generally.
At the end of the post I talk through using the train track algorithm
to compute an example coming from a pseudo-Anosov 5-braid.

## Background on graphs of groups
First, a little background for anyone reading who isn't an expert in graphs of groups.
The standard reference is Chapter 1 of Serre's book *Trees,* 
which is terse but very good.
Group actions on trees (i.e. simply connected, 1-dimensional simplicial complexes)
crop up all over the place in the theory of infinite groups.
A *graph of groups* is a kind of "orbifold quotient" of a group action on a tree.
Technically one needs to assume that the action satisfies the condition of
"no inversions in edges" which means what it probably sounds like
and can always be accomplished by passing to the barycentric subdivision of the tree.
Under this hypothesis, the quotient space of the action is naturally a graph
(i.e. a 1-dimensional CW complex, which will be connected).
Attached to the vertices and edges of the graph are groups
recording stabilizer information.
The "no inversions in edges" hypothesis ensures that if an edge is stabilized by a group element,
then so are the incident vertices,
so there are injective homomorphisms from edge groups into incident vertex groups.

If you happen to like thinking categorically,
a graph of groups can be succinctly described this way.
A graph {{< katex >}}$\Gamma${{< /katex >}} describes a small category {{< katex >}}$\Gamma${{< /katex >}} whose objects are the cells of {{< katex >}}$\Gamma${{< /katex >}}
and whose nonidentity arrows run from edges to incident vertices.
A graph of groups is a functor from the small category {{< katex >}}$\Gamma${{< /katex >}}
to the category of groups with arrows monomorphisms.

The fundamental theorem of Bass–Serre theory asserts a perfect correspondence between
groups acting on trees on the one hand and graphs of groups on the other.
The exciting part of the theorem says that given a graph of groups,
there is a group, called the *fundamental group of the graph of groups*
and a tree, called the *Bass–Serre tree* on which it acts
so that the quotient graph of groups is the given graph of groups.
By the way, the fundamental group is really a group of homotopy classes of loops
in the right sense.
In the language of orbifolds, every graph of groups is "good."
What's more, a simple presentation of the fundamental group of the graph of groups
can be written down, and the tree and action explicitly described.

## Morphisms and maps of graphs of groups
Let's call a continuous map of graphs a *morphism* if it sends vertices to vertices and edges to edges.
There is a notion, due to Bass, of a *morphism* of graphs of groups.
It's a little complicated, so I'd rather talk around it than give a formal definition here.
Suppose {{< katex >}}$G${{< /katex >}} and {{< katex >}}$G'${{< /katex >}} are groups acting on trees {{< katex >}}$T${{< /katex >}} and {{< katex >}}$T'${{< /katex >}}, respectively,
and suppose that we have a homomorphism {{< katex >}}$f_\sharp\colon G \to G'${{< /katex >}}.
A morphism {{< katex >}}$\tilde f\colon T \to T'${{< /katex >}} is *equivariant* with respect to {{< katex >}}$f_\sharp${{< /katex >}} 
if for all {{< katex >}}$g \in G${{< /katex >}} and {{< katex >}}$x \in T${{< /katex >}}, we have

{{< katex >}}$\tilde f(g.x) = f_\sharp(g).\tilde f(x).${{< /katex >}}

If {{< katex >}}$\mathcal{G}${{< /katex >}} and {{< katex >}}$\mathcal{G}'${{< /katex >}} are the quotient graphs of groups,
Bass's definition is designed so that in this situation there is a morphism {{< katex >}}$f\colon\mathscr{G} \to \mathscr{G}'${{< /katex >}}.
Conversely, given a morphism of graphs of groups {{< katex >}}$f\colon \mathscr{G} \to \mathscr{G}'${{< /katex >}},
there is a map {{< katex >}}$f_\sharp\colon G \to G'${{< /katex >}} and an equivariant map {{< katex >}}$\tilde f\colon T\to T'${{< /katex >}}.
The correspondence is not quite perfect—in some situations there are multiple morphisms of graphs of groups
yielding the same pair {{< katex >}}$f_\sharp${{< /katex >}} and {{< katex >}}$\tilde f${{< /katex >}},
but the difference is understood.

If one happens to be categorically minded, it's possible to give a succinct definition 
of a morphism of graphs of groups.
Suppose {{< katex >}}$\mathcal{G}${{< /katex >}} and {{< katex >}}$\mathcal{G}'${{< /katex >}} are graphs of groups with underlying graphs
{{< katex >}}$\Gamma${{< /katex >}} and {{< katex >}}$\Gamma'${{< /katex >}}, respectively.
A morphism of graphs {{< katex >}}$f\colon \Gamma \to \Gamma'${{< /katex >}} yields a functor of the associated small categories.
(Indeed, one could eke out slightly more generality 
by defining morphisms of graphs to be those maps yielding a functor of small categories.)
A morphism of graphs of groups is a morphism of underlying graphs {{< katex >}}$f\colon \Gamma \to \Gamma'${{< /katex >}}
and a *pseudonatural transformation* of functors {{< katex >}}$f\colon \mathscr{G} \Rightarrow \mathscr{G}'f${{< /katex >}}.

Now suppose we have an automorphism {{< katex >}}$f_\sharp\colon G \to G${{< /katex >}} and a map
{{< katex >}}$\tilde f \colon T \to T${{< /katex >}} which is equivariant with respect to {{< katex >}}$f_\sharp${{< /katex >}} 
but may not be a morphism.
After performing a homotopy, 
we may assume that {{< katex >}}$\tilde f${{< /katex >}} 
is a linear embedding on each edge, 
expanding it over an edge path.
Now {{< katex >}}$\tilde f${{< /katex >}} will become a morphism after (equivariantly) subdividing each edge into finitely many edges,
so on the quotient graph of groups we are interested in maps 
which may be represented as a subdivision followed by a morphism.
Such a map {{< katex >}}$f\colon \mathcal{G}\to\mathcal{G}${{< /katex >}} sends vertices to vertices and edges to paths in the graph of groups.
If additionally the image of each edge is a *tight* path, i.e. it cannot be shortened by a homotopy,
we'll call such a map a *topological representative.*
For (many) examples of this kind of map, hang on for one more section.

## Train track maps

Train track maps were introduced by Bestvina and Handel in their 1992 paper
"Train tracks and automorphisms of free groups"
to study outer automorphisms of free groups.
They remain one of the main tools for their study.
A topological representative is a *train track map* if for each edge {{< katex >}}$e${{< /katex >}},
the path {{< katex >}}$f^k(e))${{< /katex >}} is immersed for all {{< katex >}}$k \ge 1${{< /katex >}},
i.e. it cannot be shortened by a homotopy.
If one accepts immersions and homotopy in a graph of groups sense,
the same definition works for both topological representatives on graphs and on graphs of groups.

Bestvina and Handel describe an algorithm that takes as input an arbitrary topological representative
and progressively either improves it to a train track map or finds an invariant subgraph.
(It is *a priori* possible to be both a train track map and have an invariant subgraph, 
but these cases are of less interest.)

The argument is a beautiful application of the Perron–Frobenius theory of nonnegative integer matrices.
A nonnegative integer matrix {{< katex >}}$M${{< /katex >}} is *irreducible* if for each {{< katex >}}$i${{< /katex >}} and {{< katex >}}$j${{< /katex >}} there exists {{< katex >}}$k${{< /katex >}}
such that the {{< katex >}}$ij${{< /katex >}}th entry of {{< katex >}}$M^k${{< /katex >}} is positive.
To a topological representative {{< katex >}}$f\colon \mathcal{G} \to \mathcal{G}${{< /katex >}} we can associate a *transition matrix*
with rows and columns for each edge of the underlying graph {{< katex >}}$\Gamma${{< /katex >}}
and {{< katex >}}$ij${{< /katex >}}th entry the number of times the image of the {{< katex >}}$j${{< /katex >}}th edge crosses the {{< katex >}}$i${{< /katex >}}th edge in either direction.
It turns out that the transition matrix of {{< katex >}}$f${{< /katex >}} is irreducible exactly when {{< katex >}}$f${{< /katex >}} has no invariant subgraph.

Each irreducible matrix has a real *Perron–Frobenius eigenvalue* {{< katex >}}$\lambda${{< /katex >}} satisfying {{< katex >}}$\lambda \ge 1${{< /katex >}}.
If {{< katex >}}$f${{< /katex >}} is not a train track map, Bestvina and Handel argue, then the Perron–Frobenius eigenvalue may be decreased
by their algorithm.
But by arguing that the number of edges of the graphs they consider remains bounded,
the Perron–Frobenius eigenvalue can only be decreased finitely many times before reaching a minimum,
at which point a train track map is reached.

## A pseudo-Anosov braid example

To illustrate the algorithm and hopefully offer some illumination on how to think about maps of graphs of groups,
I'd like to compute a train track map for the 
[pseudo-Anosov 5-braid with the least dilatation,](https://arxiv.org/abs/math/0506295)
{{< katex >}}$\sigma_1\sigma_2\sigma_3\sigma_4\sigma_1\sigma_2${{< /katex >}},
seen as an (outer) automorphism of {{< katex >}}$W_5${{< /katex >}}, the free product of 5 copies of the cyclic group of order 2.

Write

{{< katex >}}$W_5 = \langle a_1,a_2,\dotsc,a_5 \mid a_1^2 = a_2^2 = \dotsb = a_5^2 = 1 \rangle.${{< /katex >}}

There is a homomorphism from the braid group {{< katex >}}$B_n${{< /katex >}} to {{< katex >}}$\operatorname{Aut}(W_n)${{< /katex >}}
sending the generator {{< katex >}}$\sigma_i${{< /katex >}} to the automorphism

{{< katex >}}$$\begin{cases}
a_i \mapsto a_ia_{i+1}a_i^{-1} \\
a_{i+1} \mapsto a_i \\
a_j \mapsto a_j & j \neq i, i+1.
\end{cases}$${{< /katex >}}

There's a good reason (involving orbifolds) that the homomorphism sends
pseudo-Anosov braids to (outer) automorphisms representable by irreducible train track maps,
but let us just remark that we expect our eventual train track map to have
Perron–Frobenius eigenvalue equal to the dilatation of {{< katex >}}$\sigma_1\sigma_2\sigma_3\sigma_4\sigma_1\sigma_2${{< /katex >}},
that is, {{< katex >}}$\lambda \approx 1.722${{< /katex >}}, the largest root of {{< katex >}}$x^4 - x^3 - x^2 - x + 1${{< /katex >}}.

Under the homomorphism, the action of our element on the generators of {{< katex >}}$W_5${{< /katex >}} is given by

{{< katex >}}$$\sigma_1\sigma_2\sigma_3\sigma_4\sigma_1\sigma_2\begin{cases}
a_1 \mapsto a_1a_2a_3a_2^{-1}a_1^{-1} \\
a_2 \mapsto a_1a_2a_4a_2^{-1}a_1^{-1} \\
a_3 \mapsto a_1a_2a_1^{-1} \\
a_4 \mapsto a_1a_5a_1^{-1} \\
a_5 \mapsto a_1.
\end{cases}$${{< /katex >}}

To start, we need a graph of groups with fundamental group {{< katex >}}$W_5${{< /katex >}}.
It is a fact that if all edge groups in a graph of groups are trivial,
and the underlying graph is a tree,
then the fundamental group of the graph of groups is isomorphic to the free product of the vertex groups.
Thus a good candidate is the following graph of groups {{< katex >}}$\mathcal{G}_1${{< /katex >}}.

![A graph of groups with fundamental group {{< katex >}}$W_5${{< /katex >}}](/img/traintrack/thistle.jpg)

There is one vertex with trivial vertex group, five vertices with vertex group cyclic of order 2,
represented in the image by a number 2,
and five edges, each one connecting a vertex with nontrivial vertex group to the vertex with trivial vertex group.
Let us base the fundamental group at the center vertex with trivial vertex group.
Under our identification of this fundamental group with {{< katex >}}$W_5${{< /katex >}},
a generator of {{< katex >}}$W_5${{< /katex >}} is represented by a loop that travels out along an edge,
picks up the nontrivial element of the vertex group, and then travels back.
Thus for example {{< katex >}}$a_2${{< /katex >}} is represented by the loop {{< katex >}}$\bar Ba_2B${{< /katex >}}.

Let's introduce some notation: 
I'll write a period for the nontrivial element of any vertex group,
and write a hat above an edge to mean traveling along the edge, 
picking up the nontrivial element of the vertex group and then traveling back.
Thus the group element {{< katex >}}$a_1a_2a_3a_2^{-1}a_1^{-1}${{< /katex >}} is represented in our graph of groups
by the loop {{< katex >}}$\hat A\hat B\hat C\hat B\hat A${{< /katex >}}.

We may represent {{< katex >}}$\sigma_1\sigma_1\sigma_3\sigma_4\sigma_1\sigma_2${{< /katex >}} by the map
{{< katex >}}$f_1\colon \mathcal{G}_1\to\mathcal{G}_1${{< /katex >}} defined as

{{< katex >}}$$f_1 \begin{cases}
A \mapsto C\hat B \hat A \\
B \mapsto D\hat B \hat A \\
C \mapsto B \hat A \\
D \mapsto E \hat A \\
E \mapsto A
\end{cases}$${{< /katex >}}

The transition matrix of {{< katex >}}$f_1${{< /katex >}} is

{{< katex >}}$$\begin{pmatrix}
2 & 2 & 2 & 2 & 1 \\
2 & 2 & 1 & 0 & 0 \\
1 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 0
\end{pmatrix},
$${{< /katex >}}

whose Perron–Frobenius eigenvalue {{< katex >}}$\lambda_1${{< /katex >}} is the largest real root of
{{< katex >}}$-x^5 + 4x^4 + 2x^3 + 4x + 1${{< /katex >}} and satisfies {{< katex >}}$\lambda_1 \approx 4.577${{< /katex >}}.

How do we decide whether {{< katex >}}$f_1${{< /katex >}} is a train track map?
Since {{< katex >}}$f_1${{< /katex >}} sends edges to tight edge paths,
the only place where cancellation could occur is where the images of edges are joined together.
For example, in {{< katex >}}$f_1^2(A)${{< /katex >}}, there is cancellation between {{< katex >}}$f_1(B)${{< /katex >}} and {{< katex >}}$f_1(\bar A)${{< /katex >}}
because the last edge of {{< katex >}}$f_1(B)${{< /katex >}}, namely {{< katex >}}$A${{< /katex >}}, is equal to the reverse of the first edge of {{< katex >}}$f_1(\bar A)${{< /katex >}}.
Thus we know {{< katex >}}$f_1${{< /katex >}} is not a train track map.

We can formalize this as follows: a *turn* is a pair of edges sharing a common initial vertex,
e.g. {{< katex >}}$\{\bar A,\bar A\}${{< /katex >}} or {{< katex >}}$\{\bar B,\bar C\}${{< /katex >}}.
The former turn is *degenerate,* while the latter is not.
If the vertex in question has nontrivial vertex group,
rather than just pairs of edges,
we should consider pairs of pairs consisting of an edge together with a vertex group element.
Thus at the initial vertex of the edge {{< katex >}}$A${{< /katex >}},
the turn {{< katex >}}$\{.A,A\}${{< /katex >}} is nondegenerate.
A topological representative {{< katex >}}$f\colon \mathcal{G} \to \mathcal{G}${{< /katex >}} induces a map {{< katex >}}$Tf${{< /katex >}}
on the set of turns by sending {{< katex >}}$\{E,E'\}${{< /katex >}} to the
turn determined by the initial edges in the image of {{< katex >}}$f(E)${{< /katex >}} and {{< katex >}}$f(E')${{< /katex >}}.
A turn is *illegal* if it is eventually mapped to a degenerate turn.
In our example, every turn based at the center vertex is illegal because
each such turn is mapped to {{< katex >}}$\{\bar A,\bar A\}${{< /katex >}}.
Thus we can say that {{< katex >}}$f_1${{< /katex >}} is not a train track map
because, for instance, the image of {{< katex >}}$f_1(A)${{< /katex >}} contains the illegal turn {{< katex >}}$\{\bar B,\bar A\}${{< /katex >}}.

To improve the situation, let's *fold* {{< katex >}}$\bar A${{< /katex >}} and {{< katex >}}$\bar B${{< /katex >}}. 
They each have initial segments mapped to the path {{< katex >}}$\hat A\hat B${{< /katex >}},
so subdivide at the endpoint of these initial segments and then identify them to create a new edge as pictured.

![Folding the edges {{< katex >}}$\bar A${{< /katex >}} and {{< katex >}}$\bar B${{< /katex >}}](/img/traintrack/fold1.jpg)

The correspondence {{< katex >}}$A \leadsto A'F${{< /katex >}} and {{< katex >}}$B \leadsto B'F${{< /katex >}} allows us to define
a new map on our new graph of groups {{< katex >}}$f_2\colon \mathcal{G}_2\to \mathcal{G}_2${{< /katex >}}.
The new map admits some tightening, which yields a corresponding reduction in the Perron–Frobenius eigenvalue
{{< katex >}}$\lambda_2${{< /katex >}},
which is now the largest root of the polynomial {{< katex >}}$x^6 - 2x^5 - 2x^4 - 4x^2 + 3x + 2${{< /katex >}}
and satisfies {{< katex >}}$\lambda_2 \approx 2.994${{< /katex >}}.

![The second topological representative](/img/traintrack/map2.jpg)

However, the map {{< katex >}}$f_2${{< /katex >}} is still not a train track map, 
since every turn based at either of the vertices with trivial vertex stabilizer is eventually mapped to
{{< katex >}}$\{\bar F,\bar F\}${{< /katex >}}.

![The second map on turns](/img/traintrack/turns2.jpg)

Let's fold again, this time identifying all of {{< katex >}}$E${{< /katex >}} with an initial segment of {{< katex >}}$\bar F${{< /katex >}}.
The correspondence {{< katex >}}$F \leadsto F'E${{< /katex >}} yields a new map {{< katex >}}$f_3\colon \mathcal{G}_3 \to \mathcal{G}_3${{< /katex >}}.

![The third topological representative](/img/traintrack/map3.jpg)

Now the Perron–Frobenius eigenvalue {{< katex >}}$\lambda_3${{< /katex >}} is the largest root of
{{< katex >}}$x^6 - 2x^5 - 2x^4 - 2x^3 + 5x - 2${{< /katex >}} and satisfies {{< katex >}}$\lambda_3 \approx 2.875${{< /katex >}}.

![The third map on turns](/img/traintrack/turns3.jpg)

There are still illegal turns, so let's fold {{< katex >}}$C${{< /katex >}} and {{< katex >}}$D${{< /katex >}} with {{< katex >}}$E${{< /katex >}} to produce a valence-one vertex
with trivial vertex group.

![The third fold](/img/traintrack/fold3.jpg)

Folding doesn't produce any cancellation, so the Perron–Frobenius eigenvalue is unchanged.

![The fourth and fifth maps](/img/traintrack/map4.jpg)

The valence-one homotopy does decrease the Perron–Frobenius eigenvalue;
{{< katex >}}$\lambda_5${{< /katex >}} is the largest root of {{< katex >}}$-x^5 + x^4 + x^3 + x^2 + x - 2${{< /katex >}}
and satisfies {{< katex >}}$\lambda_5 \approx 1.830${{< /katex >}}.

![The fifth map on turns](/img/traintrack/turns5.jpg)

The image of {{< katex >}}$F'${{< /katex >}} contains the illegal turn {{< katex >}}$\{\bar A',\bar B'\}${{< /katex >}},
which is first mapped to {{< katex >}}$\{\bar C',\bar D'\}${{< /katex >}} before degenerating.
So we'll fold {{< katex >}}$\bar D'${{< /katex >}} and {{< katex >}}$\bar C'${{< /katex >}}, then {{< katex >}}$\bar A'${{< /katex >}} and {{< katex >}}$\bar B'${{< /katex >}}, 
and then the interior of {{< katex >}}$F'${{< /katex >}} if need be.

![The sixth and seventh maps](/img/traintrack/map6.jpg)

As it happens, the second fold produces nontrivial tightening;
{{< katex >}}$\lambda_7${{< /katex >}} is the largest root of {{< katex >}}$-x^7 + x^6 + x^5 + x^4 + x^3 - 2x^2 - 2${{< /katex >}}
and satisfies {{< katex >}}$\lambda_7 \approx 1.789${{< /katex >}}.
We have produced a vertex of valence two with trivial vertex group and would like to get rid of it via a homotopy.
The eigenvector coefficient of the edge {{< katex >}}$G${{< /katex >}} is larger than the eigenvector coefficient for {{< katex >}}$F'${{< /katex >}},
so we collapse {{< katex >}}$G${{< /katex >}}.

![The eighth map](/img/traintrack/map8.jpg)

The Perron–Frobenius eigenvalue {{< katex >}}$\lambda_8${{< /katex >}} is the largest root of
{{< katex >}}$x^6 - x^5 - 2x^3 - x - 1${{< /katex >}} and satisfies {{< katex >}}$\lambda_8 \approx 1.783${{< /katex >}}.
The turn {{< katex >}}$\{\bar E',\bar F'\}${{< /katex >}} is illegal and in the image of {{< katex >}}$F'${{< /katex >}}, so we fold them.

![The ninth map](/img/traintrack/map9.jpg)

The Perron–Frobenius eigenvalue {{< katex >}}$\lambda_9${{< /katex >}} is the largest root of {{< katex >}}$x^6 - x^5 - 2x^3 - x + 1${{< /katex >}}
and satisfies {{< katex >}}$\lambda_9 \approx 1.722${{< /katex >}}.
The only turns that we need to worry about in the image of edges of {{< katex >}}$f_9${{< /katex >}} are {{< katex >}}$\{E',\bar F''\}${{< /katex >}}
and {{< katex >}}$\{\bar B'',F''\}${{< /katex >}}.

![The ninth map on turns](/img/traintrack/turns9.jpg)

As it turns out, both of these turns are legal, so this is a train track map!
Indeed {{< katex >}}$\lambda_9${{< /katex >}} is also the largest real root of {{< katex >}}$x^4 - x^3 - x^2 - x + 1${{< /katex >}},
the polynomial we mentioned before in connection with {{< katex >}}$\sigma_1\sigma_2\sigma_3\sigma_4\sigma_1\sigma_2${{< /katex >}}.


