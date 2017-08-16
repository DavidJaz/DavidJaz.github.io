---
published: false
---
## Constant Quantities and Constant Domains

When explaining category theory to my friends (which happens more than you might think), I often find myself summing the theory up as "the abstract study of variable quantities". We analyse the notion of a variable quantity into two components: what the quantity *is*, and with what the quantities *varies*. To say that a quantity $q$ *is* an number that *varies* with the time (say, if $q$ is the position of a beetle as it walks along the edge of a ruler, or the angle in degrees that the sun makes with the horizon), we write $q : T \to N$ where $T$ is our notion of time and $N$ our notion of number. 

The question comes: how do represent constant quantities? The usual answer: they are quantities $q : 1 \to X$, whose domain is a "single point" characterized as the terminal object. But why do these quantities deserve the name "constant"? What is so special about the domain $1$?

When answering these questions, I have for a while now fallen back onto another interpretation of the arrow $a : A \to B$. We can see the arrow $a : A \to B$ as a "figure of shape $A$ in $B$". The, I equivocate by saying, "Well, the quantity $q : 1 \to X$ is constant because $1$ is, as a shape, a single point, and therefore $q$ varies over a point, which is to say it doesn't vary at all". This approach is overly complicated because it introduces a whole new metaphor for the arrow. But even more, it leads to problematic intuitions later on.

Euclid begins his *Elements* with the definition: "A point is that which has no part". This proclamation has colored our intuitions of points ever since. So, if we primarily conceptualize the terminal object as a point, and use that conception as our reason for using it as the domain of constant quantities, then we are conceptually ill-equipped to handle the existence of nontrivial subterminal objects. I remember the idea of nontrivial subterminal objects being difficult to grasp.

We can resolve both of these issues at the same time by directly defining what it means for a quantity to be constant, and what it then means for a domain to be a domain of constant quantities.

# Definitions and the Basic Theory

Let's begin by defining what it means for a quantity to be constant. Intuitively, a quantity $q$ which depends on a variable $t$ is constant if no matter how $t$ is specified, the resulting quantity is the same.  We can formalize this as follows:

**Definition:** A quantity $q : A \to B$ is *constant* if for any $x, y : X \to A$, $q \circ x = q \circ y$.

We can piggy back off of this definition to define a constant domain.

**Definition:** A domain $C$ is *constant* if every quantity varying over it is constant. (That is, $C$ is constant if all $q : C \to X$ are constant.)

We can immediately give a less grand and more categorical-feeling characterization of constant domains.

**Claim:** A domain $C$ is constant if and only if its identity map is constant. 

**Proof:** If $C$ is constant, then every map out of it is constant, including the identity. On the other hand, if the identity is constant, then for any map $q : C \to X$ and $x, y : Y \to C$ we have
$$q \circ x = q \circ C \circ x = q \circ C \circ y = q \circ y.$$

We can follow this up by expanding what it means for the identity map to be constant.

**Claim:** A domain $C$ is constant if and only if there is at most one quantity $X \to C$ for each domain $X$.

**Proof:** This is exactly what it means for the identity of $C$ to be constant. If the identity of $C$ is constant, then for any $x, y : X \to C$ we have that $x = C \circ x = C \circ y = y$. On the other hand, if for any two $x, y : X \to C$, $x = y$, then $C \circ x = C \circ y$.





























