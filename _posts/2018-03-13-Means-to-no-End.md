---
published: false
---
The arithmetic mean is perhaps one of the oldest mathematical ideas, intimately tied to fairness in mutual endeavor. The arithmetic mean answers the question "what payout would we have gotten if we all got the same payout", or in other words, which $$A$$ makes
$$$$p_1 + \cdots + p_n = A + \cdots A$$$$$
true? Most people are familiar with the arithmetic mean, and a few math nerds might know about the geometric or harmonic means. But what is a _mean_, in general?

In general, we might think of a mean as a way of turning many things into one thing. But we shouldn't be led to prematurely coneptualize our ensembles as sets. In this post, I would like to work out some of the consequences of the following idea:

**Idea:** A *mean* is a way of representing some aspect of a complicated figure in terms the same aspect of a simpler figure.

## Definition of a Mean

We can formalize the above idea as follows

**Definition:** Let $$c : S \to P$$ be way to collapse the shape $$S$$ onto the shape $$P$$. Denote by $$\Delta_c : X^P \to X^S$$ the induced restriction map. Let $$a : X^S \to Q$$ be some aspect of $$S$$-shaped figures in $$X$$. 

Given a figure $$f : S \to X$$ of shape $$S$$, an $$a$$*-mean* for $f$ is a figure $m : P \to X$ of shape $P$ which has the same aspect of $$f$$:
$$$$amc = af.$$$$

A *mean function*, or just a mean for short, is an assignment $m : X^S \to X^P$ of a mean to each $S$-shaped figure, 
![diag1.png]({{site.baseurl}}/_posts/diag1.png)


Usually, we are interested in means for which $$P= \ast$$ is a single point. 

**Examples:** For all the following, $$P = \ast$$
* Let $$X = \mathbb{N}$$, $$S = n$$ a finite set. Then an $$S$$-shaped element of $$X$$ is a set of $$n$$ natural numbers. Let $$a : \mathbb{N}^n \to \mathbb{N}$$ be the sum, $$a(\lambda i. x_i) = \sum_{0 \leq i \leq n} x_i$$. 

There is a unique mean $$m : \mathbb{N}^n \to \mathbb{N}$$, and it is defined by 
$$$$m(\lambda n. x_n) + \cdots + m(\lambda n. x_n) = x_1 + \ldots + x_n$$$$
or, solving,
$$$$m(\lambda n. x_n) = \frac{x_1 + \ldots + x_n}{n}.$$$$
So the arithmetic mean is a mean as we've defined it.
* If we change the aspect $a$ above to be the product, we get the geometric mean. If we change it to be the reciprocal of the sum of the reciprocals, we get the harmonic mean. 
* If we work in a continuous category, and let $$S$$ be a compact subspace of $$\mathbb{R}^n$$ (a body) and $$X$$ be an ambient space. Suppose we have a mass distribution $$ d : X \to \mathbb{R}$$, and let 
$$$$a(b) = \int_B d(b)$$$$
be the total mass of a body $$b : B \to X$$. Then a mean $m : X^S \to X$ for this assigns to each body the position of its center of mass.

**Observation:** If $$m$$ is a mean for the aspect $a : X^S \to Q$, and $$t : Q \to Q'$$ is any transformation of that aspect, then $$m$$ is a mean for $$ta$$ as well.

## Perfect Means

A perfect mean is a mean which loses no information. In other words, a perfect mean is a mean for the thing itself, and not just some aspect of it.

**Definition:** A perfect mean is a mean for $$a = \textbf{id}_{X^S}$$. Equivalently, a perfect mean is a section of $$\Delta_c$$.

Intuitively, the existence of a perfect mean should impose strong conditions on the relationship between $$S$$, $$P$$, and $$X$$; if $$X$$ allows a lot of movement, then this must mean that $$S$$ and $$P$$ are very similar, and if $$S$$ and $$P$$ are very different, this must mean $$X$$ is very rigid. We can prove a beginning result to this end.

**Lemma:** Let $$S = 2$ and $$P = 1$$. Then $$X$$ admits a perfect mean if and only if it is subterminal.
*Proof:* We note that in this case, $$\Delta_c$$ is mono. Therefore, it has a section if and only if it is iso. But an object is subterminal if and only if it is isomorphic to its cartesian square.






























