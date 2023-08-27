---
title: "More Maps: Lerman's Critique"
date: 2022-05-15T15:32:29-04:00
math: true
---
[Lerman] critiques the category of étale groupoids with arrows generalized maps
by arguing that there is a problem with gluing maps.
The purpose of this blog post is to try to digest this critique.
We follow the notation set up in the previous two blog posts.

Lerman's critique takes place in the realm of bibundles,
but as we saw in the [previous post],
it's possible to translate from the bibundles point of view to the generalized maps point of view.

Lerman's bibundles {{< katex >}}$X${{< /katex >}} and {{< katex >}}$Y${{< /katex >}} are from {{< katex >}}$S^1${{< /katex >}}, 
thought of as a groupoid with only identity arrows,
to {{< katex >}}$C_2${{< /katex >}}, thought of as a groupoid with one object.
If you chase through the definitions,
you see that a bibundle is thus a principal {{< katex >}}$C_2${{< /katex >}} bundle over {{< katex >}}$S^1${{< /katex >}}.
There are two: the trivial bundle {{< katex >}}$S^1\times C_2${{< /katex >}}
and the nontrivial bundle which is {{< katex >}}$S^1${{< /katex >}} double covering itself.
Call the former {{< katex >}}$X${{< /katex >}} and the latter {{< katex >}}$Y${{< /katex >}}.
The former bundle has a global section and so ought to be represented by an honest functor {{< katex >}}$S^1 \to C_2${{< /katex >}}.
There is only one such functor, sending every object of {{< katex >}}$S^1${{< /katex >}} to the unique object of {{< katex >}}$C_2${{< /katex >}}
and sending all the arrows to the identity.

For the nontrivial bundle {{< katex >}}$Y${{< /katex >}},
we can choose contractible open neighborhoods {{< katex >}}$U_1${{< /katex >}} and {{< katex >}}$U_2${{< /katex >}} which cover {{< katex >}}$S^1${{< /katex >}}
and on which there exist local sections {{< katex >}}$s_1${{< /katex >}} and {{< katex >}}$s_2${{< /katex >}}.
The groupoid {{< katex >}}$(S^1)^{\mathcal{U}}${{< /katex >}} has space of objects the disjoint copy of two open intervals in {{< katex >}}$\mathbb{R}${{< /katex >}}
and space of arrows of the form
{{< katex >}}$(1_x)_{j,i} \colon x_i \to x_j${{< /katex >}} for {{< katex >}}$x \in U_i \cap U_j${{< /katex >}}.
Topologically this space of arrows is a copy of the object space (for the identity arrows)
together with two copies of the intersection {{< katex >}}$U_1 \cap U_2${{< /katex >}} (which is disconnected),
one for arrows of the form {{< katex >}}$(1_x)_{1,2}${{< /katex >}} and another for the arrows {{< katex >}}$(1_x)_{2,1}${{< /katex >}}.

Aha! Think about the definition of these local sections:
on one component of the intersection {{< katex >}}$U_1\cap U_2${{< /katex >}}, the sections agree,
while on the other, they differ by the action of {{< katex >}}$C_2${{< /katex >}}.

![The nontrivial bundle with its local sections](/assets/img/circlebundle.jpeg)

In other words, if we chase through the construction given in the [previous post],
we see that the resulting functor {{< katex >}}$(S^2)^{\mathcal{U}} \to C_2${{< /katex >}}
sends all identity arrows to the identity arrow of {{< katex >}}$C_2${{< /katex >}} (as they must be sent),
and for {{< katex >}}$x${{< /katex >}} in the first component of {{< katex >}}$U_1 \cap U_2${{< /katex >}},
the arrows {{< katex >}}$(1_x)_{1,2}${{< /katex >}} and {{< katex >}}$(1_x)_{2,1}${{< /katex >}} are sent to the identity,
while for all {{< katex >}}$x${{< /katex >}} in the second component of {{< katex >}}$U_1 \cap U_2${{< /katex >}},
the arrows {{< katex >}}$(1_x)_{1,2}${{< /katex >}} and {{< katex >}}$(1_x)_{2,1}${{< /katex >}} are sent to the nontrivial arrow in {{< katex >}}$C_2${{< /katex >}}.

It's clear in bibundle land that these are the two isomorphism classes of maps from {{< katex >}}$S^1${{< /katex >}} to {{< katex >}}$C_2${{< /katex >}},
and I think I buy in generalized map land that any generalized map will be one of these two as well.

The complaint, if I understand it, is this:
we can also define the functor associated to the trivial bundle on the open cover {{< katex >}}$\mathcal{U}${{< /katex >}}.
If you restrict either of these functors to either {{< katex >}}$U_1${{< /katex >}} or {{< katex >}}$U_2${{< /katex >}},
you get the same map: since {{< katex >}}$U_1${{< /katex >}} and {{< katex >}}$U_2${{< /katex >}} are contractible, the only principal {{< katex >}}$C_2${{< /katex >}}-bundles
over {{< katex >}}$U_1${{< /katex >}} and {{< katex >}}$U_2${{< /katex >}} are trivial.
This is slightly less clear in generalized maps land:
you could imagine cutting up an open interval into a couple pieces and having some of the
identifying arrows on the overlaps map to the nontrivial arrow in {{< katex >}}$C_2${{< /katex >}}.
The point, though, is that you can undo this difference with a natural transformation,
essentially because the subintervals you slice into only overlap their neighbors once,
not twice as in the example above.

I think this is a serious issue:
imagine having only the functors from {{< katex >}}$U_1${{< /katex >}} and {{< katex >}}$U_2${{< /katex >}} to {{< katex >}}$C_2${{< /katex >}}.
There's only one choice of functor and only one generalized map.
Nevertheless, when you try to glue these maps together to give you a new map from {{< katex >}}$S^1${{< /katex >}} to {{< katex >}}$C_2${{< /katex >}},
you find that there are *two* possible maps!
What's worse, since {{< katex >}}$U_1${{< /katex >}} and {{< katex >}}$U_2${{< /katex >}} don't see the arrows on the overlaps,
there's *no way* to tell from the restriction which of the two maps you're trying to end up with!

[Lerman]: https://ems.press/content/serial-article-files/6839
[previous post]: {{< ref "maps-of-etale-groupoids.md" >}}
