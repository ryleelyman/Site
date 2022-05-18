---
layout: post
math: true
---
In the previous two posts we met stacks for the first time.
We'd like to know what a *geometric* or *Artin* stack over $$\mathbf{Top}$$ is,
since these are the stacks that correspond to, e.g. graphs of groups.
To get there, I'm told, Yoneda lemma (sorry sorry).

If you're trying to follow who I'm following,
we're back to [Lerman],
for no particular reason other than I find it helpful to bounce.

## The 2-Yoneda lemma

The 2-Yoneda lemma works for categories fibered in groupoids over any category,
but to keep things hopefully slightly clearer I will continue to speak of our base category
as $$\mathbf{Top}$$.
Given a space $$X$$, there is a category fibered in groupoids over $$\mathbf{Top}$$,
namely the *slice category* $$\mathbf{Top}/X = \underline{X}$$.
The objects of $$\underline{X}$$ are maps with codomain $$X$$
and arrows are maps of the domains making the diagram below commute

$$\require{AMScd}\begin{CD}
Y @>f>> Z \\
@VVV @VVV \\
X @= X
\end{CD}$$

where the vertical maps are the defining maps of the objects.
The projection $$\underline{X} \to \mathbf{Top}$$ sends an object, which is a map $$Y \to X$$
to its domain $$Y$$,
and sends an arrow to the corresponding map of domains.
Notationally, this category is very frustrating to work with,
since both objects and arrows are maps, and we'll want to use a single map as both.
Lerman solves this problem with the power of TikZ, which we don't have here in blog land.
I will attempt to solve this by referring to objects of $$\underline{X}$$
by their domain when I can,
and saving the maps for referring to arrows.
Thus, for example, if $$F$$ is a functor with domain $$\underline{X}$$,
after specifying that I am considering $$f\colon Y \to X$$,
I will write $$F(Y)$$ the image of $$f\colon Y \to X$$ under $$F$$,
and write $$F(f)$$ for the image of the arrow that is secretly the following diagram

$$\begin{CD}
Y @>f>> X \\
@VfVV @V1_XVV \\
X @= X.
\end{CD}$$

You see? Clear as mud.

The Pasting Lemma from general topology, essentially,
tells us that $$\underline{X}$$ is actually a stack.
(Given a map to $$X$$ defined on an open cover of a space $$Y$$
with isomorphisms between double intersections 
satisfying the cocycle condition on triple intersections,
there is certainly a map $$Y \to X$$, so every descent datum is effective.
What's more, an isomorphism over $$X$$ between $$Y$$ and $$Y'$$ is definitely
determined by its restriction to an open cover, so isomorphisms form a sheaf.)
We don't need that at the moment, but it will be useful later.

Recall that natural transformations (necessarily isomorphisms)
between maps (functors) of categories fibered in groupoids
make the collection (ack, is it a set??)
of maps $$F\colon \mathsf{C} \to \mathsf{D}$$ into a category (necessarily a groupoid)
called $$\operatorname{Hom}(\mathsf{C},\mathsf{D})$$.
Similarly, given a category fibered in groupoids $$\mathsf{D}$$
and a space $$X$$, there is a category $$\mathsf{D}(X)$$
comprising all those objects $$\xi \in \mathsf{D}$$ with $$\pi(\xi) = X$$,
where arrows are arrows $$f\colon \xi \to \xi'$$ in $$\mathsf{D}$$
with the property that $$\pi(f) = 1_X$$.
Ahh, this latter category is probably not small in general,
but maybe there are standard(?) tricks you can do to show it is equivalent to a small category.

Anyway:

 > **Theorem.** (The 2-Yoneda Lemma)
 The functor 
 $$\operatorname{よ}\colon \operatorname{Hom}(\underline{X},\mathsf{D}) \to \mathsf{D}(X)$$
 defined on objects (functors) as 
 $$(F\colon \underline{X} \to \mathsf{D}) \mapsto F(1_X\colon X \to X)$$
 and on arrows (natural transformations) as
 $$(\alpha\colon F \Rightarrow G) \mapsto (\alpha(1_X)\colon F(1_X) \to G(1_X))$$
 is an equivalence of categories.

In more words, the functor $$\operatorname{よ}$$ sends a functor $$F$$ to its
action on the map $$1_X \colon X \to X$$ in $$\underline{X}$$
and sends a natural transformation $$\alpha$$ between functors $$F$$ and $$G$$
to its action on the map $$1_X \colon X \to X$$,
which happens to be (by the definition of a natural transformation)
an arrow from $$F(1_X)$$ to $$G(1_X)$$.

*Proof.*   
First notice that $$\operatorname{よ}(F)$$ is definitely an object over $$X$$,
since maps of categories fibered in groupoids preserve the projection to $$\mathbf{Top}$$.
Similarly, since natural transformations are over the identity of $$\mathbf{Top}$$,
$$\operatorname{よ}(\alpha)$$ is definitely over $$1_X$$.
Therefore the map is well-defined.

Next observe that
$$\operatorname{よ}(1_F \colon F \Rightarrow F) = 1_F(1_X) \colon F(1_X) \to F(1_X)$$
is in fact the identity arrow of $$1_X \colon X \to X$$.

Now suppose that we have $$\alpha\colon F \Rightarrow G$$ and $$\beta\colon G \Rightarrow H$$.
We have

$$\operatorname{よ}(\beta\alpha) = (\beta\alpha)(1_X) 
= \beta(1_X)\alpha(1_X) = \operatorname{よ}(\beta)\operatorname{よ}(\alpha)$$

so $$\operatorname{よ}$$ is indeed a functor.

To show that $$\operatorname{よ}$$ is an equivalence of categories we will show that
it is full, faithful and essentially surjective.
Suppose $$F$$ and $$G$$ are functors $$\underline{X} \to \mathsf{D}$$.
Write $$X$$ for the object $$1_X \colon X \to X$$ in $$\underline{X}$$, and
write $$F(X) = \xi$$ and $$G(X) = \xi'$$.
Given a map of spaces $$f\colon Y \to X$$,
there is by the definition of categories fibered in groupoids,
a unique isomorphism $$\sigma_{F,f}\colon F(Y) \to f^*\xi$$ 
with the property that the following diagram commutes

$$\begin{CD}
F(Y) @>F(f)>> \xi \\
@V\sigma_{F,f}VV @| \\
f^*\xi @>f_\xi>> \xi.
\end{CD}$$

There is also the pullback isomorphism $$f^*a\colon f^*\xi \to f^*\xi'$$.
We define the action of our putative natural transformation $$\alpha\colon F \Rightarrow G$$
as $$\alpha(Y) = \sigma_{G,f}^{-1}\circ f^*a\circ\sigma_{F,f}$$.
Given another map $$g\colon Z \to X$$ and an arrow $$h \colon Y \to Z$$ in $$\underline{X}$$,
we trace the naturality square:

$$\begin{CD}
F(Y) @>\sigma_{G,f}^{-1}\circ f^*a\circ\sigma_{F,f}>> G(Y) \\
@VF(h)VV @VG(h)VV \\
F(Z) @>\sigma_{G,g}^{-1}\circ g^*a\circ\sigma_{F,g}>> G(Z).
\end{CD}$$

We claim that both paths around the square fit into the 
unlabeled vertical arrow in the following diagram
to make it commute

$$\begin{CD}
F(Y) @>aF(f)>> \xi' \\
@VVV @| \\
G(Z) @>G(g)>> \xi'.
\end{CD}$$

Indeed, we have

$$\begin{gather*}aF(f) = af_\xi\sigma_{F,f} = f_{\xi'}f^*a\sigma_{F,f} 
= G(f)\sigma_{G,f}^{-1} f^*a \sigma_{F,f} \\
= G(g) \circ G(h) \sigma_{G,f}^{-1} f^*a \sigma_{F,f}.
\end{gather*}$$

But on the other hand, we also have

$$\begin{gather*}
aF(f) = a F(g)F(h) = ag_\xi \sigma_{F,g} F(h) = g_{\xi'} g^*a \sigma_{F,g} F(h) \\
= G(g) \circ \sigma_{G,g}^{-1} g^*a \sigma_{F,g} F(h).
\end{gather*}$$

The argument is summarized in the following rather pretty commutative diagram.

![The argument above summarized in diagram form](/assets/img/cfgdiagram.jpeg)

It follows by properties of categories fibered in groupoids that the naturality square commutes.
This proves that $$\operatorname{よ}$$ is full.
In fact it is faithful as well, since the arrow $$\alpha(Y)$$ 
is uniquely determined by $$Y$$ (really $$f\colon Y \to X$$) and $$a$$.

To complete the proof, we show essential surjectivity.
Suppose $$\xi$$ is an object over $$X$$ in $$\mathsf{D}$$.
We need to show that there is a functor $$F \colon \underline{X} \to \mathsf{D}$$
and an isomorphism $$\xi \to \operatorname{よ}(F) = F(X)$$.
We will do one better:
define $$F(X) = \xi$$ and given a map $$f\colon Y \to X$$, define $$F(Y) = f^*\xi$$.
Given an arrow $$h \colon Y \to Z$$ over $$X$$, (where again we have $$g\colon Z \to X$$)
there is by the definition of a category fibered in groupoids
a unique arrow $$F(h) \colon f^*\xi \to g^*\xi$$
making the following diagram commute

$$\begin{CD}
f^*\xi @>f_\xi>> \xi \\
@VF(h)VV @| \\
g^*\xi @>g_\xi>> \xi
\end{CD}$$

over the map $$h\colon Y \to Z$$.
Functoriality of $$F$$ follows by uniqueness.
Thus $$\xi$$ is *equal* to the image of $$1_X\colon X \to X$$ under some functor,
hence certainly isomorphic to it. $$\blacksquare$$

[Lerman]: https://ems.press/content/serial-article-files/6839
