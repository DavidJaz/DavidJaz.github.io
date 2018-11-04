---
published: true
---
The arithmetic mean is perhaps one of the oldest mathematical ideas, intimately tied to fairness in mutual endeavor. The arithmetic mean answers the question "what payout would we have gotten if we all got the same payout", or in other words, which $$A$$ makes

>$$p_1 + \cdots + p_n = A + \cdots + A$$

true? Most people are familiar with the arithmetic mean, and a few math nerds might know about the geometric or harmonic means. But what is a _mean_, in general?

In general, we might think of a mean as a way of turning many things into one thing. But we shouldn't be led to prematurely coneptualize our ensembles as sets. In this post, I would like to work out some of the consequences of the following idea:

**Idea:** A *mean* is a way of representing some aspect of a complicated figure in terms the same aspect of a simpler figure.

## Definition of a Mean

We can formalize the above idea as follows

**Definition:** Let $$c : S \to P$$ be way to collapse the shape $$S$$ onto the shape $$P$$. Denote by $$\Delta_c : X^P \to X^S$$ the induced restriction map. Let $$a : X^S \to Q$$ be some aspect of $$S$$-shaped figures in $$X$$. 

Given a figure $$f : S \to X$$ of shape $$S$$, an $$a$$*-mean* for $$f$$ is a figure $$m : P \to X$$ of shape $$P$$ which has the same aspect of $$f$$:

> $$amc = af.$$

A *mean function*, or just a mean for short, is an assignment $$m : X^S \to X^P$$ of a mean to each $$S$$-shaped figure, 
![diag1.png]({{site.baseurl}}/_posts/diag1.png)


Usually, we are interested in means for which $$P= \ast$$ is a single point. 

**Examples:** For all the following, $$P = \ast$$
* Let $$X = \mathbb{R}$$, $$S = n$$ a finite set. Then an $$S$$-shaped element of $$X$$ is a set of $$n$$ natural numbers. Let $$a : \mathbb{R}^n \to \mathbb{R}$$ be the sum, $$a(\lambda i. x_i) = \sum_{0 \leq i \leq n} x_i$$. 

There is a unique mean $$m : \mathbb{R}^n \to \mathbb{R}$$, and it is defined by 

>$$m(\lambda i. x_i) + \cdots + m(\lambda i. x_i) = x_1 + \ldots + x_n$$

or, solving,

>$$m(\lambda i. x_i) = \frac{x_1 + \ldots + x_n}{n}.$$

So the arithmetic mean is a mean as we've defined it.
* If we change the aspect $$a$$ above to be the product, we get the geometric mean. If we change it to be the reciprocal of the sum of the reciprocals, we get the harmonic mean. 
* If we work in a continuous category, and let $$S$$ be a compact subspace of $$\mathbb{R}^n$$ (a body) and $$X$$ be an ambient space. Suppose we have a mass distribution $$ d : X \to \mathbb{R}$$, and let 

>$$a(b) = \int_B d(b)$$

be the total mass of a body $$b : B \to X$$. Then a mean $$m : X^S \to X$$ for this assigns to each body the position of its center of mass.

**Observation:** If $$m$$ is a mean for the aspect $$a : X^S \to Q$$, and $$t : Q \to Q'$$ is any transformation of that aspect, then $$m$$ is a mean for $$ta$$ as well. If this transformation is a monomorphism, then any $$ta$$-mean is a mean for $$a$$; if $$tac^{\ast}m = ta$$, then $$ac^{\ast}m = a$$.

## When do Means Exist?

Let's look a bit more closely about the calculation of the arithmetic mean. We noted that

>$$m(\lambda i. x_i) + \cdots + m(\lambda i. x_i) = n \cdot m(\lambda i. x_i)$$

and then we noted that multiplying by $$n$$ is an isomorphism of $$\mathbb{R}$$. The mean was then given by summing up (taking the aspect of the figure) and then multiplying by the inverse of $$n$$. We can break this observation up into three parts.

**Lemma:** If
* $$ac^{\ast}$$ is a monomorphism, then means are unique,
* $$ac^{\ast}$$ is a split epimorphism by $$s$$, then $$sa$$ is a mean, and
* $$ac^{\ast}$$ is an isomorphism by $$s$$, then $$sa$$ is the unique mean and it splits $$c^{\ast}$$.
*proof:* We prove these claims in turn.
* Suppose that $$ac^{\ast}$$ is mono, and let $$m$$ and $$m'$$ be means. Then $$ac^{\ast}m = a = ac^{\ast}m'$$ and so $$m = m'$$ by monomorphicity.
* Suppose that $$ac^{\ast}$$ is split epi by $$s$$. Then $$ac^{\ast}s = \textbf{id}$$, so that $$ac^{\ast}sa = a$$.
* If $$ac^{\ast}$$ is iso by $$s$$, then $$sa$$ is a mean and since $ac^{\ast}$ is then mono, it is unique. Furthermore, $$sac^{\ast} = \textbf{id}$$ so that $$sa$$ splits $$c^{\ast}$$.

That last property is perhaps useful to single out as a desired characteristic of means. Lacking a better name, I'll call such a mean *normal*.

**Definition:** A mean $$m$$ is *normal* if $$mc^{\ast} = \textbf{id}$$. 

In a category with an epi-mono factorization system, we can factor any aspect $$a : X^S \to Q$$ into $$a = ie$$ with $$i$$ mono and $$e$$ epi. Since $$i$$ is mono, the $$a$$ means correspond to the $$e$$ means. So, in this case, we can always assume our aspects are epi.

## Perfect Means

A perfect mean is a mean which loses no information. In other words, a perfect mean is a mean for the thing itself, and not just some aspect of it.

**Definition:** A perfect mean is a mean for $$a = \textbf{id}_{X^S}$$. Equivalently, a perfect mean is a section of $$\Delta_c$$.

We can expand the criterion for perfect means a bit.

**Lemma:** If $$a$$ is mono and $$m$$ is a mean, then $$m$$ is a perfect mean. If $$m$$ is also normal, then $$m$$ is an inverse of $$c^{\ast}$$.
*proof:* If $$m$$ is a mean, then $$ac^{\ast}m = a$$, so if $$a$$ is mono, then $$c^{\ast}m = \textbf{id}$$. For $$m$$ to be normal is precisely $$mc^{\ast} = \textbf{id}$$.

Intuitively, the existence of a perfect mean should impose strong conditions on the relationship between $$S$$, $$P$$, and $$X$$; if $$X$$ allows a lot of movement, then this must mean that $$S$$ and $$P$$ are very similar, and if $$S$$ and $$P$$ are very different, this must mean $$X$$ is very rigid. We can prove a beginning result to this end.

**Lemma:** Let $$S = 2$$ and $$P = 1$$. Then $$X$$ admits a perfect mean if and only if it is subterminal.
*Proof:* We note that in this case, $$c^{\ast} = \Delta$$ is mono. Therefore, it has a section if and only if it is iso. But an object is subterminal if and only if it is isomorphic to its cartesian square.

In other words, if you can perfectly average two things, then you had at most one thing.

## Next Time

In the next post on the topic of means, I hope to look into what happens if you turn the intuition around. The idea of a mean was to express an aspect of a complicated figure in terms of the same aspect of a simpler figure. What if we tried to express an aspect of a simple figure in terms of the same aspect of a more complicated figure?
