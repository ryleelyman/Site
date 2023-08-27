---
title: "Locally Coarsely Bounded Mapping Class Groups"
date: 2022-08-17T16:18:43-04:00
math: true
---
This is the fourth post in a series on Katie Mann and Kasra Rafi's paper
[Large-scale geometry of big mapping class groups](https://arxiv.org/abs/1912.10914).
Truth be told, I've made many abortive attempts at writing this post.
I want to describe the classification of locally coarsely bounded mapping class groups
in a way that is useful and not too technical.
I'm going to try and talk through two examples 
that Mann–Rafi give at the beginning of the paper,
and then state the classification theorem at the end of the section.

## A locally coarsely bounded example

Consider the following surface {{< katex >}}$\Sigma${{< /katex >}} first introduced in the [first post] in the series.

![The surface {{< katex >}}$\Sigma${{< /katex >}}](/img/infinitetypesurface.jpeg)

As a reminder, {{< katex >}}$\Sigma${{< /katex >}} has three maximal ends,
two of which are accumulated by punctures (isolated, planar ends),
and two of which are accumulated by genus;
the two sets of two overlap in exactly one end.

Consider a pair of pants {{< katex >}}$P${{< /katex >}} in {{< katex >}}$\Sigma${{< /katex >}} which separates each of the maximal ends from the others.
I claim that {{< katex >}}$U_P${{< /katex >}},
the set of mapping classes which have representative homeomorphisms preserving {{< katex >}}$P${{< /katex >}}
and restricting to the identity on {{< katex >}}$P${{< /katex >}},
is a coarsely bounded neighborhood of the identity in {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}.

How would one go about showing this?
To say that {{< katex >}}$U_P${{< /katex >}} is coarsely bounded says that for any neighborhood {{< katex >}}$U${{< /katex >}} of the identity,
there exists a finite set {{< katex >}}$F${{< /katex >}} in {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}} and {{< katex >}}$k \ge 1${{< /katex >}}
such that {{< katex >}}$U_P \subset (FU)^k${{< /katex >}}.
Now, {{< katex >}}$U${{< /katex >}} contains a neighborhood of the form {{< katex >}}$U_S${{< /katex >}},
where {{< katex >}}$S \supset P${{< /katex >}} is a finite-type subsurface.
We will show that there is a finite set {{< katex >}}$F${{< /katex >}} and {{< katex >}}$k \ge 1${{< /katex >}}
so that if {{< katex >}}$[g] \in \operatorname{Map}(\Sigma)${{< /katex >}} satisfies {{< katex >}}$g|_P = 1${{< /katex >}},
then {{< katex >}}$g \in (FU_S)^k${{< /katex >}}, hence in {{< katex >}}$(FU)^k${{< /katex >}}.

Now, since {{< katex >}}$g|_P = 1${{< /katex >}} and {{< katex >}}$\Sigma - P${{< /katex >}} has three components,
we may write {{< katex >}}$g${{< /katex >}} as {{< katex >}}$g_1g_2g_3${{< /katex >}},
where each {{< katex >}}$g_i${{< /katex >}} is supported on a component of {{< katex >}}$\Sigma - P${{< /katex >}}.
We will focus on each {{< katex >}}$g_i${{< /katex >}} separately.

Given one of the maximal ends {{< katex >}}$\xi${{< /katex >}}, consider a subsurface {{< katex >}}$\Sigma_\xi${{< /katex >}} of {{< katex >}}$\Sigma${{< /katex >}}
in the complement of {{< katex >}}$S${{< /katex >}}
with one boundary component and having {{< katex >}}$\xi${{< /katex >}} as an end.
For example, maybe {{< katex >}}$\xi${{< /katex >}} is the end accumulated only by punctures
and {{< katex >}}$\Sigma_\xi${{< /katex >}} is determined by a curve in the complement of {{< katex >}}$S${{< /katex >}}
which cuts off {{< katex >}}$\xi${{< /katex >}} from the other two ends.
We will construct a homeomorphism {{< katex >}}$f_\xi \colon \Sigma \to \Sigma${{< /katex >}}
with the property that {{< katex >}}$f_\xi(\Sigma_\xi)${{< /katex >}} contains (up to isotopy)
the complementary component of {{< katex >}}$\Sigma - P${{< /katex >}} with end {{< katex >}}$\xi${{< /katex >}}.

Here is the construction:
since two (this is important) ends of {{< katex >}}$\Sigma${{< /katex >}} are accumulated by punctures,
we can embed a "strip of punctures" into {{< katex >}}$\Sigma${{< /katex >}} in a proper way.
By a strip of punctures I mean begin with an infinite strip {{< katex >}}$\mathbb{R} \times [0,1]${{< /katex >}},
and then remove each point of the form {{< katex >}}$(n, \frac 12)${{< /katex >}} for {{< katex >}}$n \in \mathbb{Z}${{< /katex >}}.
The homeomorphism {{< katex >}}$f_\xi${{< /katex >}} will be supported on this strip of punctures,
and what it does is "shift" the punctures by some integer,
sending the (missing) points {{< katex >}}$(n,\frac 12)${{< /katex >}} to {{< katex >}}$(n + m, \frac 12)${{< /katex >}} for some fixed integer {{< katex >}}$m${{< /katex >}},
and then tapering to the identity on the boundary 
{{< katex >}}$\mathbb{R} \times \{0\}${{< /katex >}} and {{< katex >}}$\mathbb{R} \times\{1\}${{< /katex >}}.
Here is a picture with an arc {{< katex >}}$\gamma${{< /katex >}} 
connecting the two boundary components illustrated along with its image {{< katex >}}$f_\xi(\gamma)${{< /katex >}}.

![Shifting a strip of punctures](/img/punctureshift.jpeg)

Anyway, you should convince yourself that by choosing the shift map {{< katex >}}$f_\xi${{< /katex >}} appropriately,
we may satisfy the condition that {{< katex >}}$f_\xi(\Sigma_\xi)${{< /katex >}} contains the complementary component
of {{< katex >}}$\Sigma - P${{< /katex >}} with maximal end {{< katex >}}$\xi${{< /katex >}},
at least up to isotopy.
So if {{< katex >}}$g_i${{< /katex >}} is supported on that complementary component {{< katex >}}$C${{< /katex >}},
{{< katex >}}$f_\xi^{-1} g f_\xi${{< /katex >}} is supported on {{< katex >}}$f_\xi^{-1}(C)${{< /katex >}}, which is, up to isotopy,
contained in {{< katex >}}$\Sigma - S${{< /katex >}}!

The story is similar for the end accumulated by genus;
instead of shifting a strip of punctures, we shift a "strip of handles".
For the end accumulated by both genus and punctures,
we shift *both* a strip of handles and a strip of punctures off to different ends.
The finite set {{< katex >}}$F${{< /katex >}} is the set of all these shift maps and their inverses,
and {{< katex >}}$k${{< /katex >}} is, doing a little arithmetic, {{< katex >}}$2 \cdot 3 = 6${{< /katex >}},
since each {{< katex >}}$g_i${{< /katex >}} is in {{< katex >}}$FU_SF${{< /katex >}}.

## A non-example

Now consider a surface {{< katex >}}$\Sigma'${{< /katex >}} that is similar to {{< katex >}}$\Sigma${{< /katex >}}
except that only one maximal end is accumulated by punctures,
and the other two are accumulated by genus only.

![The surface {{< katex >}}$\Sigma'${{< /katex >}}](/img/infinitetypenonexample.jpeg)

With {{< katex >}}$\Sigma${{< /katex >}}, we made use of the fact that {{< katex >}}$P${{< /katex >}} separated each of the finitely many
maximal (types) of ends into self-similar neighborhoods.
We can mimic this construction to define finite-type subsurfaces {{< katex >}}$P'${{< /katex >}} of {{< katex >}}$\Sigma'${{< /katex >}};
for example a pair of pants which separates all the punctures from all the genus
and also separates the two ends accumulated by genus.
But a key feature of {{< katex >}}$\Sigma${{< /katex >}} is missing from {{< katex >}}$\Sigma'${{< /katex >}}:
we cannot shift a strip of punctures away from one end and toward a different end.
This changes the situation so much that I claim the following:
no matter what finite-type subsurface {{< katex >}}$P'${{< /katex >}} of {{< katex >}}$\Sigma'${{< /katex >}} you choose,
{{< katex >}}$\Sigma' - P'${{< /katex >}} contains a finite-type subsurface which is nondisplaceable in {{< katex >}}$\Sigma'${{< /katex >}}.
This implies, by our observation in [a previous post],
that {{< katex >}}$U_{P'}${{< /katex >}} is not coarsely bounded,
so since {{< katex >}}$P'${{< /katex >}} was arbitrary and the sets of the form {{< katex >}}$U_{P'}${{< /katex >}} 
as {{< katex >}}$P'${{< /katex >}} varies
forms a neighborhood basis of the identity
in {{< katex >}}$\operatorname{Map}(\Sigma')${{< /katex >}},
we see that {{< katex >}}$\operatorname{Map}(\Sigma')${{< /katex >}} is not locally coarsely bounded.

To see that {{< katex >}}$\Sigma' - P'${{< /katex >}} contains a nondisplaceable finite-type subsurface,
take an annulus {{< katex >}}$A${{< /katex >}} in the complement of {{< katex >}}$P'${{< /katex >}}
whose core curve separates the end {{< katex >}}$\xi${{< /katex >}} accumulated by punctures
from {{< katex >}}$P'${{< /katex >}} and the two ends accumulated by genus.
Note that there are finitely many punctures in one component of the complement of {{< katex >}}$A${{< /katex >}},
and although the punctures themselves do not have to be preserved by
a homeomorphism {{< katex >}}$f\colon \Sigma' \to \Sigma'${{< /katex >}},
the number of punctures in the component of {{< katex >}}$\Sigma' - f(A)${{< /katex >}}
not containing {{< katex >}}$\xi${{< /katex >}} in its end set remains the same, call it {{< katex >}}$N${{< /katex >}}.
The core curve of {{< katex >}}$A${{< /katex >}} is, up to isotopy, the only curve separating these particular {{< katex >}}$N${{< /katex >}} punctures
and all the genus of {{< katex >}}$\Sigma'${{< /katex >}} from {{< katex >}}$\xi${{< /katex >}}.
But if we swap any of the {{< katex >}}$N${{< /katex >}} punctures for different punctures
via some homeomorphism {{< katex >}}$f${{< /katex >}},
then {{< katex >}}$f(A)${{< /katex >}} and {{< katex >}}$A${{< /katex >}} must intersect!
Thus, while strictly speaking {{< katex >}}$A${{< /katex >}} may not be nondisplaceable 
(push it off of itself entirely by a homeomorphism isotopic to the identity),
any sufficiently complex finite-type subsurface containing {{< katex >}}$A${{< /katex >}} will be nondisplaceable.

## The statement of the classification theorem

These two examples demonstrate the key ideas of the classification theorem:
if {{< katex >}}$\Sigma${{< /katex >}} is to be locally coarsely bounded,
there must be, it's not too hard to argue, finitely many types of maximal ends.

If {{< katex >}}$U_S${{< /katex >}} is to be a coarsely bounded neighborhood of the identity in {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}},
it turns out {{< katex >}}$S${{< /katex >}} must separate the maximal ends of different types from each other,
each complementary component must have infinite or zero genus 
(otherwise we would find nondisplaceable subsurfaces)
and each maximal end must have not only a self-similar neighborhood determined by the decomposition,
but it must be so strongly self-similar that we can construct these
"shift" homeomorphisms like we did in the example of {{< katex >}}$\Sigma${{< /katex >}}.

As it happens, {{< katex >}}$S${{< /katex >}} is allowed to additionally cut off some infinite-type pieces
which contain no maximal end—as long as we can move these "peripheral" pieces
into some piece containing some maximal ends.

There is one exceptional case to the discussion above 
that isn't well-spelled out in the Mann–Rafi paper:
if {{< katex >}}$\Sigma${{< /katex >}} has finitely many punctures,
then punctures are maximal ends.
It is convenient to insist that each component of {{< katex >}}$\Sigma - S${{< /katex >}} have infinite type,
but we cannot do this and also insist that the punctures have their own self-similar neighborhoods:
such a neighborhood in {{< katex >}}$\Sigma${{< /katex >}} would be just the puncture itself,
which clearly does not have infinite type.
Fortunately in this case the answer is clear: just include the punctures in {{< katex >}}$S${{< /katex >}}.

Here is a possibly too verbose statement of the theorem.

> **Theorem 5.7** ([Mann–Rafi]).
There exists a coarsely bounded neighborhood of the identity in {{< katex >}}$\operatorname{Map}(\Sigma)${{< /katex >}}
if and only if there exists a finite-type subsurface {{< katex >}}$S${{< /katex >}} of {{< katex >}}$\Sigma${{< /katex >}} with the following properties.

> (1) Each boundary component of {{< katex >}}$S${{< /katex >}} is separating, each complementary component of {{< katex >}}$\Sigma - S${{< /katex >}}
is of infinite type and has infinite or zero genus.

> (2) Each of the finitely many complementary components of {{< katex >}}$\Sigma - S${{< /katex >}} 
are either "big" or "small" according to whether
their end sets contain a maximal end or not.
If {{< katex >}}$C${{< /katex >}} is a "big" component, each maximal end of {{< katex >}}$C${{< /katex >}} is in fact maximal in {{< katex >}}$\Sigma${{< /katex >}}.

> (3) The end sets of "big" components are self-similar
(and so contain either a single maximal end or a Cantor set of maximal ends of the same type)
and for each maximal end {{< katex >}}$\xi${{< /katex >}} in a "big" component {{< katex >}}$C${{< /katex >}},
there exists, for any subsurface {{< katex >}}$\Sigma_\xi${{< /katex >}} with one boundary component containing {{< katex >}}$\xi${{< /katex >}}
in its end set,
a homeomorphism {{< katex >}}$f \colon \Sigma \to \Sigma${{< /katex >}}
with the property that {{< katex >}}$f(\Sigma_\xi) \supset C${{< /katex >}}.

> (4) For each "small" component {{< katex >}}$P${{< /katex >}}, there exists a "big" component {{< katex >}}$C${{< /katex >}}
and a homeomorphism {{< katex >}}$f\colon \Sigma \to \Sigma${{< /katex >}} exchanging {{< katex >}}$P${{< /katex >}} with a subsurface of {{< katex >}}$C${{< /katex >}};
equivalently the end set of {{< katex >}}$P${{< /katex >}} is homeomorphic to a clopen subset of the end set of {{< katex >}}$C${{< /katex >}}.

> Moreover, if such a subsurface {{< katex >}}$S${{< /katex >}} exists, 
{{< katex >}}$U_S${{< /katex >}} is a coarsely bounded neighborhood of the identity.
We may always take {{< katex >}}$S${{< /katex >}} to have genus zero if {{< katex >}}$S${{< /katex >}} has infinite genus,
and genus equal to the genus of {{< katex >}}$\Sigma${{< /katex >}} otherwise.
If {{< katex >}}$\Sigma${{< /katex >}} has finitely many punctures, we may assume {{< katex >}}$S${{< /katex >}} contains all of them.

[first post]: {{< ref "ends-of-surfaces.md" >}}
[Mann–Rafi]: https://arxiv.org/abs/1912.10914
[a previous post]: {{< ref "nondisplaceable-subsurfaces.md" >}}
