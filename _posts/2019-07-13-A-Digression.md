---
math: true
---
I'm not sure what this post set out to be. It ended up a digression
on set theory vs. category theory.

In modern mathematics, there are two notions that might be truly called 
foundational to all the work we do. These are *set theory* and *category theory.*
Both theories are living, evolving things with their specialists, constructions
and interesting problems, just like any other field of math, 
but the core ideas are familiar and useful to nearly every mathematician.

A *set,* naively, is just a way to collect a bunch of objects (called *elements*)
together. Since a set only cares about membership or lack thereof, duplicate
elements are ignored. When we're explicit about them, a set is typically
denoted as a list of elements (thought of as unordered), surrounded by curly braces.
So as sets, $$\{1,2,3,3,5\} = \{1,2,3\}$$. A set comprises its elements, nothing more,
nothing less. Thus, maps or functions $$f$$ between sets $$X$$ and $$Y$$ are just
assignments: to each element $$x$$ in $$X$, we assign a (unique) element $$f(x)$$
of $$Y$$. 

Things, mathematical objects, whatever you can pin down in language,
may be elements (or not) of sets. Sets may even be elements of other sets, although
here is a source of worry. Bertrand Russell observed in 1901 that allowing this
kind of willy-nilly calling things sets yields the mathematical equivalent of the
following silly story: In a small village there is one barber. He shaves the
beards of only those men who does not shave themselves. Who shaves the barber?

The question, of course, has no good answer. If the barber shaves himself, then
he cannot, but then he must. The mathematical response to Russell's realization
was to retrench a bit, but it also paved the way for set theory to become an 
interesting field of research in its own right.

Set theory, thanks to work of Kurt Goedel and many others, has raised thorny,
even unsolvable, problems that mathematicians working in other fields would often
prefer to gloss over. One example is the following: If you have in front of you
a finite collection of sets, maybe think of them as baskets in the produce section,
you can obviously choose an element from each basket. This process is sometimes
called a *choice function.* If you imagine an infinitely long aisle at the grocery
store with baskets evenly spaced along it, you might agree that you can still
choose one element from each basket. Even though you won't live to see it
through, it's easy to describe a way to decide how to choose the next element;
each basket is eventually reached by you, even though you will never reach 
every basket. This kind of infinity is *countably infinite,* like the numbers
we use for counting. But there are more kinds of infinity, and in those cases
it's maybe not immediately clear that we should still be able to take an object from
each basket. The hypothesis that we *can* is called the *Axiom of Choice,* and it
turns out to be "independent" of the rest of the rules of set theory we commonly employ.
That is, the rest of set theory *can remain true* whatever position we wish to take on
the axiom of choice.

Category theory, (already touched on implicitly in [The Category of Graphs]) has
a somewhat similar history, although it arose later. Introduced by Samuel Eilenberg
and Saunders Mac Lane in their study of algebraic topology, it has since become
a central perspective in many areas of mathematics and also grown into a field
of interest in its own right. A category is a collection of objects and arrows.
Note that I did not say a *set.* This distinction is important theoretically
but in practice categorical and set-theoretic reasoning are typically 
sufficiently different that this can be ignored. In category theory,
the sets themselves comprise a category, typically called **Set** with
objects sets and arrows functions between sets. This metaphor motivates
the definition: arrows have a *domain* and *codomain,* just as functions
between sets do. Arrows, like functions, may be *composed* (i.e.
"first add four, and then multiply by sixteen"), and the composition is
associative, but need not be commutative.

This general picture allows one to talk about several different, yet related,
situations together at once. Many common constructions in mathematics, including
"sum" and "product" may be phrased as a certain kind of "universal" construction
in the language of category theory. One such construction, the *free object,*
is particularly interesting within group theory. Originally I had meant to talk
about it in this post, but perhaps the next one.

[The Category of Graphs]: {% post_url 2019-06-29-The-Category-of-Graphs %}
