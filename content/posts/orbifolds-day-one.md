---
title: "Orbifolds Day One"
date: 2020-07-05T13:21:27-04:00
math: true
---
I wrote [some notes][Notes] introducing orbifolds from Haefliger's perspective in *Metric Spaces of Non-positive Curvature*.
There is some surprisingly heavy machinery that goes into it.
In this blog post I want to talk a little about it at a high level.

An *orbifold* of dimension {{< katex >}}$n${{< /katex >}} is a Hausdorff space locally modeled on {{< katex >}}$\mathbb{R}^n${{< /katex >}} modulo
the action of a finite group.
This is a simple enough idea on its face:
a useful perspective on the fundamental group of a manifold 
is the passage between its action on the universal cover
and the calculus of loops in the base space.
For a group {{< katex >}}$G${{< /katex >}} that acts merely properly discontinuously and not freely,
the quotient space is no longer a manifold,
and yet we would like to accesss the "loops" perspective regardless.
This is the idea that orbifolds are trying to capture.
It is maybe surprising both how successful this project is,
and yet how much more complex the theory becomes.

Let's remember back to when we learned Calculus.
First we learned how to manipulate real-valued functions of one variable,
and later multivariable functions {{< katex >}}$f\colon \mathbb{R}^m \to \mathbb{R}^n${{< /katex >}}.
In particular, we defined a notion of differentiability for these maps.
To replicate this effort on differentiable manifolds,
one uses *charts.* The idea is that the local structure of a manifold {{< katex >}}$M${{< /katex >}}
can be captured by a map {{< katex >}}$\varphi\colon U \to M${{< /katex >}}, where {{< katex >}}$U${{< /katex >}} is an
open subset of {{< katex >}}$\mathbb{R}^n${{< /katex >}}.
A map of manifolds {{< katex >}}$f\colon M \to N${{< /katex >}} is *defined* to be differentiable
if its expression in any pair of charts is differentiable.

A ridiculously maximalist approach to this idea is the following:
suppose {{< katex >}}$(U_i,\varphi_i)_{i\in I}${{< /katex >}} is an *atlas* for {{< katex >}}$M${{< /katex >}}
(in the usual sense), and that {{< katex >}}$(V_j,\psi_j)_{j\in J}${{< /katex >}}
is an atlas for {{< katex >}}$N${{< /katex >}}.
A function {{< katex >}}$f\colon M \to N${{< /katex >}}
defines a map {{< katex >}}$f_{ij}\colon U_i \to V_j${{< /katex >}}
whenever {{< katex >}}$f\varphi_i(U_i) \subset \psi_j(V_j)${{< /katex >}}.
By refining the open cover of {{< katex >}}$M${{< /katex >}}, we can assume this is always the case.
We can do the following strange thing:
the disjoint union {{< katex >}}$U = \coprod_{i\in I}U_i${{< /katex >}}
is a differentiable manifold, each of whose components is an open subset of {{< katex >}}$\mathbb{R}^m${{< /katex >}},
and the resulting map {{< katex >}}$\varphi = \coprod_{i\in I}\varphi_i${{< /katex >}} is differentiable
(in fact a local diffeomorphism).
The maps {{< katex >}}$f_{ij}${{< /katex >}} assemble into a map {{< katex >}}$F\colon U \to V${{< /katex >}} such that the following diagram commutes

{{< katex >}}$$\begin{CD} U @>F>> V \\ @VV\varphi V @VV\psi V \\ M @>f>> N. \end{CD}$${{< /katex >}}

And we are justified in saying that {{< katex >}}$f${{< /katex >}} is differentiable when there exists
a map {{< katex >}}$F${{< /katex >}} constructed as above.
What we have done, essentially, is said that we don't understand the quotient manifold,
but we *do* understand open subsets of {{< katex >}}$\mathbb{R}^m${{< /katex >}}, and have performed
a non-unique but useful construction to exploit that understanding.
This is the jumping-off point for orbifolds.

There is just one more wrinkle: 
the definition of an atlas includes various differentiable maps
called *changes of charts.* It would be convenient if there
were a way to stipulate that our map {{< katex >}}$F${{< /katex >}} must play nicely with these changes of charts
beyond just saying that there exists a map on the quotient space.
This is where Lie Groupoids come in: they turn out to be precisely the gadget we need
to manage the expression of {{< katex >}}$f${{< /katex >}} in charts while asserting that these expressions
play nicely with the changes of charts.
I'll let you read the notes—and Haefliger too, hopefully.
Next time I'll try to wrap my head around the fundamental group of an orbifold,
and hopefully thereafter the mapping class group of an orbifold.

[Notes]: /pdfs/OrbifoldNotes1.pdf


