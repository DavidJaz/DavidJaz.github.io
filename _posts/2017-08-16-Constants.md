---
published: false
---
## Constant Quantities and Constant Domains

When explaining category theory to my friends (which happens more than you might think), I often find myself summing the theory up as "the abstract study of variable quantities". We analyse the notion of a variable quantity into two components: what the quantity *is*, and with what the quantities *varies*. To say that a quantity $q$ *is* an number that *varies* with the time (say, if $q$ is the position of a beetle as it walks along the edge of a ruler, or the angle in degrees that the sun makes with the horizon), we write $q : T \to N$ where $T$ is our notion of time and $N$ our notion of number. 

The question comes: how do represent constant quantities? The usual answer: they are quantities $q : 1 \to X$, whose domain is a "single point" characterized as the terminal object. But why do these quantities deserve the name "constant"? What is so special about the domain $1$?

When answering these questions, I have for a while now fallen back onto another interpretation of the arrow $a : A \to B$. We can see the arrow $a : A \to B$ as a "figure of shape $A$ in $B$". The, I equivocate by saying, "Well, the quantity $q : 1 \to X$ is constant because $1$ is, as a shape, a single point, and therefore $q$ varies over a point, which is to say it doesn't vary at all". This approach is overly complicated because it introduces a whole new metaphor for the arrow. But even more, it leads to problematic intuitions later on.

Euclid begins his *Elements* with the definition: "A point is that which has no part". This proclamation has colored our intuitions of points ever since. So, if we primarily conceptualize the terminal object as a point, and use that conception as our reason for using it as the domain of constant quantities, then we are conceptually ill-equipped to handle the existence of nontrivial subterminal objects. I remember the idea of nontrivial subterminal objects being difficult to grasp.

We can resolve both of these issues at the same time by directly defining what it means for a quantity to be constant, and what it then means for a domain to be a domain of constant quantities. This post will be a very elementary theory of constant quantities.

# Definitions and Relationship to the Terminal Object

Let's begin by defining what it means for a quantity to be constant. Intuitively, a quantity $q$ which depends on a variable $t$ is constant if no matter how $t$ is specified, the resulting quantity is the same.  We can formalize this as follows:

**Definition:** A quantity $q : A \to B$ is *constant* if for any $x, y : X \to A$, $q \circ x = q \circ y$.

We can piggy back off of this definition to define a constant domain.

**Definition:** A domain $C$ is *constant* if every quantity varying over it is constant. (That is, $C$ is constant if all $q : C \to X$ are constant.)

We can immediately give a less grand and more categorical-feeling characterization of constant domains.

**Claim:** A domain $C$ is constant if and only if its identity map is constant. 

**Proof:** If $C$ is constant, then every map out of it is constant, including the identity. On the other hand, if the identity is constant, then for any map $q : C \to X$ and $x, y : Y \to C$ we have
$$q \circ x = q \circ C \circ x = q \circ C \circ y = q \circ y.$$ $\square$

We can follow this up by expanding what it means for the identity map to be constant.

**Claim:** A domain $C$ is constant if and only if there is at most one quantity $X \to C$ for each domain $X$.

**Proof:** This is exactly what it means for the identity of $C$ to be constant. If the identity of $C$ is constant, then for any $x, y : X \to C$ we have that $x = C \circ x = C \circ y = y$. On the other hand, if for any two $x, y : X \to C$, $x = y$, then $C \circ x = C \circ y$. $\square$

Furthermore, any quantity varying within a constant domain is in fact constant. Intuitively, this is because "there isn't enough space in a constant domain to vary".

**Claim:** A domain $C$ is constant if and only if every quantity $q : X \to C$ is constant.

**Proof:** If $C$ is constant and $x, y : Y \to X$, then $q \circ x = q \circ y$ since they are both maps $Y \to C$. On the other hand, if every quantity $q : X \to C$ is constant, then in particular the identity of $C$ is constant. $\square$

Now we can begin to see the relationship to the terminal object.

**Corollary:** The terminal object $1$, if it exists, is constant.

**Proof:** The uniqueness portion of the universal property gaurentees that there is at most one map $X \to 1$ for any $X$. $\square$

In fact, if there is a terminal object, we can give another characterization of the constant domains. Let's prove a few basic lemmas relating constant maps to monic maps. Intuitively, monic maps are "one-to-one". If ther is "at most one" element of the domain (that is, the domain is constant), then every map out of it should be one-to-one.

**Lemma:** Every quantity varying over a constant domain is monic.

**Proof:** If $q : C \to X$ is a quanity varying over a constant domain, then for any two maps $x, y : Y \to C$ such that $q \circ x = q \circ y$ (which happens to be any $x, y : Y \to C$), we have that $x = y$ (since $C$ is constant). $\square$

We have a converse to this lemma as well, which we might as well prove now.

**Lemma:** Suppose that $q : C \to X$ is constant and monic. Then $C$ is constant.

**Proof:** Let $x, y : Y \to C$. Since $q$ is constant, $q \circ x = q \circ y$. But then since $q$ is monic, $x = y$. $\square$

Intuitively, if a map is both one-to-one and constant, then there must be "at most one" element of the domain. Furthermore, any part of a constant domain is itself constant.

**Corollary:** If $m : C \to C'$ is a monic, and $C'$ is constant, then $C$ is consant.

**Proof:** Maps into a constant domain are constant, and the domain of a constant monic map is constant. $\square$

Now, we can show that if there is a terminal object, then the constant domains are precisely the subterminal objects.

**Claim:** If there is a terminal object $1$, then a domain is constant if and only if it is subterminal.

**Proof:** If $C$ is constant, then the terminal map $! : C \to 1$ is monic by the above lemma. If $C$ is subterminal, then $! : C \to 1$ is a monic constant, so $C$ is constant. $\square$

I think this demystifies the subterminal objects somewhat: they are just the possible domains for constant quantities. In fact, I think it also helps demystify the terminal object as a constant domain: in a precise sense, the terminal object is the largest constant domain. We will come to this idea later.

# Relationship of Constants to Pullbacks and Products

With our definition of constant quantity and constant domain in hand, we can formalize the intuition that a monic map is one-to-one. Intuitively, a map is one-to-one if it cannot send two distinct things to the same place. In more positive terms, this means that the inverse image of a constant should be itself constant.

**Claim:** The pullback of a constant along a monic is constant.

**Proof:** Let $c : A \to B$ be constant and $m : X \to B$ be monic. We need to show that $m^{\ast}c : X \times_B A \to X$ is constant. Let $x, y : Y \to X \times_B A$. These correspond respectively to $x_1, y_1 : Y \to X$ and $x_2, y_2 : Y \to A$ for which $c \circ x_2 = m \circ x_1$ and $c \circ y_2 = m \circ y_1$. Since $c$ is constant, we have that $c \circ x_2 = c \circ y_2$. From this and the previous equations, we see that $m \circ x_1 = m \circ y_1$. Since $m$ is monic, we conclude that $x_1 = y_1$. But then $x = m^{\ast}c \circ x_1 = m^{\ast}c \circ y_1 = y$, so $m^{\ast}c$ is constant. $\square$

If we say that a map is "one-to-one" if the pullback of any constant along it is constant, then we have just shown that monic maps are one-to-one. It will not in general be possible to prove a converse, since the monicness of a map must be checked on non-constant quantities (figures of more complicated shape than a point) as well. This also gives a slick way to prove that parts of constant domains are constant; just pull back the identity.

There is a nice relationship between constant domains and products. 

**Claim:** $C$ is a constant domain if and only if the diagonal map $\Delta : C \to C \times C$ is an isomorphism.

**Proof:** Suppose that $C$ is constant. Then the two projections $p_1, p_2 : C \times C \to C$ are equal. Call this single map $p : C \times C \to C$. Since $p_1 \circ \Delta = C$, $p \circ \Delta = C$. On the other hand, $\Delta \circ p = (p, p) = (p_1, p_2) = C \times C$, so $p$ is the inverse of $\Delta$.

If $\Delta$ is an isomorphism with inverse $p$, then for any $x, y : X \to C$, we have that $(x, y) = \Delta \circ p \circ (x, y) = (p \circ (x, y), p \circ (x, y))$, so $x = p \circ (x, y) = y$. $\square$

It's also straightforward to show that if the diagonal map is constant, then the domain is constant. In total, we can sum up our various definitions of a constant domain as follows.

**Claim:** The following are equivalent when they can hold
* $C$ is a constant domain.
* Every quantity varying over $C$ is constant.
* Every quantity varying in $C$ is constant.
* The identity of $C$ is constant.
* $C$ is subterminal.
* The diagonal of $C$ is an isomorphism $C \cong C \times C$.
* The diagonal of $C$ is constant.
* There is a monic constant with domain $C$.

Constant domains play nicely with products in another sense.

**Claim:** The product of two constant domains is constant.

**Proof:** A map into the product is a pair of maps into each constant domain, but since those domains are constant there is at most one such pair.

By a similar proof, any limit of a diagram of constant domains is constant.

# Constant Domains and Supports

Why are there (potentially) so many different constant domains? If I define a quantity $q : C \to X$, and you define one $q' : C' \to X$, what makes them different? Here, I would like to make an analogy between constant domains and "namespaces" as they arise in programming languages.

It is fairly common to call an arrow $q : 1 \to X$ a "global element" of $X$. Since we are focusing on the arrows-as-quantities view (rather than the arrows-as-figures view), we could call this a "global constant" of $X$. This suggests, if only by contraposition, that we could call $q : C \to X$ for constant domains other than $X$ "local constants". 

We can think of the constant domains then as "namespaces" in which a constant is defined. A global constant is defined in the global namespace (say, in the "main" file of your project), while the local constants are defined in smaller namespaces (say, within particular class definitions, or whatever). A map $C \to C'$ is a  containment of namespaces (since $C'$ is constant, there can be at most one such map). In this case, any constant defined over in the namespace $C'$ can be used in $C$ by precomposing.

I'm not sure how well this analogy really plays out. But it *is* a good idea to think of the different constant domains as different "local domains of definition for constants". The category of constant domains is then seen to be the category of these possible local domains.

**Definition:** An object $X$ is *defined over* a constant domain $U$ if there is a map $X \to U$.

Being defined over a constant domain is a property of an object, not a structure on that object, because there is at most one map into a constant domain. $X$ being defined over $U$ constrains the possible kinds of constants in $X$; If $c : C \to X$ is a constant, then the composite $C \to X \to U$ shows us that $C$ is contained in $U$. Intuitively, $X$ is defined over $U$ if the constants in $X$ are at most defined over $U$.

This leads us to the natural question: is there a smallest $U$ over which $X$ is defined?

**Claim:** Suppose that for every object $X$, there is a constant domain $\sigma X$ which is the smallest constant domain over which $X$ is defined. Then $\sigma$ is a left adjoint to the inclusion of the constant domains.

**Proof:** The adjoint bijection is
$$\frac{X \to U}{\sigma X \to U}$$
which precisely states that $\sigma X$ is the smallest constant domain over which $X$ is defined. The unit shows that $X$ is defined over $\sigma X$. We see that $\sigma$ is functorial as well; given $f : X \to Y$, we take the composite $X \to Y \to \sigma X$ and therefore find that $\sigma X \to \sigma Y$.



