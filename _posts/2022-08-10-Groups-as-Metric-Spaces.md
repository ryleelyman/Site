---
layout: post
math: true
---

A week ago I attended [Big Mapping Class Groups at BC](http://ianbiringer.net/bigmcg.html),
a workshop where participants, myself included,
presented on papers about mapping class groups of infinite-type surfaces that we did not write.
I'd like to spend a couple of posts talking about the paper I was assigned,
[Large scale geometry of big mapping class groups](https://arxiv.org/abs/1912.10914)
by [Katie Mann](https://e.math.cornell.edu/people/mann/) and [Kasra Rafi](https://www.math.toronto.edu/~rafi/).
This is post "zero" in that series; 
I want to describe the project of large scale geometry of groups.

## Groups as metric spaces

So, let's begin.
Let $$G$$ be a group,
and $$S$$ a symmetric generating set.
Here, *symmetric* means that if $$s$$ belongs to $$S$$, so does $$s^{-1}$$.
Every element $$g$$ of $$G$$ can be written as

$$g = s_1 s_2 \ldots s_n$$

where each $$s_i$$ belongs to $$S$$,
and we define the *word length* $$\|g\|$$ of $$g$$ to be the minimal $$n$$ possible.
By convention, the length of the identity element is zero.
This yields a *word metric* on $$G$$, where the distance $$d_S$$ between $$g$$ and $$h$$ is

$$d_S(g,h) = \|g^{-1}h\|.$$

A good exercise is to prove that $$d_S$$ *is* a metric
(i.e. it's symmetric, nonnegative, nonzero if $$g \ne h$$, and satisfies the triangle inequality)
that is additionally *left invariant,* in the sense that $$d_S(kg,kh) = d_S(g,h)$$
for all $$k \in G$$.
Note: symmetry of $$d_S$$ seems to require symmetry of $$S$$.
If you relaxed the requirement of symmetry,
you might get "asymmetric" metrics.

## Quasi-isometric invariance

Now, different choices of $$S$$ yield *a priori* different metrics.
But! In some cases, some "large-scale" features of the metric are actually properties of the group,
in the sense that $$d_S$$ and $$d_{S'}$$ are *quasi-isometric.*
I defined quasi-isometry in [this post](https://ryleealanza.org/2021/07/01/Gromov-hyperbolicity-for-arbitrary-metric-spaces.html),
but the rough idea (as it were) is that distances are distorted a uniformly bounded amount
both multiplicatively and additively.
The classic example of this is the following lemma, due independently to Milnor and Schwarz.

> **Lemma.** Suppose a group $$G$$ acts *properly discontinuously* and *cocompactly*
by isometries on a geodesic metric space $$(X,d)$$.
Then $$G$$ is finitely generated and $$(X,d)$$ is quasi-isometric
to $$(G,d_S)$$ for any finite, symmetric generating set $$S$$.

Here *properly discontinuously* means that for every compact subset $$K \subset X$$,
the set of group elements $$g \in G$$ such that $$g.K \cap K \ne \varnothing$$ is finite.
(If you know what a *proper* map of topological spaces is,
this is equivalent to the condition that the map $$G\times X \to X \times X$$
defined as $$(g,x) \mapsto (g.x, x)$$ is proper
when $$G$$ is given the discrete topology.)
*Cocompact* means the quotient $$G\backslash X$$ is compact.

Thus, any properties of the metric space $$(X,d)$$ that are invariant under quasi-isometry
(and, crucially, there are many such)
are actually properties of the group $$G$$!

A finitely generated group $$G$$ is quasi-isometric to any of its finite-index subgroups,
so quasi-isometry is a somewhat weak relation.
Actually, saying the word "relation" just reminded me:
Carlos Adrian Perez Estrada pointed out a [paper of Samuel Corson](https://arxiv.org/abs/1609.01353) 
to me that proves that the symmetry of the quasi-isometry relation 
is equivalent to the axiom of choice,
which I think is quite a cute fact.
But anyway, a natural question to ask is when are two finitely generated groups quasi-isometric?
More ambitiously, we could follow a program of Gromov:
distinguish finitely generated groups up to quasi-isometry.

## A Polish generalization

The setting of the Mann–Rafi paper is mapping class groups of infinite-type surfaces,
so you should think surfaces with an infinite number of punctures 
(or more complicated "end" behavior)
or infinite genus.
Unlike the mapping class group of a finite-type surface,
these groups are *uncountable* so certainly not finitely generated.
They come with two (equivalent) natural topologies:
Thinking of the mapping class group as a (continuous) quotient of the homeomorphism group
equipped with the compact–open topology yields one topology,
and the action of the mapping class group on the (countable) set of
isotopy classes of essential, simple closed curves on the surface
yields another called the *permutation topology.*
Unfortunately, even with these topologies, things are not so nice: 
these are not locally compact groups.
Nevertheless they do have a useful structure:
they're what are called *Polish groups,* meaning 
they have a countable dense subset and admit a complete metric inducing the topology.

[Christian Rosendal](http://homepages.math.uic.edu/~rosendal/)
proposed a framework for large-scale geometry of Polish groups.
A subspace $$A$$ of a Polish group $$G$$ is called *coarsely bounded*
if every *compatible* (i.e. inducing the topology) 
left-invariant metric $$d$$ on $$G$$ gives $$A$$ finite *diameter,*
in the sense that the supremum

$$\sup\{d(g,h) : g,\ h \in A\}$$

is finite.
Equivalently, in every continuous action of $$G$$ by isometries on a metric space $$X$$,
the orbit $$A.x$$ is bounded for every $$x \in X$$.
So *bounded,* yes, but also *coarsely* because the metric may change but boundedness does not.

The usefulness of the concept is the following theorem,
which you might think of as a kind of "Milnor–Schwarz lemma" for Polish groups.
A group is *locally coarsely bounded* if every element, or equivalently the identity,
has a coarsely bounded neighborhood.

> **Theorem** (Rosendal). If $$G$$ is locally coarsely bounded,
then the map $$g \mapsto g$$ is a quasi-isometry
from $$(G,d_S)$$ to $$(G,d_{S'})$$ for any symmetric, *analytic,* coarsely bounded generating sets
$$S$$ and $$S'$$ for $$G$$.

Here, *analytic* means the continuous image of another Polish space;
so for example any Borel subset will do.
Put another way, the theorem says that if a Polish group is both locally coarsely bounded
and generated by a coarsely bounded set,
then it has a well-defined quasi-isometry type.
One might ambitiously reframe Gromov's program,
asking instead to classify such Polish groups up to quasi-isometry.
Mann–Rafi take the first steps towards this program 
for mapping class groups of infinite-type surfaces.
