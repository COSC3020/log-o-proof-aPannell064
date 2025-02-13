# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

# Proof

$T(n) \in O(log_2(n)) \iff T(n) \in O(log_5(n))$

$(T(n) \in O(log_2(n)) \implies T(n) \in O(log_5(n))) \land (T(n) \in O(log_5(n)) \implies T(n) \in O(log_2(n)))$  //Definition of $\iff$

## Solve Each Side of $\land$ Seperatly:

### First Part

$(T(n) \in O(log_2(n)) \implies T(n) \in O(log_5(n)))$

$(\exists c, n_0: T(n) \leq c \cdot log_2(n) \forall n \geq n_0) \implies (\exists c, n_0: T(n) \leq c \cdot log_5(n) \forall n \geq n_0)$  //Defintion of O

$(\exists c, n_0: T(n) \leq c \cdot log_2(n) \forall n \geq n_0) \implies (\exists c_0, n_0: T(n) \leq c_0 \cdot log_5(n) \forall n \geq n_0)$  //Rename second c to $c_0$ for simplicty

$\forall c, \exists c_0, (\exists n_0: T(n) \leq c \cdot log_2(n) \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c_0 \cdot log_5(n) \forall n \geq n_0)$  //Migrate c and $c_0$ quantifiers to front

$\exists c_0, (\exists n_0: T(n) \leq c \cdot log_2(n) \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c_0 \cdot log_5(n) \forall n \geq n_0)$  //Remove $\forall c$ quantifier

$(\exists n_0: T(n) \leq c \cdot log_2(n) \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c_0 \cdot log_5(n) \forall n \geq n_0)$
