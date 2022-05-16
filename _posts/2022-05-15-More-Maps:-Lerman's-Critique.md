---
layout: post
math: true
---
[Lerman] critiques the category of étale groupoids with arrows generalized maps
by arguing that there is a problem with gluing maps.
The purpose of this blog post is to try to digest this critique.
We follow the notation set up in the previous two blog posts.

Lerman's critique takes place in the realm of bibundles,
but as we saw in the [previous post],
it's possible to translate from the bibundles point of view to the generalized maps point of view.

Lerman's bibundles $$X$$ and $$Y$$ are from $$S^1$$, 
thought of as a groupoid with only identity arrows,
to $$C_2$$, thought of as a groupoid with one object.
If you chase through the definitions,
you see that a bibundle is thus a principal $$C_2$$ bundle over $$S^1$$.
There are two: the trivial bundle $$S^1\times C_2$$
and the nontrivial bundle which is $$S^1$$ double covering itself.
Call the former $$X$$ and the latter $$Y$$.
The former bundle has a global section and so ought to be represented by an honest functor $$S^1 \to C_2$$.
There is only one such functor, sending every object of $$S^1$$ to the unique object of $$C_2$$
and sending all the arrows to the identity.

For the nontrivial bundle $$Y$$,
we can choose contractible open neighborhoods $$U_1$$ and $$U_2$$ which cover $$S^1$$
and on which there exist local sections $$s_1$$ and $$s_2$$.
The groupoid $$(S^1)^{\mathcal{U}}$$ has space of objects the disjoint copy of two open intervals in $$\mathbb{R}$$
and space of arrows of the form
$$(1_x)_{j,i} \colon x_i \to x_j$$ for $$x \in U_i \cap U_j$$.
Topologically this space of arrows is a copy of the object space (for the identity arrows)
together with two copies of the intersection $$U_1 \cap U_2$$ (which is disconnected),
one for arrows of the form $$(1_x)_{1,2}$$ and another for the arrows $$(1_x)_{2,1}$$.

Aha! Think about the definition of these local sections:
on one component of the intersection $$U_1\cap U_2$$, the sections agree,
while on the other, they differ by the action of $$C_2$$.

![The nontrivial bundle with its local sections](/assets/img/circlebundle.jpeg)

In other words, if we chase through the construction given in the [previous post],
we see that the resulting functor $$(S^2)^{\mathcal{U}} \to C_2$$
sends all identity arrows to the identity arrow of $$C_2$$ (as they must be sent),
and for $$x$$ in the first component of $$U_1 \cap U_2$$,
the arrows $$(1_x)_{1,2}$$ and $$(1_x)_{2,1}$$ are sent to the identity,
while for all $$x$$ in the second component of $$U_1 \cap U_2$$,
the arrows $$(1_x)_{1,2}$$ and $$(1_x)_{2,1}$$ are sent to the nontrivial arrow in $$C_2$$.

It's clear in bibundle land that these are the two isomorphism classes of maps from $$S^1$$ to $$C_2$$,
and I think I buy in generalized map land that any generalized map will be one of these two as well.

The complaint, if I understand it, is this:
we can also define the functor associated to the trivial bundle on the open cover $$\mathcal{U}$$.
If you restrict either of these functors to either $$U_1$$ or $$U_2$$,
you get the same map: since $$U_1$$ and $$U_2$$ are contractible, the only principal $$C_2$$-bundles
over $$U_1$$ and $$U_2$$ are trivial.
This is slightly less clear in generalized maps land:
you could imagine cutting up an open interval into a couple pieces and having some of the
identifying arrows on the overlaps map to the nontrivial arrow in $$C_2$$.
The point, though, is that you can undo this difference with a natural transformation,
essentially because the subintervals you slice into only overlap their neighbors once,
not twice as in the example above.

I think this is a serious issue:
imagine having only the functors from $$U_1$$ and $$U_2$$ to $$C_2$$.
There's only one choice of functor and only one generalized map.
Nevertheless, when you try to glue these maps together to give you a new map from $$S^1$$ to $$C_2$$,
you find that there are *two* possible maps!
What's worse, since $$U_1$$ and $$U_2$$ don't see the arrows on the overlaps,
there's *no way* to tell from the restriction which of the two maps you're trying to end up with!

[Lerman]: https://ems.press/content/serial-article-files/6839
[previous post]: {% link _posts/2022-05-15-Maps-of-étale-groupoids.md %}
