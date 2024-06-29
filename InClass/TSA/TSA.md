- [Statistical inference I: Foundations of statistical models](#statistical-inference-i-foundations-of-statistical-models)
  - [Measure Theory](#measure-theory)
    - [Example (Dice)](#example-dice)
    - [Definition ($\\sigma$-Algebra)](#definition-sigma-algebra)
    - [Remark](#remark)
    - [Example (Trivial $\\sigma$-algebras)](#example-trivial-sigma-algebras)

# Statistical inference I: Foundations of statistical models
## Measure Theory

Let $\Omega \neq \emptyset$ be an arbitrary set. For $A \subseteq \Omega$, the set $A^c := \{\omega \in \Omega \mid \omega \notin A\}$ is called the complement of $A$ in $\Omega$. The set $\mathcal{P}(\Omega) = \{B \mid B \subseteq \Omega\}$ is the power set of $\Omega$ and contains all subsets of $\Omega$.

### Example (Dice)

A six-sided unbiased dice is rolled. The goal is to find a suitable and rigorous mathematical concept of this real-world random experiment. To represent this experiment, the space $\Omega$ should include all elementary events that can occur during the roll, i.e., the occurrence of any of the six numbers. For the simple dice roll, this means

$\Omega = \{1, 2, 3, 4, 5, 6\}$.

In the following, we will usually refer to $\Omega$ as the set of all elementary events that can occur. But what if the outcome of the dice roll is not fully observable? Perhaps we only receive the information whether the outcome number is odd or even. The set of all sets of elementary events that are observable are modeled in the following definition of a $\sigma$-algebra.

### Definition ($\sigma$-Algebra)

A set $A \subseteq \mathcal{P}(\Omega)$ is called a $\sigma$-algebra on $\Omega$ if:

- $\Omega \in A$,
- $A \in A \Rightarrow A^c \in A$,
- $A_1, A_2, \ldots \in A \Rightarrow \bigcup_{n=1}^{\infty} A_n \in A$.

Elements of $A$ are called measurable sets. The tuple $(\Omega, A)$ is called a measurable space.

A $\sigma$-algebra is designed to assign a measure to an observed event.

### Remark

The properties of a $\sigma$-algebra have the following interpretations in the context of modeling a random experiment (i.e., the process by which an observation is made):

- We should be able to observe that an experiment has taken place,
- If the occurrence of an event is observable, we should also be able to observe the case that the event has not occurred,
- If the occurrence of a countable sequence of events is observable，we should also be able toobserve that one of these events has occurred. This translates to a logical OR relationship between events.

### Example (Trivial $\sigma$-algebras)

The set $A_1 = \{\emptyset, \Omega\}$ and the power set $A_2 = \mathcal{P}(\Omega)$ are $\sigma$-algebras.
