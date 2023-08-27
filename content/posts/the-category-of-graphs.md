---
title: "The Category of Graphs"
date: 2019-06-29T10:02:43-04:00
draft: false
math: true
---
You know the sensation where a familiar word becomes suddenly
completely *strange* for no apparent reason? Like suddenly the scales
fall away from your eyes and you see how utterly weird it is that a
concept has a particular name? I've been having that feeling with the
word *graph* as I use it in math.

As a kid, you learn how to *graph* simple functions in the sense of 
being able to sketch them on a sheet of, say, *graph* paper. Millions
of adults probably faintly remember the shape of 
{{< katex >}}$y = x^2${{< /katex >}} but aren't
quite sure why.

To mathematicians and computer scientists, though, for some reason *graph*
means something similar, but different: to them a graph is an object with
*vertices* and *edges*. Indeed, to Serre, that's literally all a graph is:
a quadruple {{< katex >}}$(V,E,\bar{},\iota)${{< /katex >}}. Two sets, {{< katex >}}$V${{< /katex >}} and {{< katex >}}$E${{< /katex >}}, represent the
vertices and (oriented) edges of the graph, and  {{< katex >}}$\bar{}\colon E \to E${{< /katex >}} and
{{< katex >}}$\iota\colon E \to V${{< /katex >}} are functions; {{< katex >}}$\bar{e}${{< /katex >}} is the edge {{< katex >}}$e${{< /katex >}} with its
orientation reversed, (so {{< katex >}}$\bar{\bar{e}} = e${{< /katex >}} for any edge {{< katex >}}$e${{< /katex >}}, but
{{< katex >}}$\bar e \neq e${{< /katex >}}), and
{{< katex >}}$\iota(e)${{< /katex >}} represents the initial vertex of the edge {{< katex >}}$e${{< /katex >}}. This lets us
define a function {{< katex >}}$\tau\colon E \to V${{< /katex >}} picking out the *terminal* vertex
of an edge by setting {{< katex >}}$\tau(e) = \iota(\bar{e})${{< /katex >}}.

A topologist would prefer to say that a graph is a 1-dimensional CW complex.
So rather than an abstract set of vertices, we have a set of points, {{< katex >}}$V${{< /katex >}},
the {{< katex >}}$0${{< /katex >}}-cells of our CW complex. And rather than an abstract set of oriented
edges, we have a collection of {{< katex >}}$1${{< /katex >}}-cells (intervals of the real line) 
whose endpoints are attached to {{< katex >}}$0${{< /katex >}}-cells.

These two descriptions really are in agreement for most purposes. Maybe one would
prefer the more combinatorial description as a way of "rigidifying" some of the
inherent floppiness of topological spaces. At the same time, using topological methods
allows one access to a whole host of techniques that a too-rigid approach might bury
under a sea of formalism.

But of course, neither definition really squares with the idea of the graph of
{{< katex >}}$y = x^2${{< /katex >}}, hence why I've been feeling weird about the word.

Anyway, the *category of graphs*, introduced by John Stallings in
[Topology of Finite Graphs](https://www2.math.ou.edu/~nbrady/teaching/s11-5863/stallings.pdf),
building on work of Serre in [Trees](https://d-nb.info/965816907/04), more about which
almost certainly soon, has (as all categories do)
collections of objects and arrows between them.
Here the objects are graphs and arrows are *morphisms of graphs.* 
A morphism {{< katex >}}$f\colon G \to H${{< /katex >}} between
graphs {{< katex >}}$G${{< /katex >}} and {{< katex >}}$H${{< /katex >}} is a pair of functions {{< katex >}}$f_V\colon V(G) \to V(H)${{< /katex >}} 
and {{< katex >}}$f_E\colon E(G) \to E(H)${{< /katex >}}, such that the following diagrams commute:

{{< katex >}}$$
\begin{CD}
E(G) @>f_E>> E(H) \\
@V{\iota}VV @V{\iota}VV \\
V(G) @>f_V>> V(H)
\end{CD}\qquad
\begin{CD}
E(G) @>f_E>> E(H) \\
@V\bar{}VV @V\bar{}VV \\
E(G) @>f_E>> E(H)
\end{CD}
$${{< /katex >}}

In English what this is saying is that {{< katex >}}$f${{< /katex >}} preserves the graph structure:
it sends edges to edges, vertices to vertices, {{< katex >}}$e${{< /katex >}} and {{< katex >}}$\bar e${{< /katex >}} are sent
to {{< katex >}}$f(e)${{< /katex >}} and {{< katex >}}$\overline{f(e)}${{< /katex >}}, and the initial vertex of {{< katex >}}$e${{< /katex >}} is
sent to the initial vertex of {{< katex >}}$f(e)${{< /katex >}}.

Stallings emphasizes the rigidity of morphisms in this construction:

> By graph and map of graphs, I mean something purely combinatorial or
algebraic. Pictures can be drawn, but one has to understand that maps are
rigid and not just continuous, maps do not collapse edges or wrap edges
around several edges.

And it's true; it's a little challenging to describe precisely which
topological maps between graphs are even homotopic to morphisms without
giving the game (Stallings' paper) away too quickly!


