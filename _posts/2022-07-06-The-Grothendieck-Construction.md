---
layout: post
math: true
---
I think that right after you learn the Yoneda lemma,
the Grothendieck construction might be one of the most surprisingly useful
techniques in basic category theory.
The purpose of this post is to introduce the Grothendieck construction
and illustrate a situation where it came up for me.

Let $$\mathsf{C}$$ be a category and $$F\colon \mathsf{C} \to \mathsf{Cat}$$
a functor to the category of small categories.
The Grothendieck construction takes this situation
and produces a new category $$\mathsf{D}$$ equipped with a functor 
$$\pi\colon \mathsf{D} \to \mathsf{C}$$.
The category $$\mathsf{D}$$ is sometimes called the *category of elements* of the functor $$F$$.
Now, $$F$$ is allowed to be either covariant or contravariant,
but I'll concentrate on the covariant case in this post.
If you wish, you may secretly replace $$\mathsf{Cat}$$ with $$\mathsf{Set}$$ or $$\mathsf{Grpoid}$$.

## The category of elements

Here is the construction of the category $$\mathsf{D}$$ assuming that $$F$$ is covariant.
An object of $$\mathsf{D}$$ is a pair $$(c,x)$$,
where $$c \in \mathsf{C}$$ is an object and $$x \in Fc$$ is an object.
(If $$\mathsf{Cat}$$ were $$\mathsf{Set}$$, we'd have an *element* of the set $$Fc$$, hence the name.)
An arrow $$(c,x) \to (d,y)$$ is a pair $$(f,\alpha)$$,
where $$f\colon c \to d$$ is an arrow in $$\mathsf{C}$$ 
and $$\alpha\colon Ff(x) \to y$$ is an arrow in the category $$Fd$$.
(If $$\mathsf{Cat}$$ is $$\mathsf{Set}$$, the only arrows are of the form $$(f,1_{Ff(x)})$$
from $$(c,x)$$ to $$(d,Ff(x))$$.)
If you think about it, the only sensible way to define
the composition of $$(f,\alpha)\colon (c,x) \to (d,y)$$ with $$(g,\beta)\colon (d,y) \to (e,z)$$
is as $$(gf,\beta \circ Fg(\alpha))$$,
and so we do. 
Checking that composition is associative is cute; I'll let you do it.

The functor $$\pi\colon \mathsf{D} \to \mathsf{C}$$ is sort of staring at us:
it's defined as $$\pi(c,x) = c$$ and $$\pi(f,\alpha) = f$$.

## Co-fibered categories

The functor $$\pi\colon \mathsf{D} \to \mathsf{C}$$ is *pre-cofibered*
in the sense that given $$f\colon c \to d$$ in $$\mathsf{C}$$
and any object of the form $$(c,x)$$,
precomposition with the arrow $$(f,1_{Ff(x)})$$ provides,
for any $$(d,y)$$ in $$\mathsf{D}$$,
an isomorphism

$$\{(1_d,\alpha) \colon (d,Ff(x)) \to (d,y)\} \cong \{(f,\beta) \colon (x,c) \to (d,y)\}.$$

The arrows of the form $$(f,1_x)$$ are called *co-cartesian*
and because the composition of co-cartesian arrows is co-cartesian,
we say that $$\pi\colon \mathsf{D} \to \mathsf{C}$$ is *cofibered.*

The usefulness of this formulation is the following
corollary to Quillen's Theorem A:

 > **Corollary.** Suppose that $$\pi\colon \mathsf{D} \to \mathsf{C}$$
 is pre-cofibered (or the dual notion, *pre-fibered*)
 and that for each $$c \in \mathsf{C}$$,
 the category $$\pi^{-1}(c)$$ comprising those objects $$d \in \mathsf{D}$$
 satisfying $$\pi(d) = c$$ and those arrows $$\alpha$$ satisfying $$\pi(\alpha) = 1_c$$
 has a contractible geometric realization.
 Then the resulting map of geometric realizations $$|\pi|\colon |\mathsf{D}| \to |\mathsf{C}|$$
 is a homotopy equivalence.

Here's how this came up for me:
I have managed to be very coy about talking about Outer Space so far
and unfortunately I will continue to be coy here and now.
The *spine of Outer Space* is the geometric realization of a certain category,
whose objects are in one formulation (equivalence classes) of trees
equipped with the action of a group (classically the free group of rank $$n$$)
satisfying certain conditions.
Arrows of the category are collapse maps.
If we think of the barycentric subdivision of each tree as a geometric realization of a category,
then each collapse map is a *functor* of the associated categories.

Carefully (or not, the equivalence relation is such that the "category of choices"
is a contractible groupoid)
choosing a tree in each equivalence class defines, then,
a *functor* from Outer Space to $$\mathsf{Cat}$$.
If you perform the Grothendieck construction on this situation,
you get *the spine of l'Autre Espace* (French: "the other space"),
a space that the full *automorphism* group of a free group acts on nicely.
Anyway, contractibility of the spine of l'Autre Espace 
thus follows from the fact that trees are contractible,
the spine of Outer Space is contractible, and the corollary to Quillen's Theorem A.
