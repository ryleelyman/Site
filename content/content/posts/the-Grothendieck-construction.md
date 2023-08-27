---
title: "The Grothendieck Construction"
date: 2022-07-06T16:06:06-04:00
math: true
---
I think that right after you learn the Yoneda lemma,
the Grothendieck construction might be one of the most surprisingly useful
techniques in basic category theory.
The purpose of this post is to introduce the Grothendieck construction
and illustrate a situation where it came up for me.

Let {{< katex >}}$\mathsf{C}${{< /katex >}} be a category and {{< katex >}}$F\colon \mathsf{C} \to \mathsf{Cat}${{< /katex >}}
a functor to the category of small categories.
The Grothendieck construction takes this situation
and produces a new category {{< katex >}}$\mathsf{D}${{< /katex >}} equipped with a functor 
{{< katex >}}$\pi\colon \mathsf{D} \to \mathsf{C}${{< /katex >}}.
The category {{< katex >}}$\mathsf{D}${{< /katex >}} is sometimes called the *category of elements* of the functor {{< katex >}}$F${{< /katex >}}.
Now, {{< katex >}}$F${{< /katex >}} is allowed to be either covariant or contravariant,
but I'll concentrate on the covariant case in this post.
If you wish, you may secretly replace {{< katex >}}$\mathsf{Cat}${{< /katex >}} with {{< katex >}}$\mathsf{Set}${{< /katex >}} or {{< katex >}}$\mathsf{Grpoid}${{< /katex >}}.

## The category of elements

Here is the construction of the category {{< katex >}}$\mathsf{D}${{< /katex >}} assuming that {{< katex >}}$F${{< /katex >}} is covariant.
An object of {{< katex >}}$\mathsf{D}${{< /katex >}} is a pair {{< katex >}}$(c,x)${{< /katex >}},
where {{< katex >}}$c \in \mathsf{C}${{< /katex >}} is an object and {{< katex >}}$x \in Fc${{< /katex >}} is an object.
(If {{< katex >}}$\mathsf{Cat}${{< /katex >}} were {{< katex >}}$\mathsf{Set}${{< /katex >}}, we'd have an *element* of the set {{< katex >}}$Fc${{< /katex >}}, hence the name.)
An arrow {{< katex >}}$(c,x) \to (d,y)${{< /katex >}} is a pair {{< katex >}}$(f,\alpha)${{< /katex >}},
where {{< katex >}}$f\colon c \to d${{< /katex >}} is an arrow in {{< katex >}}$\mathsf{C}${{< /katex >}} 
and {{< katex >}}$\alpha\colon Ff(x) \to y${{< /katex >}} is an arrow in the category {{< katex >}}$Fd${{< /katex >}}.
(If {{< katex >}}$\mathsf{Cat}${{< /katex >}} is {{< katex >}}$\mathsf{Set}${{< /katex >}}, the only arrows are of the form {{< katex >}}$(f,1_{Ff(x)})${{< /katex >}}
from {{< katex >}}$(c,x)${{< /katex >}} to {{< katex >}}$(d,Ff(x))${{< /katex >}}.)
If you think about it, the only sensible way to define
the composition of {{< katex >}}$(f,\alpha)\colon (c,x) \to (d,y)${{< /katex >}} with {{< katex >}}$(g,\beta)\colon (d,y) \to (e,z)${{< /katex >}}
is as {{< katex >}}$(gf,\beta \circ Fg(\alpha))${{< /katex >}},
and so we do. 
Checking that composition is associative is cute; I'll let you do it.

The functor {{< katex >}}$\pi\colon \mathsf{D} \to \mathsf{C}${{< /katex >}} is sort of staring at us:
it's defined as {{< katex >}}$\pi(c,x) = c${{< /katex >}} and {{< katex >}}$\pi(f,\alpha) = f${{< /katex >}}.

## Co-fibered categories

The functor {{< katex >}}$\pi\colon \mathsf{D} \to \mathsf{C}${{< /katex >}} is *pre-cofibered*
in the sense that given {{< katex >}}$f\colon c \to d${{< /katex >}} in {{< katex >}}$\mathsf{C}${{< /katex >}}
and any object of the form {{< katex >}}$(c,x)${{< /katex >}},
precomposition with the arrow {{< katex >}}$(f,1_{Ff(x)})${{< /katex >}} provides,
for any {{< katex >}}$(d,y)${{< /katex >}} in {{< katex >}}$\mathsf{D}${{< /katex >}},
an isomorphism

{{< katex >}}$\{(1_d,\alpha) \colon (d,Ff(x)) \to (d,y)\} \cong \{(f,\beta) \colon (x,c) \to (d,y)\}.${{< /katex >}}

The arrows of the form {{< katex >}}$(f,1_x)${{< /katex >}} are called *co-cartesian*
and because the composition of co-cartesian arrows is co-cartesian,
we say that {{< katex >}}$\pi\colon \mathsf{D} \to \mathsf{C}${{< /katex >}} is *cofibered.*

The usefulness of this formulation is the following
corollary to Quillen's Theorem A:

 > **Corollary.** Suppose that {{< katex >}}$\pi\colon \mathsf{D} \to \mathsf{C}${{< /katex >}}
 is pre-cofibered (or the dual notion, *pre-fibered*)
 and that for each {{< katex >}}$c \in \mathsf{C}${{< /katex >}},
 the category {{< katex >}}$\pi^{-1}(c)${{< /katex >}} comprising those objects {{< katex >}}$d \in \mathsf{D}${{< /katex >}}
 satisfying {{< katex >}}$\pi(d) = c${{< /katex >}} and those arrows {{< katex >}}$\alpha${{< /katex >}} satisfying {{< katex >}}$\pi(\alpha) = 1_c${{< /katex >}}
 has a contractible geometric realization.
 Then the resulting map of geometric realizations {{< katex >}}$|\pi|\colon |\mathsf{D}| \to |\mathsf{C}|${{< /katex >}}
 is a homotopy equivalence.

Here's how this came up for me:
I have managed to be very coy about talking about Outer Space so far
and unfortunately I will continue to be coy here and now.
The *spine of Outer Space* is the geometric realization of a certain category,
whose objects are in one formulation (equivalence classes) of trees
equipped with the action of a group (classically the free group of rank {{< katex >}}$n${{< /katex >}})
satisfying certain conditions.
Arrows of the category are collapse maps.
If we think of the barycentric subdivision of each tree as a geometric realization of a category,
then each collapse map is a *functor* of the associated categories.

Carefully (or not, the equivalence relation is such that the "category of choices"
is a contractible groupoid)
choosing a tree in each equivalence class defines, then,
a *functor* from Outer Space to {{< katex >}}$\mathsf{Cat}${{< /katex >}}.
If you perform the Grothendieck construction on this situation,
you get *the spine of l'Autre Espace* (French: "the other space"),
a space that the full *automorphism* group of a free group acts on nicely.
Anyway, contractibility of the spine of l'Autre Espace 
thus follows from the fact that trees are contractible,
the spine of Outer Space is contractible, and the corollary to Quillen's Theorem A.
