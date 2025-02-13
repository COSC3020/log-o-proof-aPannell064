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

## Proof

$T(n) \in O(log_2(n)) \iff T(n) \in O(log_5(n))$

$(T(n) \in O(log_2(n)) \implies T(n) \in O(log_5(n))) \land (T(n) \in O(log_5(n)) \implies T(n) \in O(log_2(n)))$  // Definition of $\iff$

### Solve Each Side of $\land$ Seperatly

#### Part One

$(T(n) \in O(log_2(n)) \implies T(n) \in O(log_5(n)))$

$(\exists c, n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0) \implies (\exists c, n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0)$  // Defintion of O

$(\exists c, n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0) \implies (\exists c_0, n_0: T(n) \leq c_0 \cdot log_5(n), \forall n \geq n_0)$  // Rename second c to $c_0$ for simplicty

$\forall c, \exists c_0: (\exists n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c_0 \cdot log_5(n), \forall n \geq n_0)$  // Migrate c and $c_0$ quantifiers to front

$\exists c_0: (\exists n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c_0 \cdot log_5(n), \forall n \geq n_0)$  // Remove $\forall c$ quantifier

$(\exists n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq \frac{c}{log_5(2)} \cdot log_5(n) \forall n \geq n_0)$  // Remove $\exists c_0$ quantifier, replacing $c_0$ with $\frac{c}{log_5(2)}$

$(\exists n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0)$  // Log base conversion

$True$    //Self-implication

#### Part Two

$(\exists c, n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0) \implies (\exists c, n_0: T(n) \leq c \cdot log_2(n), \forall n \geq n_0)$  // Defintion of O

$(\exists c, n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0) \implies (\exists c_0, n_0: T(n) \leq c_0 \cdot log_2(n), \forall n \geq n_0)$  // Rename second c to $c_0$ for simplicty

$\forall c, \exists c_0: (\exists n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c_0 \cdot log_2(n), \forall n \geq n_0)$  // Migrate c and $c_0$ quantifiers to front

$\exists c_0: (\exists n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c_0 \cdot log_2(n), \forall n \geq n_0)$  // Remove $\forall c$ quantifier

$(\exists n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq \frac{c}{log_2(5)} \cdot log_2(n) \forall n \geq n_0)$  // Remove $\exists c_0$ quantifier, replacing $c_0$ with $\frac{c}{log_2(5)}$

$(\exists n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0) \implies (\exists n_0: T(n) \leq c \cdot log_5(n), \forall n \geq n_0)$  // Log base conversion

$True$    // Self-implication

### Wrap-up

$(T(n) \in O(log_2(n)) \implies T(n) \in O(log_5(n))) \land (T(n) \in O(log_5(n)) \implies T(n) \in O(log_2(n)))$

$True \land True$  // Proofs in parts one and two

$True$    // $\land$ Idempotent

## Extra Help

"I certify that I have listed all sources used to complete this exercise, 
including the use of any Large Language Models. All of the work is my own, 
except where stated otherwise. I am aware that plagiarism carries severe 
penalties and that if plagiarism is suspected, charges may be filed against 
me without prior notice."
