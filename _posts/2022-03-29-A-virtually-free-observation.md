---
layout: post
math: true
---
[Martin Pettet][virtually free finite out] characterized which virtually free groups
have finite outer automorphism group.
[Krstić and Vogtmann][equivariant outer space] studied what I'll call
the "spine of reduced Outer Space" for a virtually free group
and gave a formula for computing its dimension.
I want to point out that the dimension of this complex can be arbitrarily big
even when the virtually free group has finite outer automorphism group,
so this post will be given to understanding a particular example.

Pettet's full conditions are somewhat technical.
Recall that a theorem of Karrass, Pietrowski and Solitar
characterizes the finitely generated virtually free groups
as those groups which are the fundamental group of a finite graph of finite groups.
To get a clean statement about those virtually free groups $$G$$
for which $$\operatorname{Out}(G)$$ is finite,
Pettet needs to allow valence-one vertices of the corresponding graph of groups to have
finite-by-(infinite cyclic) vertex groups.
It should be possible to translate his statement into a statement
purely about graphs of finite groups,
where certain "lollipop" subgraphs are allowed special behavior
but I haven't thought enough about how to go about doing that.

We'll restrict ourselves to finite trees of finite groups $$\mathcal{G}$$.
In Pettet's language, such a graph of groups $$\mathcal{G}$$ is *irreducible*
if no edge-to-vertex group inclusion is surjective.
In the language we have been developing over the past couple posts,
I would prefer to say that $$\mathcal{G}$$ is *reduced,*
since it is not possible to collapse an edge of $$\mathcal{G}$$
without either changing the fundamental group of the graph of groups 
or introducing an infinite vertex group.
The following is a sufficient (but not necessary) condition for $$\operatorname{Out}(\pi_1(\mathcal{G}))$$
to be finite.

- For each oriented edge $$e \in \mathcal{G}$$,
the normalizer of $$\iota_e(\mathcal{G}_e)$$ in $$\pi_1(\mathcal{G})$$ is finite.

The graph of groups I have in mind is the following:
the underlying graph is a tree with $$n-1$$ leaves and only one non-leaf vertex.
The vertex groups are all the symmetric group on 3 letters, $$S_3$$,
and the edge groups are all cyclic of order 2.
The fundamental group of this graph of groups 
is the amalgamated free product of $$n$$ copies of $$S_3$$ with a cyclic  group of order 2 amalgamated,
so has presentation

$$\langle a_1,\ldots, a_n,t : a_1^3 = \cdots = a_n^3 = t^2 = 1,\ ta_it^{-1} = a_i^{-1} \rangle.$$

In terms of this presentation, each $$\iota_e(\mathcal{G}_e)$$ is the cyclic group $$\langle t\rangle$$.
This subgroup is its own normalizer in $$\pi_1(\mathcal{G})$$.
Perhaps the easiest way to see this is to note that the fixed-point set of $$t$$
on the Bass–Serre tree of $$\mathcal{G}$$ is finite:
it includes one whole fundamental domain of the action but can go no further.
Since the normalizer preserves the fixed-point set, it must be finite.
Therefore the sufficient condition of Pettet mentioned above applies,
and we conclude $$\operatorname{Out}(\pi_1(\mathcal{G}))$$ is finite.

On the other hand, $$\mathcal{G}$$ contains *ideal edges* in the sense of the previous post.
The idea is that given any subset (including all) 
of the $$n-1$$ oriented edges incident to the center vertex,
we can create a new graph of groups by pulling those edges away from the center vertex
and attach them to a new vertex whose vertex group will be cyclic of order 2.
Nothing prevents us from continuing this process
until the resulting graph of groups $$\mathcal{G}'$$
has all interior vertices trivalent with $$C_2$$ vertex group,
all leaf vertices with $$S_3$$ vertex group,
and all edge groups $$C_2$$.
At this stage, an Euler characteristic argument shows that $$\mathcal{G}'$$ has $$n-2$$ vertices 
with $$C_2$$ vertex group,
while $$\mathcal{G}$$ had none.
A chain of $$n-2$$ edge collapses recovering $$\mathcal{G}$$ from $$\mathcal{G}'$$
shows that the complex studied by Krstić and Vogtmann has dimension at least (and in fact equal to) $$n-2$$.
Thus  we have shown that Krstić and Vogtmann's complex
can overestimate the *virtual cohomological dimension*
of $$\operatorname{Out}(\pi_1(\mathcal{G}))$$ by an arbitrary amount,
since the virtual cohomological dimension of a finite group is zero.

[virtually free finite out]: https://www.ams.org/journals/tran/1997-349-11/S0002-9947-97-01699-1/S0002-9947-97-01699-1.pdf
[equivariant outer space]: https://www.researchgate.net/publication/226534036_Equivariant_outer_space_and_automorphisms_of_free-by-finite_groups/link/5762c70508aee61395bef5dc/download
