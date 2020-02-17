---
layout: post
math: true
---
My office-mate asked me to give a "second lecture" in category theory
in [Eminar][eminar], the Tufts graduate student seminar. I gave a first lecture
last semester, but I thought it might be nice to have something to point people
who missed it to, in order to stick to my assignment
and begin at the Yoneda lemma. So, here is yet another rendition of the first
hour of a category theory class.

The treatment is brisk. To the interested reader,
I would highly recommend Emily Riehl's [*Category Theory in Context*][ctinc],
which is the main inspiration here and
has the advantage of being available on the author's website.
I also recommend Saunders Mac Lane's 
*Category Theory for the Working Mathematician*
and Francis Borceux's *Handbook of Categorical Algebra.*

## Categories
A *category* $$C$$ is a collection of *objects,* say $$c$$, $$d$$, and 
*arrows* between them, say $$f\colon c\to d$$.
Given a pair of arrows as below

$$\require{AMScd}\begin{CD} a @>f>> b @>g>> c,\end{CD}$$

we require the existence of their *composition,* $$gf\colon a\to c$$.
Composition is associative, and for each object $$c$$, there is a
(unique) arrow $$1_c\colon c\to c$$ which acts as an identity for composition
of arrows.

Many familiar mathematical objects assemble into categories.
To wit, there is the *category of sets,* where objects are sets
and arrows are functions of sets, and the *category of topological spaces,*
where objects are topological spaces and arrows are continuous maps.
However, the notion of a category is flexible: not all categories
have "sets with additional structure" as objects.
For instance, a *preorder* is the same data as a category
where there is at most one arrow between any two objects.
Here an arrow $$c\to d$$ should be interpreted as saying $$c\le d$$.

Note that I use the term *collection* advisedly: Russell's paradox
says that there can be no set of all sets, so the category of
sets has more than a set's worth of objects! However,
between any two sets, there is only a set's worth of distinct functions.
That is, if $$a$$ and $$b$$ are sets, there is a *set*

$$\operatorname{Set}(a,b) = \{f\colon a \to b\}.$$

Categories where this is the case for all objects are called *locally small.*
If additionally there is only a set's worth of arrows in the entire category
(and thus only a set's worth of objects!), the category is called *small.*

## Functors
If $$C$$ and $$D$$ are categories, a *functor* $$F\colon C \to D$$
is an assignment 

$$\begin{CD}a &\mapsto &Fa \\ @VfVV \mapsto @VVFfV \\ b &\mapsto &Fb.\end{CD}$$

I.e. for each object $$a$$ of $$C$$, there is an object $$Fa$$ in $$D$$,
and for each arrow $$f\colon a\to b$$ in $$C$$, there is an arrow
$$Ff\colon Fa\to Fb$$. Additionally, $$F$$ is required to satisfy

$$F1_{a} = 1_{Fa}$$ 

for all $$a$$ in $$C$$, and $$F$$ must
respect composition in the sense that 

$$F(gf) = FgFf.$$

Such functors are sometimes called *covariant.*

Every category $$C$$ has an *opposite category* 
$$\newcommand{\op}{^{\mathrm{op}}}C\op$$, which is obtained from
formally reversing the direction of all the arrows.
Thus if $$C$$ has arrows

$$\begin{CD} a @>f>> b @>g>> c,\end{CD}$$

then $$C\op$$ has arrows

$$\begin{CD} a @<f\op<< b @<g\op<< c.\end{CD}$$

Any statement about objects and arrows in $$C$$ has a *dual*
statement about objects and arrows in $$C\op$$, which is obtained
by reversing the direction of all the arrows.
If the proof of the original statement is categorical,
dualizing the proof yields a proof of the dual statement for $$C\op$$.

The definition of a functor admits dualization in $$C$$ or in $$D$$.
The import is essentially the same as long as only one dualization is
performed: the result is a *contravariant functor* $$G\colon C\op \to D$$:

$$\begin{CD} a &\mapsto & Ga \\ @VfVV \mapsto @AAGfA \\ b &\mapsto &Gb.
\end{CD}$$


Functors abound in mathematics. Many are so simple that we hardly think about
them: for instance the "forgetful" 
functor from the category of groups and homomorphisms
to sets that sends a group $$G$$ to its set of elements,
and a group homomorphism to its action on underlying sets.

If $$C$$ is a locally small category and $$c$$ is an object,
there are two particularly important functors $$C \to \operatorname{Set}$$.
Write $$C(c,b)$$ and $$C(b,c)$$ for the set of arrows in $$C$$
with domain and codomain $$c$$, respectively.
If $$f\colon b\to d$$ is an arrow in $$C$$, there are
functions 

$$f_*\colon C(c,b) \to C(c,d) \text{ and }f^*\colon C(d,c) \to C(b,c)$$

defined as $$f_*(g) = fg$$ and $$f^*(h) = hf$$, respectively.
The assignments

  $$\begin{CD} b &\mapsto & C(c,b) &\qquad\qquad &b &\mapsto & C(b,c) \\
    @VfVV \mapsto @VVf_*V \qquad\qquad @VfVV \mapsto @AAf*A \\
    d &\mapsto &C(c,d) &\qquad\qquad &d &\mapsto & C(d,c)
  \end{CD}$$

define covariant and contravariant functors 
$$C(c,-)\colon C \to \operatorname{Set}$$ and  
$$C(-,c)\colon C\op\to\operatorname{Set}$$, respectively.

### Natural Transformations
Just as we have defined functors between categories,
it is  useful to consider *functor categories,*
whose elements are functors $$C\to D$$. To do this, we need 
a  notion of a morphism between functors. It turns out
that the right notion is a *natural transformation.*
If $$F,G\colon C \to D$$ are functors, a natural transformation
$$\eta\colon F\Rightarrow G$$ is a collection of maps
$$\eta_c\colon Fc \to Gc$$, one for each object $$c$$ of $$C$$
such that for every arrow $$f\colon c \to d$$, the following
diagram commutes

$$\begin{CD}
  Fc @>\eta_c>> Gc \\
  @VFfVV @VVGfV \\
  Fd @>\eta_d>> Gd.
\end{CD}$$

Any directed path in a diagram of objects and arrows within
a category like the above yields an arrow from the initial 
"vertex" of the path to the terminal one by reading off the
labelled arrows. A diagram *commutes* if any two directed
paths with the same endpoints yield equal arrows.
Thus, to say that the above diagram commutes asserts the
equality 

$$Gf\eta_c = \eta_d Ff.$$

The standard example of a natural transformation is the following.
Let $$k$$ be a field, and consider the category of $$k$$-vector spaces
and linear transformations. There is a contravariant functor
that sends a vector space $$V$$ to its *dual* $$V^*$$, namely the vector
space of linear transformations $$V\to k$$.
A linear map $$f\colon V \to W$$ is sent to a map $$f^*\colon W^*\to V^*$$
which is defined as follows.
If $$\lambda\colon W \to k$$ is an element of $$W^*$$,
$$f^*(\lambda)$$ is the linear  map 

$$\lambda f\colon V\to k.$$

Thus there is a *covariant* functor sending a vector space $$V$$
to its "double dual" $$V^{**}=(V^*)^*$$.
There is a natural transformation $$ev$$ from the identity functor
to the double dual functor.
At a given vector space $$V$$, the map $$ev_V$$ sends a vector $$v$$
to the linear map $$V^*\to k$$ defined by "evaluation at $$v$$,"
namely

$$\lambda \mapsto \lambda(v),\quad  \lambda \in V^*.$$

Naturality of $$ev$$ asserts that for $$f\colon V \to W$$
a linear map, the following diagram commutes

$$\begin{CD}
  V @>ev_V>> V^{**} \\
  @VfVV @VVf^{**}V \\
  W @>ev_W>> W^{**}.
\end{CD}$$

To show this, consider a vector $$v \in V$$.
The element $$f^{**}(ev_V(v)) \in W^{**}$$ is
the linear map 

$$ev_V(v)\circ f^*\colon W^*\to k,$$

so its action on $$\lambda \in W*$$ is 

$$ev_V(v)(f^*(\lambda)) = ev_V(v)(\lambda f) = 
\lambda (f(v)) = ev_W(f(v))(\lambda),$$

demonstrating naturality.

The map $$ev_V$$ is an isomorphism when $$V$$ is finite dimensional.
Thus we say that when restricted to the *subcategory*
of finite dimensional vector spaces, $$ev$$ is a *natural isomorphism.*

### The Yoneda Lemma
Perhaps the fundamental result in category theory
is the following:

> **Theorem.** (The Yoneda Lemma)      
>  Let $$C$$ be a locally small category and
>  $$F\colon C \to \operatorname{Set}$$ a functor.
>  For each object $$c$$ of $$C$$, there is a bijection

$$\{\alpha\colon C(c,-)\Rightarrow F\} \longleftrightarrow \{x \in Fc\}$$

>  implemented by sending a natural transformation
>  $$\alpha$$ to the element $$\alpha_c(1_c)$$.
>  This bijection is natural in $$F$$ and $$c$$.

The proof is straightforward, once one figures out what needs proving.
The utility of the Yoneda lemma is likely 
far from obvious when one first meets it,
but it turns out to be a major tool in category theory.

[eminar]: http://www.danielkeliher.com/EminarCurrent.html
[ctinc]: http://www.math.jhu.edu/~eriehl/context.pdf
