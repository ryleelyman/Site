---
title: "Gromov Hyperbolicity for Arbitrary Metric Spaces"
date: 2021-07-01T14:52:25-04:00
math: true
---
Gromov's original definition of Gromov hyperbolicity makes sense for arbitrary metric spaces.
However, it is only a quasi-isometry invariant for geodesic metric spaces.
I learned this from a
[paper of Väisälä](https://www.sciencedirect.com/science/article/pii/S0723086905000113?via%3Dihub).
The purpose of this post is to understand the counterexample he gives.
I also define Gromov hyperbolicity and quasi-isometry in this post,
which might make it useful for future reference.
The reader already familiar with Gromov hyperbolicity and quasi-isometries
might wish to skip ahead to the heading below.

Let {{< katex >}}$(X,d)${{< /katex >}} be a metric space.
We say that {{< katex >}}$X${{< /katex >}} is a *length space* if the distance between any two points {{< katex >}}$x${{< /katex >}} and {{< katex >}}$y${{< /katex >}} in {{< katex >}}$X${{< /katex >}}
is equal to the infimum of the length of a path joining them.
A *geodesic* in {{< katex >}}$X${{< /katex >}} is a path {{< katex >}}$\gamma\colon [a,b] \to X${{< /katex >}} from a closed interval {{< katex >}}$[a,b] \subset \mathbb{R}${{< /katex >}}
such that {{< katex >}}$d(\gamma(s),\gamma(t)) = |s-t|${{< /katex >}} for all {{< katex >}}$s${{< /katex >}} and {{< katex >}}$t${{< /katex >}} in the interval {{< katex >}}$[a,b]${{< /katex >}}.
We say that {{< katex >}}$X${{< /katex >}} is a *geodesic* metric space if any two points can be joined by a geodesic.
Geodesic metric spaces are length spaces but not necessarily conversely.

Gromov's original definition of hyperbolicity of {{< katex >}}$X${{< /katex >}} is the following.
Given points {{< katex >}}$x${{< /katex >}}, {{< katex >}}$y${{< /katex >}} and {{< katex >}}$z${{< /katex >}} in {{< katex >}}$X${{< /katex >}}, define the *Gromov product*
of {{< katex >}}$x${{< /katex >}} and {{< katex >}}$y${{< /katex >}} with respect to {{< katex >}}$z${{< /katex >}} to be the quantity

{{< katex >}}$(x,y)_z = \frac{1}{2}\left(d(x,z) + d(y,z) - d(x,y)\right).${{< /katex >}}

Then we say that {{< katex >}}$X${{< /katex >}} is *{{< katex >}}$\delta${{< /katex >}}-hyperbolic* if there exists some {{< katex >}}$\delta \ge 0${{< /katex >}}
with the property that for any four points {{< katex >}}$x${{< /katex >}}, {{< katex >}}$y${{< /katex >}}, {{< katex >}}$z${{< /katex >}} and {{< katex >}}$w${{< /katex >}} in {{< katex >}}$X${{< /katex >}},
we have

{{< katex >}}$(x,z)_w \ge \min\{(x,y)_w,(y,z)_w\} - \delta.${{< /katex >}}

Let's try and make sense of this.
The intuition for the Gromov product is the following.
A *tripod* is a metric tree with four vertices, three of which are leaves and one of which has valence three.
Given any triple of points {{< katex >}}$x${{< /katex >}}, {{< katex >}}$y${{< /katex >}} and {{< katex >}}$z${{< /katex >}} in a metric space,
you should convince yourself that we can always construct a tripod
with leaves {{< katex >}}$\hat x${{< /katex >}}, {{< katex >}}$\hat y${{< /katex >}} and {{< katex >}}$\hat z${{< /katex >}} such that we have

{{< katex >}}$d(x,y) = d(\hat x,\hat y),\quad d(x,z) = d(\hat x,\hat z),\quad\text{and}\quad d(y,z) = d(\hat y,\hat z).${{< /katex >}}

In this situation, the Gromov product {{< katex >}}$(x,y)_z${{< /katex >}}
is equal to the distance from {{< katex >}}$\hat z${{< /katex >}} to the center vertex of the tripod.
To make sense of the hyperbolicity condition,
let's continue to think about trees,
only in this case assume that {{< katex >}}$X${{< /katex >}} itself is a metric tree.
Then in this case it's not too hard to argue that the hyperbolicity condition holds with {{< katex >}}$\delta = 0${{< /katex >}};
a picture illustrating the general case is below.
Thus one way to think of {{< katex >}}$\delta${{< /katex >}}-hyperbolicity is to think that from the point of view of any point {{< katex >}}$w \in X${{< /katex >}},
triangles in {{< katex >}}$X${{< /katex >}} look like triangles in trees, up to an error of {{< katex >}}$\delta${{< /katex >}}.

![Trees are {{< katex >}}$0${{< /katex >}}-hyperbolic](/img/GromovProduct.jpeg)

If {{< katex >}}$X${{< /katex >}} is a geodesic metric space, there are other conditions equivalent to this one
that are more directly about the geometry of, e.g. triangles in {{< katex >}}$X${{< /katex >}}.
I've been collecting as many of these conditions as the community will give me
in a [MathOverflow post](https://mathoverflow.net/q/396359/135175).
Eventually I expect to make a blog post or several about the various definitions.

Given metric spaces {{< katex >}}$(X,d_X)${{< /katex >}} and {{< katex >}}$(Y,d_Y)${{< /katex >}} and constants {{< katex >}}$K \ge 1${{< /katex >}} and {{< katex >}}$C \ge 0${{< /katex >}},
a *{{< katex >}}$(K,C)${{< /katex >}}-quasi-isometric embedding* is a function {{< katex >}}$f\colon X \to Y${{< /katex >}}
(it need not be continuous)
such that for all points {{< katex >}}$x${{< /katex >}} and {{< katex >}}$y${{< /katex >}} in {{< katex >}}$X${{< /katex >}}, the following inequality holds

{{< katex >}}$ \frac 1Kd_X(x,y) - C \le d_Y(f(x),f(y)) \le Kd_X(x,y) + C. ${{< /katex >}}

So we see that {{< katex >}}$f${{< /katex >}} is allowed to distort distances by a bounded multiplicative and additive amount.
A *{{< katex >}}$(K,C)${{< /katex >}}-quasi-isometry* is a {{< katex >}}$(K,C)${{< /katex >}}-quasi-isometric embedding with the additional property that
for every point {{< katex >}}$y \in Y${{< /katex >}} there is a point {{< katex >}}$x \in X${{< /katex >}} such that {{< katex >}}$d_Y(y,f(x)) \le C${{< /katex >}}.

## The theorem and the counterexample

Väisälä proves the following theorem.
> **Theorem** Let {{< katex >}}$X${{< /katex >}} and {{< katex >}}$Y${{< /katex >}} be length spaces and {{< katex >}}$f\colon X \to Y${{< /katex >}} a quasi-isometric embedding.
> If {{< katex >}}$Y${{< /katex >}} is {{< katex >}}$\delta${{< /katex >}}-hyperbolic, then {{< katex >}}$X${{< /katex >}} is {{< katex >}}$\delta'${{< /katex >}}-hyperbolic
> for some {{< katex >}}$\delta'${{< /katex >}} depending only on {{< katex >}}$\delta${{< /katex >}} and the quasi-isometry constants for {{< katex >}}$f${{< /katex >}}.

He then observes that the theorem is not true if one does not assume that {{< katex >}}$X${{< /katex >}} is a length space.
Here is the counterexample.
The hyperbolic space {{< katex >}}$Y${{< /katex >}} is the real line {{< katex >}}$\mathbb{R}${{< /katex >}} with the standard metric.
(Recall that {{< katex >}}$\mathbb{R}${{< /katex >}} is a real tree, and thus {{< katex >}}$0${{< /katex >}}-hyperbolic.)
The space {{< katex >}}$X${{< /katex >}} is the graph of the absolute value function {{< katex >}}$\{(x,y) \in \mathbb{R}^2 : y = |x| \}${{< /katex >}}
with the Euclidean metric.
The claim is that the map {{< katex >}}$f\colon X \to Y${{< /katex >}} defined as {{< katex >}}$f(x,y) = x${{< /katex >}} is a quasi-isometric embedding,
but that {{< katex >}}$X${{< /katex >}} is not hyperbolic.

First we show that {{< katex >}}$f${{< /katex >}} is a quasi-isometric embedding.
Indeed, it is clear that given {{< katex >}}$\vec x${{< /katex >}} and {{< katex >}}$\vec y${{< /katex >}} in {{< katex >}}$X${{< /katex >}},
we have {{< katex >}}$d_Y(f(\vec x),f(\vec y)) \le d_X(\vec x,\vec y)${{< /katex >}}.
On the other hand, note that {{< katex >}}$d_X(\vec x,\vec y)${{< /katex >}} is furthest from {{< katex >}}$d_Y(f(\vec x),f(\vec y))${{< /katex >}}
when {{< katex >}}$\vec x${{< /katex >}} and {{< katex >}}$\vec y${{< /katex >}} are in the same quadrant, where we have
{{< katex >}}$d_X(\vec x,\vec y) = \sqrt{2}d_Y(f(\vec x),f(\vec y))${{< /katex >}}.
Thus the map {{< katex >}}$f${{< /katex >}} is a {{< katex >}}$(\sqrt 2,0)${{< /katex >}}-quasi-isometric embedding, in fact a {{< katex >}}$(\sqrt 2,0)${{< /katex >}}-quasi-isometry.

Finally we show that {{< katex >}}$X${{< /katex >}} is not hyperbolic.
Consider the four points {{< katex >}}$x = (0,0)${{< /katex >}}, {{< katex >}}$y = (-2t,2t)${{< /katex >}}, {{< katex >}}$z = (2t,2t)${{< /katex >}} and {{< katex >}}$w = (t,t)${{< /katex >}}.
Then we have

{{< katex >}}$ (x,z)_w = \frac 12\left(\sqrt 2t + \sqrt 2t - 2\sqrt 2t\right) = 0,${{< /katex >}}

{{< katex >}}$ (x,y)_w = \frac 12\left(\sqrt 2t + 2\sqrt 5t - 2\sqrt 2t\right) \approx 1.53t${{< /katex >}}

{{< katex >}}$ (y,z)_w = \frac 12\left(2\sqrt 5t + \sqrt 2t - 4t\right) \approx 0.94t${{< /katex >}}

But observe that as {{< katex >}}$t \to \infty${{< /katex >}}, we have that {{< katex >}}$(x,y)_w${{< /katex >}} and {{< katex >}}$(y,z)_w${{< /katex >}} tend to {{< katex >}}$\infty${{< /katex >}},
so no uniform choice of {{< katex >}}$\delta${{< /katex >}} makes the inequality
{{< katex >}}$(x,z)_w \ge \min\{(x,y)_w,(y,z)_w\} - \delta${{< /katex >}} hold.
The problem, roughly, is that the quasi-isometry condition cannot see the "kink" in the space {{< katex >}}$X${{< /katex >}},
while the {{< katex >}}$\delta${{< /katex >}}-hyperbolicity condition, at least for this family of triangles, can.
