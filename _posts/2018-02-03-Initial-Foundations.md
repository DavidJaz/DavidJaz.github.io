---
published: false
---
## Initial Foundations

Axioms for the initial topos.

We assert the existence of two sorts of mathematical objects: **kinds** and **variable quantities**. Each variable quantity _is_ a certain kind of quanity, and _depends on_ or _varies with_ an independent variable of a certain kind of quantity. We write $$q : A \to B$$ to say that $$q$$ _is_ a $$B$$ that _varies with_ an $$A$$.

Given a quantity $$q : B \to C$$ depending on a quantity of kind $$B$$, we may **specialize** it by any quantity $$p : A \to B$$ of kind $$B$$ to get a quantity $q \circ p : A \to C$$. When specializing a quantity multiple times, it doesn't matter which order we specialize it in. In other words, specialization is associative.

Furthermore, to each kind $$A$$, we ask for an **independent variable** $$\bar A$$ (or **generic element**) of kind $$A$$. The quantity $$\bar A$$ is independent in the sense that it depends only on itself, so $$\bar A : A \to A$$. Since a quantity $$q : A \to B$$ depends on an independent variable of kind $$A$$, specializing it by that independent variable does nothing. In other words, $$q \circ \bar{A} = q$$. On the other hand, specializing an indpendent variable by anything just gives us that thing again, so that $\bar{A} \circ p = p$.

Given two quantities $$p : A \to C$$ and $$q : B \to C$$ of kind $$C$$, we now claim that there is a kind $$A \times_C B$$ (notationally leaving $$p$$ and $$q$$ implicit) of pairs $$(a, b)$$ of quantities of kind $$A$$ and $$B$$ respectively so that $$p \circ a = q \circ b$$. More explicitly, there is a kind $$A \times_C B$$ such that every quantity $$x : X \to A \times_C B$$ is associated to unique such pair $$(x_a, x_b)$$, and that this association is stable under specialization. 

Next we assert the existence of a quantity simpliciter. From this quantity, all the rest of our theory will bloom. We assert the existence of a quanity $$\text{true}$$, which is a proposition $$\text{Prop}$$ depending on a notion f
