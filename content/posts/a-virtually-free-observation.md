---
title: "A Virtually Free Observation"
date: 2022-03-29T15:13:50-04:00
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
To get a clean statement about those virtually free groups {{< katex >}}$G${{< /katex >}}
for which {{< katex >}}$\operatorname{Out}(G)${{< /katex >}} is finite,
Pettet needs to allow valence-one vertices of the corresponding graph of groups to have
finite-by-(infinite cyclic) vertex groups.
It should be possible to translate his statement into a statement
purely about graphs of finite groups,
where certain "lollipop" subgraphs are allowed special behavior
but I haven't thought enough about how to go about doing that.

We'll restrict ourselves to finite trees of finite groups {{< katex >}}$\mathcal{G}${{< /katex >}}.
In Pettet's language, such a graph of groups {{< katex >}}$\mathcal{G}${{< /katex >}} is *irreducible*
if no edge-to-vertex group inclusion is surjective.
In the language we have been developing over the past couple posts,
I would prefer to say that {{< katex >}}$\mathcal{G}${{< /katex >}} is *reduced,*
since it is not possible to collapse an edge of {{< katex >}}$\mathcal{G}${{< /katex >}}
without either changing the fundamental group of the graph of groups 
or introducing an infinite vertex group.
The following is a sufficient (but not necessary) condition for {{< katex >}}$\operatorname{Out}(\pi_1(\mathcal{G}))${{< /katex >}}
to be finite.

- For each oriented edge {{< katex >}}$e \in \mathcal{G}${{< /katex >}},
the normalizer of {{< katex >}}$\iota_e(\mathcal{G}_e)${{< /katex >}} in {{< katex >}}$\pi_1(\mathcal{G})${{< /katex >}} is finite.

The graph of groups I have in mind is the following:
the underlying graph is a tree with {{< katex >}}$n-1${{< /katex >}} leaves and only one non-leaf vertex.
The vertex groups are all the symmetric group on 3 letters, {{< katex >}}$S_3${{< /katex >}},
and the edge groups are all cyclic of order 2.
The fundamental group of this graph of groups 
is the amalgamated free product of {{< katex >}}$n${{< /katex >}} copies of {{< katex >}}$S_3${{< /katex >}} with a cyclic  group of order 2 amalgamated,
so has presentation

{{< katex >}}$\langle a_1,\ldots, a_n,t : a_1^3 = \cdots = a_n^3 = t^2 = 1,\ ta_it^{-1} = a_i^{-1} \rangle.${{< /katex >}}

In terms of this presentation, each {{< katex >}}$\iota_e(\mathcal{G}_e)${{< /katex >}} is the cyclic group {{< katex >}}$\langle t\rangle${{< /katex >}}.
This subgroup is its own normalizer in {{< katex >}}$\pi_1(\mathcal{G})${{< /katex >}}.
Perhaps the easiest way to see this is to note that the fixed-point set of {{< katex >}}$t${{< /katex >}}
on the Bass–Serre tree of {{< katex >}}$\mathcal{G}${{< /katex >}} is finite:
it includes one whole fundamental domain of the action but can go no further.
Since the normalizer preserves the fixed-point set, it must be finite.
Therefore the sufficient condition of Pettet mentioned above applies,
and we conclude {{< katex >}}$\operatorname{Out}(\pi_1(\mathcal{G}))${{< /katex >}} is finite.

On the other hand, {{< katex >}}$\mathcal{G}${{< /katex >}} contains *ideal edges* in the sense of the previous post.
The idea is that given any subset (including all) 
of the {{< katex >}}$n-1${{< /katex >}} oriented edges incident to the center vertex,
we can create a new graph of groups by pulling those edges away from the center vertex
and attach them to a new vertex whose vertex group will be cyclic of order 2.
Nothing prevents us from continuing this process
until the resulting graph of groups {{< katex >}}$\mathcal{G}'${{< /katex >}}
has all interior vertices trivalent with {{< katex >}}$C_2${{< /katex >}} vertex group,
all leaf vertices with {{< katex >}}$S_3${{< /katex >}} vertex group,
and all edge groups {{< katex >}}$C_2${{< /katex >}}.
At this stage, an Euler characteristic argument shows that {{< katex >}}$\mathcal{G}'${{< /katex >}} has {{< katex >}}$n-2${{< /katex >}} vertices 
with {{< katex >}}$C_2${{< /katex >}} vertex group,
while {{< katex >}}$\mathcal{G}${{< /katex >}} had none.
A chain of {{< katex >}}$n-2${{< /katex >}} edge collapses recovering {{< katex >}}$\mathcal{G}${{< /katex >}} from {{< katex >}}$\mathcal{G}'${{< /katex >}}
shows that the complex studied by Krstić and Vogtmann has dimension at least (and in fact equal to) {{< katex >}}$n-2${{< /katex >}}.
Thus  we have shown that Krstić and Vogtmann's complex
can overestimate the *virtual cohomological dimension*
of {{< katex >}}$\operatorname{Out}(\pi_1(\mathcal{G}))${{< /katex >}} by an arbitrary amount,
since the virtual cohomological dimension of a finite group is zero.

[virtually free finite out]: https://www.ams.org/journals/tran/1997-349-11/S0002-9947-97-01699-1/S0002-9947-97-01699-1.pdf
[equivariant outer space]: https://www.researchgate.net/publication/226534036_Equivariant_outer_space_and_automorphisms_of_free-by-finite_groups/link/5762c70508aee61395bef5dc/download
