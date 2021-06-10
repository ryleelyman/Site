---
layout: post
math: true
published: true
---
I submitted a "mathematical postcard" (see below)
to the [Nearly Carbon Neutral Geometric Topology][NCNGT] conference.
The purpose of this post is to share the postcard
and offer a little more context and explanation for it.
I'm also giving a talk in said conference,
but I'll talk about that in a separate post.

Here is the postcard:

<iframe src="/assets/pdfs/postcard.pdf" width="100%" height="400px">
</iframe>

Let me say a little more about the space we're talking about.
Let

$$F = A_1*\dotsb*A_n*F_k$$

be a free product of the groups $$A_1,\dotsc,A_n$$ with a free group of rank $$k$$.
It follows from elementary Bass--Serre theory
that $$F$$ acts on a (simplicial) tree $$T$$ with trivial edge stabilizers
and vertex stabilizers each conjugate to some $$A_i$$.
Let's assume that the action is *minimal,* i.e. that there is no proper invariant subtree.
Say two such trees $$S$$ and $$T$$ are *equivalent* if there is an $$F$$-equivariant homeomorphism from $$S$$ to $$T$$.
It turns out that there are many inequivalent, minimal actions!

[Guirardel and Levitt][GuirardelLevitt] define an Outer Space to parametrize them all
(up to a finer notion of equivalence: isometry).
It is a topological space on which the group of those outer automorphisms of $$F$$
which preserve the conjugacy classes of the $$A_i$$ acts.
If the $$A_i$$ are *freely indecomposable,* for example, if they are finite,
then this is all of $$\operatorname{Out}(F)$$.
This Outer Space admits a *spine,*
a subspace which is a simplicial complex
and onto which it deformation retracts $$\operatorname{Out}(F)$$-equivariantly.
Vertices of the spine are equivalence classes of minimal actions as above.
Two vertices are connected by an edge when one can be obtained from the other by collapsing an orbit of edges.
When $$n \ge 2$$, the dimension of this spine is $$n + 2k - 2$$.

When each $$A_i$$ is finite, the spine is locally finite,
and $$\operatorname{Out}(F)$$ acts with finite stabilizers and finite quotient.
This is the bread-and-butter situation for geometric group theory,
so outer automorphism groups of free products of finite and cyclic groups are interesting to study as a class
because one can use the geometry of the spine of Outer Space to investigate them.

Again by Bass--Serre theory, one can think of vertices of the spine
via their quotient graphs of groups $$\mathcal{G}$$,
as is happening in the postcard.
These quotient graphs of groups will have first Betti number $$k$$
and $$n$$ vertices with nontrivial vertex group each isomorphic to one of the $$A_i$$.

The combinatorial types of the examples in the postcard play a particularly special role
in studying the spine of Outer Space.
I call vertices combinatorially equivalent to the first and last examples *thistles*
with $$n$$ prickles and $$k$$ petals (here $$n = 3$$ and $$k = 4$$).
Vertices combinatorially equivalent to the middle examples are *bugs*
with a head, $$n-1$$ legs and $$k$$ wings.

One reason thistles and bugs are special is illustrated in the postcard:
*collapse Whitehead moves* along with their cousins *expand Whitehead moves,*
form a system of paths in the spine of Outer Space that connect any two thistles to each other.
[Collins and Zieschang][CollinsZieschang] prove a version of Whitehead's algorithm for free products
using in particular two families of *Whitehead automorphisms* that they call $$S$$-Whitehead automorphisms
and $$J$$-multiple Whitehead automorphisms.
The former correspond to expand Whitehead moves, and the latter to collapse Whitehead moves,
and their result says that any two thistles in the spine of Outer Space may be connected by a path of Whitehead moves
which has a very nice interplay with a *norm* one can put on thistles.

![An expand Whitehead move](/assets/img/expandWhitehead.png)

Let me finish by indicating my interest in these paths:
[Vogtmann][Vogtmann] proved that the outer automorphism group of a free group of rank $$k$$
is what's called *simply connected at infinity* for $$k \ge 5$$.
Briefly, a space $$X$$ is simply connected at infinity if it has one [end][ends] 
and for any compact subset $$K$$,
there is a compact subset $$L$$ with $$L \supset K$$ such that
any loop in $$X\setminus L$$ is nullhomotopic via a homotopy in $$X\setminus K$$.
A group is simply connected at infinity if some (and hence any) simplicial complex
on which it acts with finite stabilizers and finite quotient is simply connected at infinity.
So $$\mathbb{R}$$ has two ends, $$\mathbb{R}^2$$ has one end but is not simply connected at infinity,
and $$\mathbb{R}^{n}$$ is simply connected at infinity for $$n \ge 3$$;
therefore $$\mathbb{Z}^n$$ is simply connected at infinity for $$n \ge 3$$.
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
