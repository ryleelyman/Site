---
title: "Pursued by Stacks 3: We Need a Lemma"
date: 2022-05-17T15:44:23-04:00
math: true
---
In the previous two posts we met stacks for the first time.
We'd like to know what a *geometric* or *Artin* stack over {{< katex >}}$\mathbf{Top}${{< /katex >}} is,
since these are the stacks that correspond to, e.g. graphs of groups.
To get there, I'm told, Yoneda lemma (sorry sorry).

If you're trying to follow who I'm following,
we're back to [Lerman],
for no particular reason other than I find it helpful to bounce.

## The 2-Yoneda lemma

The 2-Yoneda lemma works for categories fibered in groupoids over any category,
but to keep things hopefully slightly clearer I will continue to speak of our base category
as {{< katex >}}$\mathbf{Top}${{< /katex >}}.
Given a space {{< katex >}}$X${{< /katex >}}, there is a category fibered in groupoids over {{< katex >}}$\mathbf{Top}${{< /katex >}},
namely the *slice category* {{< katex >}}$\mathbf{Top}/X = \underline{X}${{< /katex >}}.
The objects of {{< katex >}}$\underline{X}${{< /katex >}} are maps with codomain {{< katex >}}$X${{< /katex >}}
and arrows are maps of the domains making the diagram below commute

{{< katex >}}$$\begin{CD}
Y @>f>> Z \\
@VVV @VVV \\
X @= X
\end{CD}$${{< /katex >}}

where the vertical maps are the defining maps of the objects.
The projection {{< katex >}}$\underline{X} \to \mathbf{Top}${{< /katex >}} sends an object, which is a map {{< katex >}}$Y \to X${{< /katex >}}
to its domain {{< katex >}}$Y${{< /katex >}},
and sends an arrow to the corresponding map of domains.
Notationally, this category is very frustrating to work with,
since both objects and arrows are maps, and we'll want to use a single map as both.
Lerman solves this problem with the power of TikZ, which we don't have here in blog land.
I will attempt to solve this by referring to objects of {{< katex >}}$\underline{X}${{< /katex >}}
by their domain when I can,
and saving the maps for referring to arrows.
Thus, for example, if {{< katex >}}$F${{< /katex >}} is a functor with domain {{< katex >}}$\underline{X}${{< /katex >}},
after specifying that I am considering {{< katex >}}$f\colon Y \to X${{< /katex >}},
I will write {{< katex >}}$F(Y)${{< /katex >}} the image of {{< katex >}}$f\colon Y \to X${{< /katex >}} under {{< katex >}}$F${{< /katex >}},
and write {{< katex >}}$F(f)${{< /katex >}} for the image of the arrow that is secretly the following diagram

{{< katex >}}$$\begin{CD}
Y @>f>> X \\
@VfVV @V1_XVV \\
X @= X.
\end{CD}$${{< /katex >}}

You see? Clear as mud.

The Pasting Lemma from general topology, essentially,
tells us that {{< katex >}}$\underline{X}${{< /katex >}} is actually a stack.
(Given a map to {{< katex >}}$X${{< /katex >}} defined on an open cover of a space {{< katex >}}$Y${{< /katex >}}
with isomorphisms between double intersections 
satisfying the cocycle condition on triple intersections,
there is certainly a map {{< katex >}}$Y \to X${{< /katex >}}, so every descent datum is effective.
What's more, an isomorphism over {{< katex >}}$X${{< /katex >}} between {{< katex >}}$Y${{< /katex >}} and {{< katex >}}$Y'${{< /katex >}} is definitely
determined by its restriction to an open cover, so isomorphisms form a sheaf.)
We don't need that at the moment, but it will be useful later.

Recall that natural transformations (necessarily isomorphisms)
between maps (functors) of categories fibered in groupoids
make the collection (ack, is it a set??)
of maps {{< katex >}}$F\colon \mathsf{C} \to \mathsf{D}${{< /katex >}} into a category (necessarily a groupoid)
called {{< katex >}}$\operatorname{Hom}(\mathsf{C},\mathsf{D})${{< /katex >}}.
Similarly, given a category fibered in groupoids {{< katex >}}$\mathsf{D}${{< /katex >}}
and a space {{< katex >}}$X${{< /katex >}}, there is a category {{< katex >}}$\mathsf{D}(X)${{< /katex >}}
comprising all those objects {{< katex >}}$\xi \in \mathsf{D}${{< /katex >}} with {{< katex >}}$\pi(\xi) = X${{< /katex >}},
where arrows are arrows {{< katex >}}$f\colon \xi \to \xi'${{< /katex >}} in {{< katex >}}$\mathsf{D}${{< /katex >}}
with the property that {{< katex >}}$\pi(f) = 1_X${{< /katex >}}.
Ahh, this latter category is probably not small in general,
but maybe there are standard(?) tricks you can do to show it is equivalent to a small category.

Anyway:

 > **Theorem.** (The 2-Yoneda Lemma)
 The functor 
 {{< katex >}}$\operatorname{よ}\colon \operatorname{Hom}(\underline{X},\mathsf{D}) \to \mathsf{D}(X)${{< /katex >}}
 defined on objects (functors) as 
 {{< katex >}}$(F\colon \underline{X} \to \mathsf{D}) \mapsto F(1_X\colon X \to X)${{< /katex >}}
 and on arrows (natural transformations) as
 {{< katex >}}$(\alpha\colon F \Rightarrow G) \mapsto (\alpha(1_X)\colon F(1_X) \to G(1_X))${{< /katex >}}
 is an equivalence of categories.

In more words, the functor {{< katex >}}$\operatorname{よ}${{< /katex >}} sends a functor {{< katex >}}$F${{< /katex >}} to its
action on the map {{< katex >}}$1_X \colon X \to X${{< /katex >}} in {{< katex >}}$\underline{X}${{< /katex >}}
and sends a natural transformation {{< katex >}}$\alpha${{< /katex >}} between functors {{< katex >}}$F${{< /katex >}} and {{< katex >}}$G${{< /katex >}}
to its action on the map {{< katex >}}$1_X \colon X \to X${{< /katex >}},
which happens to be (by the definition of a natural transformation)
an arrow from {{< katex >}}$F(1_X)${{< /katex >}} to {{< katex >}}$G(1_X)${{< /katex >}}.

*Proof.*   
First notice that {{< katex >}}$\operatorname{よ}(F)${{< /katex >}} is definitely an object over {{< katex >}}$X${{< /katex >}},
since maps of categories fibered in groupoids preserve the projection to {{< katex >}}$\mathbf{Top}${{< /katex >}}.
Similarly, since natural transformations are over the identity of {{< katex >}}$\mathbf{Top}${{< /katex >}},
{{< katex >}}$\operatorname{よ}(\alpha)${{< /katex >}} is definitely over {{< katex >}}$1_X${{< /katex >}}.
Therefore the map is well-defined.

Next observe that
{{< katex >}}$\operatorname{よ}(1_F \colon F \Rightarrow F) = 1_F(1_X) \colon F(1_X) \to F(1_X)${{< /katex >}}
is in fact the identity arrow of {{< katex >}}$1_X \colon X \to X${{< /katex >}}.

Now suppose that we have {{< katex >}}$\alpha\colon F \Rightarrow G${{< /katex >}} and {{< katex >}}$\beta\colon G \Rightarrow H${{< /katex >}}.
We have

{{< katex >}}$$\operatorname{よ}(\beta\alpha) = (\beta\alpha)(1_X) 
= \beta(1_X)\alpha(1_X) = \operatorname{よ}(\beta)\operatorname{よ}(\alpha)$${{< /katex >}}

so {{< katex >}}$\operatorname{よ}${{< /katex >}} is indeed a functor.

To show that {{< katex >}}$\operatorname{よ}${{< /katex >}} is an equivalence of categories we will show that
it is full, faithful and essentially surjective.
Suppose {{< katex >}}$F${{< /katex >}} and {{< katex >}}$G${{< /katex >}} are functors {{< katex >}}$\underline{X} \to \mathsf{D}${{< /katex >}}.
Write {{< katex >}}$X${{< /katex >}} for the object {{< katex >}}$1_X \colon X \to X${{< /katex >}} in {{< katex >}}$\underline{X}${{< /katex >}}, and
write {{< katex >}}$F(X) = \xi${{< /katex >}} and {{< katex >}}$G(X) = \xi'${{< /katex >}}.
Given a map of spaces {{< katex >}}$f\colon Y \to X${{< /katex >}},
there is by the definition of categories fibered in groupoids,
a unique isomorphism {{< katex >}}$\sigma_{F,f}\colon F(Y) \to f^*\xi${{< /katex >}} 
with the property that the following diagram commutes

{{< katex >}}$$\begin{CD}
F(Y) @>F(f)>> \xi \\
@V\sigma_{F,f}VV @| \\
f^*\xi @>f_\xi>> \xi.
\end{CD}$${{< /katex >}}

There is also the pullback isomorphism {{< katex >}}$f^*a\colon f^*\xi \to f^*\xi'${{< /katex >}}.
We define the action of our putative natural transformation {{< katex >}}$\alpha\colon F \Rightarrow G${{< /katex >}}
as {{< katex >}}$\alpha(Y) = \sigma_{G,f}^{-1}\circ f^*a\circ\sigma_{F,f}${{< /katex >}}.
Given another map {{< katex >}}$g\colon Z \to X${{< /katex >}} and an arrow {{< katex >}}$h \colon Y \to Z${{< /katex >}} in {{< katex >}}$\underline{X}${{< /katex >}},
we trace the naturality square:

{{< katex >}}$$\begin{CD}
F(Y) @>\sigma_{G,f}^{-1}\circ f^*a\circ\sigma_{F,f}>> G(Y) \\
@VF(h)VV @VG(h)VV \\
F(Z) @>\sigma_{G,g}^{-1}\circ g^*a\circ\sigma_{F,g}>> G(Z).
\end{CD}$${{< /katex >}}

We claim that both paths around the square fit into the 
unlabeled vertical arrow in the following diagram
to make it commute

{{< katex >}}$$\begin{CD}
F(Y) @>aF(f)>> \xi' \\
@VVV @| \\
G(Z) @>G(g)>> \xi'.
\end{CD}$${{< /katex >}}

Indeed, we have

{{< katex >}}$$\begin{gather*}aF(f) = af_\xi\sigma_{F,f} = f_{\xi'}f^*a\sigma_{F,f} 
= G(f)\sigma_{G,f}^{-1} f^*a \sigma_{F,f} \\
= G(g) \circ G(h) \sigma_{G,f}^{-1} f^*a \sigma_{F,f}.
\end{gather*}$${{< /katex >}}

But on the other hand, we also have

{{< katex >}}$$\begin{gather*}
aF(f) = a F(g)F(h) = ag_\xi \sigma_{F,g} F(h) = g_{\xi'} g^*a \sigma_{F,g} F(h) \\
= G(g) \circ \sigma_{G,g}^{-1} g^*a \sigma_{F,g} F(h).
\end{gather*}$${{< /katex >}}

The argument is summarized in the following rather pretty commutative diagram.

![The argument above summarized in diagram form](/img/cfgdiagram.jpeg)

It follows by properties of categories fibered in groupoids that the naturality square commutes.
This proves that {{< katex >}}$\operatorname{よ}${{< /katex >}} is full.
In fact it is faithful as well, since the arrow {{< katex >}}$\alpha(Y)${{< /katex >}} 
is uniquely determined by {{< katex >}}$Y${{< /katex >}} (really {{< katex >}}$f\colon Y \to X${{< /katex >}}) and {{< katex >}}$a${{< /katex >}}.

To complete the proof, we show essential surjectivity.
Suppose {{< katex >}}$\xi${{< /katex >}} is an object over {{< katex >}}$X${{< /katex >}} in {{< katex >}}$\mathsf{D}${{< /katex >}}.
We need to show that there is a functor {{< katex >}}$F \colon \underline{X} \to \mathsf{D}${{< /katex >}}
and an isomorphism {{< katex >}}$\xi \to \operatorname{よ}(F) = F(X)${{< /katex >}}.
We will do one better:
define {{< katex >}}$F(X) = \xi${{< /katex >}} and given a map {{< katex >}}$f\colon Y \to X${{< /katex >}}, define {{< katex >}}$F(Y) = f^*\xi${{< /katex >}}.
Given an arrow {{< katex >}}$h \colon Y \to Z${{< /katex >}} over {{< katex >}}$X${{< /katex >}}, (where again we have {{< katex >}}$g\colon Z \to X${{< /katex >}})
there is by the definition of a category fibered in groupoids
a unique arrow {{< katex >}}$F(h) \colon f^*\xi \to g^*\xi${{< /katex >}}
making the following diagram commute

{{< katex >}}$$\begin{CD}
f^*\xi @>f_\xi>> \xi \\
@VF(h)VV @| \\
g^*\xi @>g_\xi>> \xi
\end{CD}$${{< /katex >}}

over the map {{< katex >}}$h\colon Y \to Z${{< /katex >}}.
Functoriality of {{< katex >}}$F${{< /katex >}} follows by uniqueness.
Thus {{< katex >}}$\xi${{< /katex >}} is *equal* to the image of {{< katex >}}$1_X\colon X \to X${{< /katex >}} under some functor,
hence certainly isomorphic to it. {{< katex >}}$\blacksquare${{< /katex >}}

[Lerman]: https://ems.press/content/serial-article-files/6839
