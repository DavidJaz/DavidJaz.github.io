---
published: true
---
## All Functions Are Smooth!? What about...

In [synthetic differential geometry](https://ncatlab.org/nlab/show/synthetic+differential+geometry), all real functions of a real variable are smooth -- infinitely differentiable. This is due to the Kock-Lawvere axiom, which says:

**Kock-Lawvere Axiom** Let $D = \{ \epsilon \in \mathcal{R} \mid \epsilon^2 = 0\}$ be the set of nilsquare infinitesimals. Every function $f : D \to \mathcal{R}$ is of the form
$$f(\epsilon) = f(0) + s\epsilon$$
for unique slope $s$. In other words, $D$ is a small line which may be placed in space, but not bent; any function of it is linear.

In particular, the K-L axiom lets us take the deriative of any real function by packaging the slopes together into a new function:
$$f(x + \textbf{d} x) = f(x) + \frac{\textbf{d} f}{\textbf{d} x}(x)\textbf{d} x,\quad\mbox{for nilsquare $\textbf{d} x$}$$

So we can take the derivative of any function, including the derivatives we take. Therefore, all functions are smooth. But wait! Are we not very familiar with functions that not only are not smooth, but are even not differentiable? Where did all the functions go. How could we live in a world without them?

In the usual models of SDG such as the [Cahiers topos](https://ncatlab.org/nlab/show/Cahiers+topos), where the ring $\mathcal{R}$ is the usual real line, all the real functions we know and love (or love to hate) are still there. They just have a different domain. 

For example, consider the absolute value function $|x|$. This is usually defined in the following way:
$$|x| = \begin{cases}-x & \mbox{if $x < 0$} \\ 0 & \mbox{if $x = 0$} \\ x & \mbox{if $x > 0$}  \end{cases}.$$
This definition makes apparent the domain: $x$ can be either less than $0$, equal to $0$, or greater than $0$, so the domain is $(-\infty, 0) \cup \{0\} \cup (0, \infty)$. In other theories of the continuum, this space is the whole line. But this is not the case in SDG, since it clearly ignores those numbers which aren't distinct from $0$: the infinitesimals. How could we take the derivative of a function if we can't apply it to a nilsquare infinitesimal?

For a more robust example, consider the form $x^2 \sin\left(\frac{1}{x}\right)$. This is evidently not defined at $0$, but by noting that the sinusoidal term is always bounded between $-1$ and $1$, we see that it approaches $0$ as $x$ does. This suggests that we extend the domain from $(-\infty, 0) \cup (0, \infty)$ to $(-\infty, 0) \cup \{0\} \cup (0, \infty)$. However, we can note that it is also bounded above by $x^2$ and below by $-x^2$, and both these functions have first derivative $0$ at $0$. Therefore, we can extend the domain of $x^2 \sin\left(\frac{1}{x}\right)$ to $(-\infty, 0) \cup D \cup (0, \infty)$, by sending each nilsquare infinitesimal to $0$. The functions $x^2$ and $-x^2$ however have different second derivatives, so we cannot extend the domain further.

This example shows how real information about functions, such as the number of times they me be differentiated and where, which are supervenient on the functions in the usual theory are esconcend in the domain of the function in SDG.

One thing I don't know, but would like to, is how far such arguments can be taken, and what happens when we ignore our better judgement about functions and extend their domains anyway. For example, we could define the absolute value function to be $0$ on all nilpotent infinitesimals; the domain would still not equal the whole real line, but it would now admit derivatives of all orders at $0$. Does it come down, at the end, to practical considerations about what we want to call "the absolute value function" versus "an absolute value function"?
