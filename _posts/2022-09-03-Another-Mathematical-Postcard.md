---
layout: post
math: true
---

I submitted another "mathematical postcard" (see below)
to the [Nearly Carbon Neutral Geometric Topology](https://www.ncngt.org) conference.
The purpose of this post is to offer a little more context and explanation for it.
For some reason I end up discussing things like ends of groups and finiteness properties
rather than sticking strictly to Bieri–Eckmann duality.

Here is the postcard:

<iframe src="/assets/pdfs/postcard2.pdf" width="100%" height="400px">
</iframe>

The text reads as follows:
A space $$\tilde X$$ is **$$n$$-connected at infinity**
if for all $$K \subset \tilde X$$ compact, there exists $$C \subset K$$ compact
such that every map $$S^n \to \tilde X - K$$ is nullhomotopic in $$\tilde X - C$$.
The figure illustrates the general fact that $$\mathbb{R}^n$$ is $$(n-2)$$-connected at infinity.

If $$G = \pi_1(X)$$, where $$X$$ is, say, a closed manifold with universal cover $$\tilde X = \mathbb{R}^n$$,
then we say that $$G$$ is $$(n-2)$$-connected at inifnity,
and in our case the (co-)homology of $$G$$ satisfies Poincaré duality.
As it happens, $$G$$ having cohomological dimension $$n$$ and being $$(n-2)$$-connected at infinity
implies that $$G$$ satisfies a generalization of Poincaré duality due to Bieri and Eckmann.

Unlike my [previous postcard],
I hope this one does a good job of illustrating something I care about
in a way that makes sense to a random geometric topologist,
even though secretly the postcards have the same motivation.

## Ends of groups

In [one of the big mapping class groups posts] we met the idea of the *space of ends* of a surface.
In fact, that definition, with no change, makes sense for an arbitrary topological space.
For example, suppose $$G$$ is a finitely generated group and $$S$$ is a finite generating set.
We can form a graph, called the *Cayley graph* of $$G$$ with respect to $$S$$,
by taking a vertex for each element of $$G$$ and connecting two vertices $$g$$ and $$h$$ 
by an (oriented) edge labeled $$s$$ when $$h = gs$$.
The group $$G$$ naturally acts (on the left) on any of its Cayley graphs,
and when $$S$$ is a finite generating set,
the action is properly discontinuous and cocompact, so the [Milnor–Schwarz lemma] applies:
if we $$G$$-equivariantly assign lengths to edges of the Cayley graph 
(the usual scheme is to assign each edge length one)
then the Cayley graph becomes a (proper! closed balls are compact) metric space and
$$G$$ is [quasi-isometric] to any Cayley graph with respect to a finite generating set.

Anyway, it turns out that a finitely generated group has either
$$0$$ ends (i.e. it is finite), $$1$$ end, $$2$$ ends, or a Cantor set of ends,
and this property is invariant under quasi-isometry.
(The classification is due to Freudenthal and Hopf, the quasi-isometry invariance possibly to Brick)
Actually, something slightly stronger is true:
[Brick] proves that if a space $$X$$
is quasi-isometric to a locally finite graph,
and $$Y$$ is quasi-isometric to $$X$$,
then $$X$$ and $$Y$$ have the same space of ends.
Well, the result that he claims is that quasi-isometric, locally finite graphs have the same number of ends,
but I think it shouldn't be hard to conclude what I stated from that.

What's more, Freudenthal and Hopf showed that if $$G$$ has two ends,
then $$G$$ has a finite-index subgroup isomorphic to $$\mathbb{Z}$$.
Stallings proved (earlier than Brick's result)
that if $$G$$ has a Cantor set of ends,
then $$G$$ *splits* over a finite subgroup,
in the sense that $$G$$ acts on a simplicial tree with finite edge stabilizers.
So in some sense, the general and interesting case is to understand the $$1$$-ended groups
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
on $$n$$-connected complexes and ask about the $$m$$-connectivity at infinity of said complexes
for $$m \le n$$.
This is in fact what is done.
Say that a group $$G$$ is of *type $$F_n$$* if it admits a $$K(G,1)$$ with finite $$(n-1)$$-skeleton.
A $$K(G,1)$$, remember, is a CW-complex with fundamental group $$G$$ and contractible universal cover
(or equivalently, where here I'm leaning quite heavily on "CW-complex", trivial higher homotopy groups).
Put another way, a group $$G$$ is of type $$F_n$$ if it admits a cocompact covering space action
on an $$(n-1)$$-connected CW-complex.
So being of type $$F_1$$ is equivalent to being finitely generated,
type $$F_2$$ to finite presentability,
and higher types are just their own thing.
As it happens, [Alonso] proved that being of type $$F_n$$ is a quasi-isometry invariant.
[Brick] proves that for finitely presented groups,
being simply connected at infinity is also a quasi-isometry invariant.
Combined with Alonso's result this says that if $$G$$ is quasi-isometric to $$H$$
and $$H$$ is finitely presented and simply connected at infinity,
then $$G$$ has both of these properties.
I imagine that Brick's arguments could be extended to show that higher connectivity at inifnity
is also a quasi-isometry invariant;
certainly this is known but I didn't feel it worthwhile to find out if it is written down.

## Bieri–Eckmann duallity

Recall that the *(co-)homology of a group* $$G$$ is the (co-)homology of some (any) $$K(G,1)$$.
If $$G$$ is of type $$F_n$$, then it has finitely generated (co-)homology up through dimension $$n$$.
One way for this to happen is if $$G$$ is the fundamental group of a closed, aspherical $$n$$-manifold $$X$$
(i.e. for our $$K(G,1)$$, we may take $$X$$).
In this case, since the (co-)homology of $$G$$ vanishes above dimension $$n$$,
we say that $$G$$ has *finite cohomological dimension $$n$$*.
Actually (modulo a worry in dimension 4 which I think is not relevant for groups),
this implies that $$G$$ is the fundamental group of a *finite* CW-complex with contractible universal cover,
so $$G$$ is of type $$F_n$$ for every $$n$$.
(By the way, being of finite cohomological dimension actually implies that $$G$$ is torsion free.)

Anyway, $$X$$, being a manifold, satisfies Poincaré duality.
A natural question to ask is what can be said about groups that satisfy Poincaré duality,
or maybe something weaker?
For the something weaker, we have *Bieri–Eckmann duality,*
where we say that $$G$$ is a *duality group of dimension $$n$$ in the sense of Bieri–Eckmann*
if there exists a *dualizing $$\mathbb{Z}G$$-module* $$C$$
and an element $$e$$ of $$H^n(G; C)$$ (which you might call the *fundamental class*)
such that capping with $$e$$ (okay don't shoot the messenger, 
I don't actually yet know enough cohomology to say what this means)
induces natural isomorphisms

$$H^k(G;A) \cong H_{n-k}(G; C\otimes A)$$

for every nonnegative integer $$k$$ and every $$\mathbb{Z}G$$-module $$A$$.
It turns out that $$C$$ is always $$H^n(G;\mathbb{Z}(G))$$
and that $$G$$ is therefore of cohomological dimension $$n$$.

Many groups are duality groups without being Poincaré duality groups;
Bieri–Eckmann give the example of knot groups.
Bestvina–Feighn proved that any finite-index torsion-free subgroup of $$\operatorname{Out}(F_n)$$ 
is another example.

[previous postcard]: {% link _posts/2021-06-09-A-Mathematical-Postcard.md %}
[one of the big mapping class groups posts]: {% link _posts/2022-08-11-Ends-of-Surfaces.md %}
[Milnor–Schwarz lemma]: {% link _posts/2022-08-10-Groups-as-Metric-Spaces.md %}
[quasi-isometric]: {% link _posts/2021-07-01-Gromov-hyperbolicity-for-arbitrary-metric-spaces.md %}
[Brick]: https://core.ac.uk/download/pdf/81947848.pdf
[Alonso]: https://core.ac.uk/download/pdf/82621017.pdf
