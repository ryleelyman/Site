---
layout: post
math: true
---

A week ago I attended [Big Mapping Class Groups at BC](http://ianbiringer.net/bigmcg.html),
a workshop where participants, myself included,
presented on papers about mapping class groups of infinite-type surfaces that we did not write.
I'd like to spend a couple of posts talking about the paper I was assigned,
[Large scale geometry of big mapping class groups](https://arxiv.org/abs/1912.10914)
by [Katie Mann](https://e.math.cornell.edu/people/mann/) and [Kasra Rafi](https://www.math.toronto.edu/~rafi/).
This is post "zero" in that series; 
I want to describe the project of large scale geometry of groups.

## Groups as metric spaces

So, let's begin.
Let $$G$$ be a group,
and $$S$$ a symmetric generating set.
Here, *symmetric* means that if $$s$$ belongs to $$S$$, so does $$s^{-1}$$.
Every element $$g$$ of $$G$$ can be written as

$$g = s_1 s_2 \ldots s_n$$

where each $$s_i$$ belongs to $$S$$,
and we define the *word length* $$||g||$$ of $$g$$ to be the minimal $$n$$ possible.
By convention, the length of the identity element is zero.
This yields a *word metric* on $$G$$, where the distance $$d_S$$ between $$g$$ and $$h$$ is

$$d_S(g,h) = ||g^{-1}h||.$$

A good exercise is to prove that $$d_S$$ *is* a metric
(i.e. it's symmetric, nonnegative, nonzero if $$g \ne h$$, and satisfies the triangle inequality)
that is additionally *left invariant,* in the sense that $$d_S(kg,kh) = d_S(g,h)$$
for all $$k \in G$$.
Note: symmetry of $$d_S$$ seems to require symmetry of $$S$$.
If you relaxed the requirement of symmetry,
you might get "asymmetric" metrics.

## Quasi-isometric invariance

Now, different choices of $$S$$ yield *a priori* different metrics.
But! In some cases, some "large-scale" features of the metric are actually properties of the group,
in the sense that $$d_S$$ and $$d_{S'}$$ are *quasi-isometric.*
I defined quasi-isometry in [this post](https://ryleealanza.org/2021/07/01/Gromov-hyperbolicity-for-arbitrary-metric-spaces.html),
but the rough idea (as it were) is that distances are distorted a uniformly bounded amount
both multiplicatively and additively.
The classic example of this is the following lemma, due independently to Milnor and Schwarz.

> **Lemma.** Suppose 
