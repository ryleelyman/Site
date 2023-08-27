---
title: "Anderson's Trick"
date: 2022-10-30T16:42:15-04:00
math: true
---
This week I had the pleasure of attending a seminar talk
[Nick Vlamis](https://math.nickvlamis.com) gave at CUNY,
where he taught us a very pretty trick due to [Anderson](https://www.jstor.org/stable/2372842)
which one can use, as Anderson did,
to prove that the groups of orientation-preserving homeomorphisms 
of the {{< katex >}}$2${{< /katex >}}- and {{< katex >}}$3${{< /katex >}}-spheres are simple.
The purpose of this post is to reproduce Nick's exposition of the trick.

Suppose {{< katex >}}$g${{< /katex >}} is a homeomorphism of a surface {{< katex >}}$S${{< /katex >}}
(for me a surface is a Hausdorff and second countable {{< katex >}}$2${{< /katex >}}-manifold)
whose *support*

{{< katex >}}$\operatorname{Supp}(g) = \overline{\{x \in S : g(x) \ne x\}}${{< /katex >}}

is contained in the interior of some closed disk {{< katex >}}$D${{< /katex >}} in {{< katex >}}$S${{< /katex >}}.
Since {{< katex >}}$\operatorname{Supp}(g)${{< /katex >}} is closed,
there is in fact some closed disk {{< katex >}}$\Delta${{< /katex >}} properly contained in {{< katex >}}$D${{< /katex >}} 
and containing {{< katex >}}$\operatorname{Supp}(g)${{< /katex >}}.
In fact, we can find a countable sequence of disjoint disks
{{< katex >}}$\{\Delta_n\}_{n \in \mathbb{Z}}${{< /katex >}} with {{< katex >}}$\Delta = \Delta_0${{< /katex >}}, 
each contained in the interior of {{< katex >}}$D${{< /katex >}}.
Since a sequence of points, one from each disk must have a limit point in {{< katex >}}$D${{< /katex >}},
why don't we arrange the {{< katex >}}$\Delta_n${{< /katex >}} to *Hausdorff converge*
to a point {{< katex >}}$x_{+\infty}${{< /katex >}} as {{< katex >}}$n \to +\infty${{< /katex >}}
and a point {{< katex >}}$x_{-\infty}${{< /katex >}} as {{< katex >}}$n \to -\infty${{< /katex >}}.
Here's the picture.

![The countable disjoint union of disks and their two limit points](/img/anderson.jpeg)

Here's how we'll use these disks.
There is a homeomorphism {{< katex >}}$\varphi\colon D \to D${{< /katex >}} which shifts each {{< katex >}}$\Delta_n${{< /katex >}} to {{< katex >}}$\Delta_{n+1}${{< /katex >}}
and holds {{< katex >}}$x_{\pm\infty}${{< /katex >}} fixed.
Since the {{< katex >}}$\Delta_{n}${{< /katex >}} are pairwise disjoint,
if we choose distinct {{< katex >}}$n${{< /katex >}} and {{< katex >}}$m${{< /katex >}},
the homeomorphisms {{< katex >}}$\varphi^n g \varphi^{-n}${{< /katex >}} and {{< katex >}}$\varphi^m g \varphi^{-m}${{< /katex >}}
have disjoint support and thus commute.
Thus the infinite product
{{< katex >}}$\sigma = \prod_{n = 0}^\infty \varphi^n g\varphi^{-n}${{< /katex >}} makes sense 
as a homeomorphism whose support is contained in {{< katex >}}$D${{< /katex >}}.

> **Proposition.**
> 1. {{< katex >}}$[\sigma,\varphi] = \sigma\varphi\sigma^{-1}\varphi^{-1} = g${{< /katex >}}.
> 2. Suppose {{< katex >}}$f${{< /katex >}} is a homeomorphism of {{< katex >}}$S${{< /katex >}} satisfying {{< katex >}}$f(D) \cap D = \varnothing${{< /katex >}}
> and such that there exists a homeomorphism {{< katex >}}$\psi\colon S \to S${{< /katex >}} exchanging {{< katex >}}$D${{< /katex >}} and {{< katex >}}$f(D)${{< /katex >}}
> and satisfying {{< katex >}}$\psi|_D = f${{< /katex >}} and {{< katex >}}$\psi|_{f(D)} = \varphi f^{-1}${{< /katex >}}.
> Then any normal subgroup of {{< katex >}}$\operatorname{Homeo}(S)${{< /katex >}} containing {{< katex >}}$f${{< /katex >}} contains {{< katex >}}$g${{< /katex >}}.

*Proof.*
From the definition of {{< katex >}}$\sigma$$ we have ${{< /katex >}}\varphi\sigma^{-1}\varphi^{-1} 
= \prod_{n=1}^\infty \varphi^n g^{-1} \varphi^{-n}$$
from which it follows that {{< katex >}}$\sigma(\varphi\sigma^{-1}\varphi^{-1}) = g${{< /katex >}}.
We claim that {{< katex >}}$g = [\sigma,f]\psi [\sigma,f]\psi^{-1}.${{< /katex >}}
Expanding, we see that this is a product of conjugates of {{< katex >}}$f${{< /katex >}} and {{< katex >}}$f^{-1}${{< /katex >}} 
and is thus contained in any normal subgroup containing {{< katex >}}$f.${{< /katex >}}

To see that this product is really {{< katex >}}$g${{< /katex >}},
observe that since {{< katex >}}$\sigma${{< /katex >}} is supported on {{< katex >}}$D${{< /katex >}},
for {{< katex >}}$x \in D${{< /katex >}}, we have {{< katex >}}$\sigma f \sigma^{-1}f^{-1}(x) = \sigma(x)${{< /katex >}}.
On the other hand, for {{< katex >}}$x \in f(D)${{< /katex >}}, we have {{< katex >}}$\sigma f \sigma^{-1}f^{-1}(x) = \sigma^{-1}(x)${{< /katex >}}.
Thus if {{< katex >}}$x \in D${{< /katex >}}, 

$$\psi\sigma f \sigma^{-1}f^{-1}\psi^{-1}(x) = \psi\sigma f \sigma^{-1} f^{-1} f\varphi^{-1}(x) 
= \psi f \sigma^{-1} \varphi^{-1}(x) = \varphi \sigma^{-1} \varphi^{-1}(x)$$

which is in {{< katex >}}$D${{< /katex >}}, so further applying {{< katex >}}$\sigma f\sigma^{-1} f^{-1}${{< /katex >}} we obtain
{{< katex >}}$\sigma \varphi \sigma^{-1} \varphi^{-1}(x) = g(x)${{< /katex >}}.

Next, if {{< katex >}}$x \in f(D)${{< /katex >}}, we have {{< katex >}}$\psi^{-1}(x) = f^{-1}(x) \in D${{< /katex >}},
applying {{< katex >}}$\psi [\sigma,f]${{< /katex >}} yields {{< katex >}}$f \sigma f^{-1}(x),${{< /katex >}}
and further applying {{< katex >}}$\sigma f \sigma^{-1} f^{-1}${{< /katex >}} yields {{< katex >}}$\sigma(x) = x${{< /katex >}}, since {{< katex >}}$x \notin D${{< /katex >}}.

Finally, if {{< katex >}}$x \notin D \cup f(D)${{< /katex >}},
note that {{< katex >}}$f^{-1}\psi^{-1}(x)${{< /katex >}} is not in {{< katex >}}$D${{< /katex >}},
so we have {{< katex >}}$\psi[\sigma, f]\psi^{-1}(x) = x${{< /katex >}} and in fact the whole product fixes {{< katex >}}$x${{< /katex >}}.
Thus we have shown that {{< katex >}}$g = [\sigma, f]\psi[\sigma,f]\psi^{-1}${{< /katex >}}. {{< katex >}}$\blacksquare${{< /katex >}}

### Simplicity of {{< katex >}}$\operatorname{Homeo}_+(S^2)${{< /katex >}}.

Now, all of {{< katex >}}$\operatorname{Homeo}(S^2)${{< /katex >}} cannot be simple,
since it has an action on the {{< katex >}}$2${{< /katex >}}-element set of orientations of {{< katex >}}$S_2${{< /katex >}}.
On the other hand, let's show that {{< katex >}}$\operatorname{Homeo}_+(S^2)${{< /katex >}} is simple.
To do so, we want to apply the proposition,
for which we need to express any given orientation-preserving homeomorphism {{< katex >}}$h\colon S^2 \to S^2${{< /katex >}}
as being built out of homeomorphisms supported on disks.

Suppose at first that {{< katex >}}$h${{< /katex >}} fixes some (topological) circle on {{< katex >}}$S^2${{< /katex >}}.
Then {{< katex >}}$h${{< /katex >}} is the product of {{< katex >}}$h^+${{< /katex >}} and {{< katex >}}$h^-${{< /katex >}}, 
which are supported in the two hemispheres (thanks Schoenflies!) determined by the circle.
If {{< katex >}}$h${{< /katex >}} does not fix a given circle {{< katex >}}$C${{< /katex >}},
say one disjoint from some fixed point {{< katex >}}$p${{< /katex >}} of {{< katex >}}$h${{< /katex >}},
there is again a homeomorphism {{< katex >}}$h'${{< /katex >}} of {{< katex >}}$S^2${{< /katex >}}
fixing {{< katex >}}$p${{< /katex >}} taking {{< katex >}}$h(C)${{< /katex >}} back to {{< katex >}}$C${{< /katex >}} 
(thanks [Schoenflies](https://en.wikipedia.org/wiki/Schoenflies_problem)!)
so that the composition {{< katex >}}$h'h${{< /katex >}} fixes {{< katex >}}$C${{< /katex >}},
and we can use the argument from above.
It looks like this expresses {{< katex >}}$h${{< /katex >}} as the product of three homeomorphisms supported in disks,
but Nick observed that we can actually combine {{< katex >}}$h'${{< /katex >}} with one of {{< katex >}}$h^+${{< /katex >}} or {{< katex >}}$h^-${{< /katex >}},
so only two are needed.

Anyway, now we have {{< katex >}}$h = h^+h^-${{< /katex >}} where each of {{< katex >}}$h^+${{< /katex >}} and {{< katex >}}$h^-${{< /katex >}} 
are supported in disks {{< katex >}}$D^+${{< /katex >}} and {{< katex >}}$D^-${{< /katex >}}.
If {{< katex >}}$f${{< /katex >}} displaces {{< katex >}}$D^+${{< /katex >}} (i.e. {{< katex >}}$f(D^+) \cap D^+ = \varnothing${{< /katex >}})
and {{< katex >}}$\iota_+^-${{< /katex >}} is an orientation-preserving homeomorphism of {{< katex >}}$S^2${{< /katex >}} taking {{< katex >}}$D^+${{< /katex >}} to {{< katex >}}$D^-${{< /katex >}},
(one exists! I think this is still thanks Schoenflies!)
we have that {{< katex >}}$\iota_+^- f (\iota_+^-)^{-1} (D^-) \cap D^- = \varnothing${{< /katex >}}.
Indeed, if our original {{< katex >}}$f${{< /katex >}} had a {{< katex >}}$\psi${{< /katex >}},
then our new {{< katex >}}$\iota_+^- f (\iota_+^-)^{-1}${{< /katex >}} has one.

It follows from the proposition, assuming we can construct {{< katex >}}$\psi${{< /katex >}},
that {{< katex >}}$h^+${{< /katex >}} and {{< katex >}}$h^-${{< /katex >}} are both products of conjugates of {{< katex >}}$f${{< /katex >}}, so so is {{< katex >}}$h${{< /katex >}}.
But now {{< katex >}}$f${{< /katex >}} itself can be arbitrary so long as it's nontrivial,
for if {{< katex >}}$f(x) \ne x${{< /katex >}}, we can find an open neighborhood small enough that it is moved entirely off itself,
and this open neighborhood contains some disk that {{< katex >}}$f${{< /katex >}} therefore displaces.
Therefore the smallest normal subgroup of {{< katex >}}$\operatorname{Homeo}_+(S^2)${{< /katex >}} containing a nontrivial element
is the whole group—we've shown it is simple.

### Other results

From here it's actually not too hard to show that {{< katex >}}$\operatorname{Homeo}_+(S^2)${{< /katex >}} is coarsely bounded.
Originally I was going to give some argument here,
but I have to turn in an application tomorrow, so I'll sign off and work on that instead.

