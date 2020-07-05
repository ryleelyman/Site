---
layout: post
math: true
---
I wrote [some notes][Notes] introducing orbifolds from Haefliger's perspective in *Metric Spaces of Non-positive Curvature*.
There is some surprisingly heavy machinery that goes into it.
In this blog post I want to talk a little about it at a high level.

An *orbifold* of dimension $$n$$ is a Hausdorff space locally modeled on $$\mathbb{R}^n$$ modulo
the action of a finite group.
This is a simple enough idea on its face:
a useful perspective on the fundamental group of a manifold 
is the passage between its action on the universal cover
and the calculus of loops in the base space.
For a group $$G$$ that acts merely properly discontinuously and not freely,
the quotient space is no longer a manifold,
and yet we would like to accesss the "loops" perspective regardless.
This is the idea that orbifolds are trying to capture.
It is maybe surprising both how successful this project is,
and yet how much more complex the theory becomes.

Let's remember back to when we learned Calculus.
First we learned how to manipulate real-valued functions of one variable,
and later multivariable functions $$f\colon \mathbb{R}^m \to \mathbb{R}^n$$.
In particular, we defined a notion of differentiability for these maps.
To replicate this effort on differentiable manifolds,
one uses *charts.* The idea is that the local structure of a manifold $$M$$
can be captured by a map $$\varphi\colon U \to M$$, where $$U$$ is an
open subset of $$\mathbb{R}^n$$.
A map of manifolds $$f\colon M \to N$$ is *defined* to be differentiable
if its expression in any pair of charts is differentiable.

A ridiculously maximalist approach to this idea is the following:
suppose $$(U_i,\varphi_i)_{i\in I}$$ is an *atlas* for $$M$$
(in the usual sense), and that $$(V_j,\psi_j)_{j\in J}$$
is an atlas for $$N$$.
A function $$f\colon M \to N$$
defines a map $$f_{ij}\colon U_i \to V_j$$
whenever $$f\varphi_i(U_i) \subset \psi_j(V_j)$$.
By refining the open cover of $$M$$, we can assume this is always the case.
We can do the following strange thing:
the disjoint union $$U = \coprod_{i\in I}U_i$$
is a differentiable manifold, each of whose components is an open subset of $$\mathbb{R}^m$$,
and the resulting map $$\varphi = \coprod_{i\in I}\varphi_i$$ is differentiable
(in fact a local diffeomorphism).
The maps $$f_{ij}$$ assemble into a map $$F\colon U \to V$$ such that the following diagram commutes

$$\require{AMScd}\begin{CD} U @>F>> V \\ @VV\varphi V @VV\psi V \\ M @>f>> N. \end{CD}$$

And we are justified in saying that $$f$$ is differentiable when there exists
a map $$F$$ constructed as above.
What we have done, essentially, is said that we don't understand the quotient manifold,
but we *do* understand open subsets of $$\mathbb{R}^m$$, and have performed
a non-unique but useful construction to exploit that understanding.
This is the jumping-off point for orbifolds.

There is just one more wrinkle: 
the definition of an atlas includes various differentiable maps
called *changes of charts.* It would be convenient if there
were a way to stipulate that our map $$F$$ must play nicely with these changes of charts
beyond just saying that there exists a map on the quotient space.
This is where Lie Groupoids come in: they turn out to be precisely the gadget we need
to manage the expression of $$f$$ in charts while asserting that these expressions
play nicely with the changes of charts.
I'll let you read the notes—and Haefliger too, hopefully.
Next time I'll try to wrap my head around the fundamental group of an orbifold,
and hopefully thereafter the mapping class group of an orbifold.

[Notes]: {{ "assets/pdfs/OrbifoldNotes1.pdf" | relative_url }}
