---
title: "Another Mathematical Postcard"
date: 2022-09-03T16:36:45-04:00
math: true
---
I submitted another "mathematical postcard" (see below)
to the [Nearly Carbon Neutral Geometric Topology](https://www.ncngt.org) conference.
The purpose of this post is to offer a little more context and explanation for it.
For some reason I end up discussing things like ends of groups and finiteness properties
rather than sticking strictly to Bieri–Eckmann duality.

Here is the postcard:

{{< pdf-embed "/pdfs/postcard2.pdf" >}}

The text reads as follows:
A space {{< katex >}}$\tilde X${{< /katex >}} is **{{< katex >}}$n${{< /katex >}}-connected at infinity**
if for all {{< katex >}}$K \subset \tilde X${{< /katex >}} compact, there exists {{< katex >}}$C \subset K${{< /katex >}} compact
such that every map {{< katex >}}$S^n \to \tilde X - K${{< /katex >}} is nullhomotopic in {{< katex >}}$\tilde X - C${{< /katex >}}.
The figure illustrates the general fact that {{< katex >}}$\mathbb{R}^n${{< /katex >}} is {{< katex >}}$(n-2)${{< /katex >}}-connected at infinity.

If {{< katex >}}$G = \pi_1(X)${{< /katex >}}, where {{< katex >}}$X${{< /katex >}} is, say, a closed manifold with universal cover {{< katex >}}$\tilde X = \mathbb{R}^n${{< /katex >}},
then we say that {{< katex >}}$G${{< /katex >}} is {{< katex >}}$(n-2)${{< /katex >}}-connected at inifnity,
and in our case the (co-)homology of {{< katex >}}$G${{< /katex >}} satisfies Poincaré duality.
As it happens, {{< katex >}}$G${{< /katex >}} having cohomological dimension {{< katex >}}$n${{< /katex >}} and being {{< katex >}}$(n-2)${{< /katex >}}-connected at infinity
implies that {{< katex >}}$G${{< /katex >}} satisfies a generalization of Poincaré duality due to Bieri and Eckmann.

Unlike my [previous postcard],
I hope this one does a good job of illustrating something I care about
in a way that makes sense to a random geometric topologist,
even though secretly the postcards have the same motivation.

## Ends of groups

In [one of the big mapping class groups posts] we met the idea of the *space of ends* of a surface.
In fact, that definition, with no change, makes sense for an arbitrary topological space.
For example, suppose {{< katex >}}$G${{< /katex >}} is a finitely generated group and {{< katex >}}$S${{< /katex >}} is a finite generating set.
We can form a graph, called the *Cayley graph* of {{< katex >}}$G${{< /katex >}} with respect to {{< katex >}}$S${{< /katex >}},
by taking a vertex for each element of {{< katex >}}$G${{< /katex >}} and connecting two vertices {{< katex >}}$g${{< /katex >}} and {{< katex >}}$h${{< /katex >}} 
by an (oriented) edge labeled {{< katex >}}$s${{< /katex >}} when {{< katex >}}$h = gs${{< /katex >}}.
The group {{< katex >}}$G${{< /katex >}} naturally acts (on the left) on any of its Cayley graphs,
and when {{< katex >}}$S${{< /katex >}} is a finite generating set,
the action is properly discontinuous and cocompact, so the [Milnor–Schwarz lemma] applies:
if we {{< katex >}}$G${{< /katex >}}-equivariantly assign lengths to edges of the Cayley graph 
(the usual scheme is to assign each edge length one)
then the Cayley graph becomes a (proper! closed balls are compact) metric space and
{{< katex >}}$G${{< /katex >}} is [quasi-isometric] to any Cayley graph with respect to a finite generating set.

Anyway, it turns out that a finitely generated group has either
{{< katex >}}$0${{< /katex >}} ends (i.e. it is finite), {{< katex >}}$1${{< /katex >}} end, {{< katex >}}$2${{< /katex >}} ends, or a Cantor set of ends,
and this property is invariant under quasi-isometry.
(The classification is due to Freudenthal and Hopf, the quasi-isometry invariance possibly to Brick)
Actually, something slightly stronger is true:
[Brick] proves that if a space {{< katex >}}$X${{< /katex >}}
is quasi-isometric to a locally finite graph,
and {{< katex >}}$Y${{< /katex >}} is quasi-isometric to {{< katex >}}$X${{< /katex >}},
then {{< katex >}}$X${{< /katex >}} and {{< katex >}}$Y${{< /katex >}} have the same space of ends.
Well, the result that he claims is that quasi-isometric, locally finite graphs have the same number of ends,
but I think it shouldn't be hard to conclude what I stated from that.

What's more, Freudenthal and Hopf showed that if {{< katex >}}$G${{< /katex >}} has two ends,
then {{< katex >}}$G${{< /katex >}} has a finite-index subgroup isomorphic to {{< katex >}}$\mathbb{Z}${{< /katex >}}.
Stallings proved (earlier than Brick's result)
that if {{< katex >}}$G${{< /katex >}} has a Cantor set of ends,
then {{< katex >}}$G${{< /katex >}} *splits* over a finite subgroup,
in the sense that {{< katex >}}$G${{< /katex >}} acts on a simplicial tree with finite edge stabilizers.
So in some sense, the general and interesting case is to understand the {{< katex >}}$1${{< /katex >}}-ended groups
(she says, despite being an expert in groups with a Cantor set of ends...)

## Finer invariants of one-ended groups

So anyway, one way of distinguishing one-ended groups up to quasi-isometry
would be to have finer end invariants.
For example, we might ask about the higher connectivity of the ends of some CW complex
on which the group acts nicely 
(say a covering space action, or properly discontinuously and cocompactly, either should be fine).
One possible problem is that the connectivity properties of the complex might get in the way.
For example, every finitely generated group is quasi-isometric to a *graph,*
which, while typically being far from simply connected, has no higher homotopy groups to speak of.
This is not useful!

Better would be to restrict to the class of groups which admit nice actions
on {{< katex >}}$n${{< /katex >}}-connected complexes and ask about the {{< katex >}}$m${{< /katex >}}-connectivity at infinity of said complexes
for {{< katex >}}$m \le n${{< /katex >}}.
This is in fact what is done.
Say that a group {{< katex >}}$G${{< /katex >}} is of *type {{< katex >}}$F_n${{< /katex >}}* if it admits a {{< katex >}}$K(G,1)${{< /katex >}} with finite {{< katex >}}$(n-1)${{< /katex >}}-skeleton.
A {{< katex >}}$K(G,1)${{< /katex >}}, remember, is a CW-complex with fundamental group {{< katex >}}$G${{< /katex >}} and contractible universal cover
(or equivalently, where here I'm leaning quite heavily on "CW-complex", trivial higher homotopy groups).
Put another way, a group {{< katex >}}$G${{< /katex >}} is of type {{< katex >}}$F_n${{< /katex >}} if it admits a cocompact covering space action
on an {{< katex >}}$(n-1)${{< /katex >}}-connected CW-complex.
So being of type {{< katex >}}$F_1${{< /katex >}} is equivalent to being finitely generated,
type {{< katex >}}$F_2${{< /katex >}} to finite presentability,
and higher types are just their own thing.
As it happens, [Alonso] proved that being of type {{< katex >}}$F_n${{< /katex >}} is a quasi-isometry invariant.
[Brick] proves that for finitely presented groups,
being simply connected at infinity is also a quasi-isometry invariant.
Combined with Alonso's result this says that if {{< katex >}}$G${{< /katex >}} is quasi-isometric to {{< katex >}}$H${{< /katex >}}
and {{< katex >}}$H${{< /katex >}} is finitely presented and simply connected at infinity,
then {{< katex >}}$G${{< /katex >}} has both of these properties.
I imagine that Brick's arguments could be extended to show that higher connectivity at inifnity
is also a quasi-isometry invariant;
certainly this is known but I didn't feel it worthwhile to find out if it is written down.

## Bieri–Eckmann duallity

Recall that the *(co-)homology of a group* {{< katex >}}$G${{< /katex >}} is the (co-)homology of some (any) {{< katex >}}$K(G,1)${{< /katex >}}.
If {{< katex >}}$G${{< /katex >}} is of type {{< katex >}}$F_n${{< /katex >}}, then it has finitely generated (co-)homology up through dimension {{< katex >}}$n${{< /katex >}}.
One way for this to happen is if {{< katex >}}$G${{< /katex >}} is the fundamental group of a closed, aspherical {{< katex >}}$n${{< /katex >}}-manifold {{< katex >}}$X${{< /katex >}}
(i.e. for our {{< katex >}}$K(G,1)${{< /katex >}}, we may take {{< katex >}}$X${{< /katex >}}).
In this case, since the (co-)homology of {{< katex >}}$G${{< /katex >}} vanishes above dimension {{< katex >}}$n${{< /katex >}},
we say that {{< katex >}}$G${{< /katex >}} has *finite cohomological dimension {{< katex >}}$n${{< /katex >}}*.
Actually (modulo a worry in dimension 4 which I think is not relevant for groups),
this implies that {{< katex >}}$G${{< /katex >}} is the fundamental group of a *finite* CW-complex with contractible universal cover,
so {{< katex >}}$G${{< /katex >}} is of type {{< katex >}}$F_n${{< /katex >}} for every {{< katex >}}$n${{< /katex >}}.
(By the way, being of finite cohomological dimension actually implies that {{< katex >}}$G${{< /katex >}} is torsion free.)

Anyway, {{< katex >}}$X${{< /katex >}}, being a manifold, satisfies Poincaré duality.
A natural question to ask is what can be said about groups that satisfy Poincaré duality,
or maybe something weaker?
For the something weaker, we have *Bieri–Eckmann duality,*
where we say that {{< katex >}}$G${{< /katex >}} is a *duality group of dimension {{< katex >}}$n${{< /katex >}} in the sense of Bieri–Eckmann*
if there exists a *dualizing {{< katex >}}$\mathbb{Z}G${{< /katex >}}-module* {{< katex >}}$C${{< /katex >}}
and an element {{< katex >}}$e${{< /katex >}} of {{< katex >}}$H^n(G; C)${{< /katex >}} (which you might call the *fundamental class*)
such that capping with {{< katex >}}$e${{< /katex >}} (okay don't shoot the messenger, 
I don't actually yet know enough cohomology to say what this means)
induces natural isomorphisms

{{< katex >}}$H^k(G;A) \cong H_{n-k}(G; C\otimes A)${{< /katex >}}

for every nonnegative integer {{< katex >}}$k${{< /katex >}} and every {{< katex >}}$\mathbb{Z}G${{< /katex >}}-module {{< katex >}}$A${{< /katex >}}.
It turns out that {{< katex >}}$C${{< /katex >}} is always {{< katex >}}$H^n(G;\mathbb{Z}(G))${{< /katex >}}
and that {{< katex >}}$G${{< /katex >}} is therefore of cohomological dimension {{< katex >}}$n${{< /katex >}}.

Many groups are duality groups without being Poincaré duality groups;
Bieri–Eckmann give the example of knot groups.
Bestvina–Feighn proved that any finite-index torsion-free subgroup of {{< katex >}}$\operatorname{Out}(F_n)${{< /katex >}} 
is another example.

[previous postcard]: {{< ref "a-mathematical-postcard.md" >}}
[one of the big mapping class groups posts]: {{< ref "ends-of-surfaces.md" >}}
[Milnor–Schwarz lemma]: {{< ref "groups-as-metric-spaces.md" >}}
[quasi-isometric]: {{< ref "Gromov-hyperbolicity-for-arbitrary-metric-spaces.md" >}}
[Brick]: https://core.ac.uk/download/pdf/81947848.pdf
[Alonso]: https://core.ac.uk/download/pdf/82621017.pdf

