- [Statistical inference I: Foundations of statistical models](#statistical-inference-i-foundations-of-statistical-models)
  - [Measure Theory](#measure-theory)
    - [Example (Dice)](#example-dice)
    - [Definition ($\\sigma$-Algebra)](#definition-sigma-algebra)
    - [Remark](#remark)
    - [Example (Trivial $\\sigma$-algebras)](#example-trivial-sigma-algebras)
    - [Example (Dice)](#example-dice-1)
    - [Definition (Probability Measure)](#definition-probability-measure)
    - [Remark](#remark-1)
    - [Remark](#remark-2)
    - [Definition (Probability space)](#definition-probability-space)
  - [Probability theory and random variables](#probability-theory-and-random-variables)
    - [Remark (Existence of measures)](#remark-existence-of-measures)
  - [Definition(Generated $\\sigma$-algebra)](#definitiongenerated-sigma-algebra)
    - [Remark](#remark-3)
    - [Definition (Borel $\\sigma$-algebra)](#definition-borel-sigma-algebra)
    - [Remark](#remark-4)
    - [Definition (Measurable map)](#definition-measurable-map)
    - [Example (Measurable maps)](#example-measurable-maps)
    - [Remark](#remark-5)
    - [Theorem (Push-forward)](#theorem-push-forward)
    - [Definition (Random variable)](#definition-random-variable)
    - [Remark](#remark-6)

# Statistical inference I: Foundations of statistical models
## Measure Theory

Let $\Omega \neq \emptyset$ be an arbitrary set. For $A \subseteq \Omega$, the set $A^c := \{\omega \in \Omega \mid \omega \notin A\}$ is called the complement of $A$ in $\Omega$. The set $\mathcal{P}(\Omega) = \{B \mid B \subseteq \Omega\}$ is the power set of $\Omega$ and contains all subsets of $\Omega$.

### Example (Dice)

A six-sided unbiased dice is rolled. The goal is to find a suitable and rigorous mathematical concept of this real-world random experiment. To represent this experiment, the space $\Omega$ should include all elementary events that can occur during the roll, i.e., the occurrence of any of the six numbers. For the simple dice roll, this means

$\Omega = \{1, 2, 3, 4, 5, 6\}$.

In the following, we will usually refer to $\Omega$ as the set of all elementary events that can occur. But what if the outcome of the dice roll is not fully observable? Perhaps we only receive the information whether the outcome number is odd or even. The set of all sets of elementary events that are observable are modeled in the following definition of a $\sigma$-algebra.

### Definition ($\sigma$-Algebra)

A set $\mathcal{A} \subseteq \mathcal{P}(\Omega)$ is called a $\sigma$-algebra on $\Omega$ if:

- $\Omega \in \mathcal{A}$,
- $A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A}$,
- $A_1, A_2, \ldots \in \mathcal{A} \Rightarrow \bigcup_{n=1}^{\infty} A_n \in \mathcal{A}$.

Elements of $A$ are called measurable sets. The tuple $(\Omega, A)$ is called a measurable space.

A $\sigma$-algebra is designed to assign a measure to an observed event.

### Remark

The properties of a $\sigma$-algebra have the following interpretations in the context of modeling a random experiment (i.e., the process by which an observation is made):

- We should be able to observe that an experiment has taken place,
- If the occurrence of an event is observable, we should also be able to observe the case that the event has not occurred,
- If the occurrence of a countable sequence of events is observable，we should also be able toobserve that one of these events has occurred. This translates to a logical OR relationship between events.

### Example (Trivial $\sigma$-algebras)

The set $\mathcal{A}_1 = \{\emptyset, \Omega\}$ and the power set $\mathcal{A}_2 = \mathcal{P}(\Omega)$ are $\sigma$-algebras.

### Example (Dice)

As stated above the space of elementary events $\Omega$ of a dice roll is given by

$$ \Omega = \{1, 2, 3, 4, 5, 6\}.$$

If the number rolled is observable the $\sigma$-algebra has the following form

$$\mathcal{A}_1 = \{\emptyset, \{1\}, \ldots, \{6\}, \{1, 2, 3\}, \{5, 6\}, \{1, 2, 3, \ldots\}, \Omega\} = \mathcal{P}(\Omega).$$

If only the parity of the rolled number is observable, i.e., odd or even, the $\sigma$-algebra has the following form

$$\mathcal{A}_2 = \left\{ \emptyset, \underbrace{\{1, 3, 5\}}_{\text{odd}}, \underbrace{\{2, 4, 6\}}_{\text{even}}, \Omega \right\}
.$$

The ability to measure occurring events (or sets of elementary events) contained in the $\sigma$-algebra has been ensured. The next step is to assign them a value (e.g., a probability). To be in accordance with the natural understanding of the behavior of probabilities, the mapping from the $\sigma$-algebra to the reals should satisfy certain properties, which are collected in the following definition of a measure.

### Definition (Probability Measure)

Let $A$ be a $\sigma$-Algebra. A map $\mu : A \to [0, \infty)$ is called a measure on $A$ if

- $\mu(\emptyset) = 0$,
- for pairwise disjoint sets $A_1, A_2, \ldots \in A$, it holds that

  $\mu\left(\bigcup_{n=1}^{\infty} A_n\right) = \sum_{n=1}^{\infty} \mu(A_n)$.

A measure is called *finite* if $\mu(\Omega) < \infty$. A measure is called *probability measure* if $\mu(\Omega) = 1$. Probability measures are denoted by $\mathbb{P}$.

### Remark

For a probability measure $\mathbb{P}$ on a measurable space $(\Omega, A)$, it holds that

$$\mathbb{P}(A) \in [0, 1], \quad \forall A \in A.$$

This is based on the second defining property of measure and the property of non-negativity.

### Remark

It is necessary to assume disjointedness in the second property of the definition: For $A_1 = \{1, 2\}$ (i.e., rolling a 1 or a 2 in a dice toss) and $A_2 = \{2, 3\}$, it holds that

$$\mathbb{P}(\{1,2\}) = \frac{1}{3} and \mathbb{P}(\{2,3\}) = \frac{1}{3},$$

but

$$\mathbb{P}(\{1,2\} \cup \{2,3\}) = \mathbb{P}(\{1,2,3\}) = \frac{1}{2} \neq \frac{1}{3} + \frac{1}{3} = \mathbb{P}(\{1,2\}) + \mathbb{P}(\{2,3\}).$$

This can be fixed by subtracting the measure of the intersection of the sets.

### Definition (Probability space)

Let $\Omega$ be a set of elementary events, $\mathcal{A}$ be a $\sigma$-algebra on $\Omega$ and $\mathbb{P}$ a probability measure on $\mathcal{A}$. The tuple $(\Omega, \mathcal{A}, \mathbb{P})$ is called probability space. Every $A \in \mathcal{A}$ is called event. For $A \in \mathcal{A}$, $\mathbb{P}(A)$ is called as the probability of $A$.

## Probability theory and random variables

For continuous probability spaces, the following theoretical groundwork is necessary.

### Remark (Existence of measures)

Strictly, to ensure that a measure exists on sample spaces defined on the real numbers (i.e., if $\Omega = \mathbb{R}$), the Borel $\sigma$-algebra $\mathcal{B}(\mathbb{R})$ is introduced (out of the scope of this lecture). The exact content of the Borel $\sigma$-algebra is difficult to grasp. In simple words, $\mathcal{B}(\mathbb{R})$ contains all open, closed and compact intervals and countable unions and intersections of those - so all sets that are interesting.

## Definition(Generated $\sigma$-algebra)

Let $\Omega$ be a set of elementary events and $\varepsilon \subseteq \mathcal{P}(\Omega)$. Then, the $\sigma$-algebra generated by $\varepsilon$ is defined as:

$$
\sigma(\varepsilon) = \bigcap_{\varepsilon \subset C, C \text{ is a }\sigma\text{-algebra}} C
$$

This is called the $\sigma$-algebra generated by $\varepsilon$. The set $\varepsilon$ is called the generating set of $\sigma(\varepsilon)$.

### Remark

The generating set is not unique.

### Definition (Borel $\sigma$-algebra)

Let $\Omega = \mathbb{R}$ and $\varepsilon = \{(-\infty, a] \mid a \in \mathbb{R}\}$, the set of all intervals. Then, the $\sigma$-algebra

$$\mathcal{B}(\mathbb{R}) = \sigma(\varepsilon)$$

is called Borel $\sigma$-algebra.

To always work with numbers, rather than 'abstract' events (e.g., 'heads' or 'tails'), the concept of a random variable is introduced next. A random variable maps the set of events to the reals and allows one to establish a more familiar object - a distribution function. These real functions describe where and how much randomness is assigned by the corresponding measures and are fully informative about the nature of a measure on the reals. Two important examples (which will also be the main focus of this lecture) are discrete and absolute continuous distributions.

### Remark

To make the transition to the real numbers consistent on a theoretical level, the following ideas are introduced:

- Sets in the Borel-$\sigma$-algebra should be assigned the probability of their preimage under the mapping of the random variable (push-forward),
- Every set in the Borel-$\sigma$-algebra should have a measurable preimage (measurable map).

### Definition (Measurable map)

Let $(\Omega, \mathcal{A})$, $(\Omega', \mathcal{A}')$ be two measurable spaces. A map $f: \Omega \rightarrow \Omega'$ is called $(\mathcal{A}, \mathcal{A}')$-measurable if all preimages of the measurable sets are measurable, i.e.,

$$A' \in \mathcal{A}' \implies f^{-1}(A') \in \mathcal{A}$$

### Example (Measurable maps)

The following two examples are measurable:

- Continuous maps $f: \mathbb{R} \rightarrow \mathbb{R}$,
- Indicator maps $f_A: \mathbb{R} \rightarrow \mathbb{R}, x \mapsto 1_A(x)$.

### Remark

If the respective $\sigma$-algebras match, the sum, product, and composition of two measurable functions is again a measurable function. So are supremum, infimum, lim sup, and lim inf of a sequence of measurable functions. Hence, the same will hold for random variables.

### Theorem (Push-forward)

Let $(\Omega, \mathcal{A})$, $(\Omega', \mathcal{A}')$ be two measurable spaces, $f : \Omega \to \Omega'$ be measurable and $\mu$ a measure on $\mathcal{A}$. Then, it holds that:

$$
\mu_f(B) := \mu(f^{-1}(B)), \quad B \in \mathcal{A}'
$$

is a measure on $\mathcal{A}'$. $This measure is called *push-forward* of $f$.

### Definition (Random variable)

Let $(\Omega, A)$ be a measurable space. A map $X : \Omega \to \mathbb{R}$ is called a random variable if it is $(A, \mathcal{B}(\mathbb{R}))$-measurable. For a fixed $\omega \in \Omega$, the value $X(\omega)$ is called sample of $X$.

### Remark

A random variable may take on as many values as there are events. In theory, the random variable can map to any measurable space, e.g., $\mathbb{R}^n$ or even more abstract spaces, equipped with a suitable $\sigma$-algebra and measure on each space. Given that we defined random variables on $\mathbb{R}$, the next section will focus on probability measures defined on $\mathbb{R}$. For such measures, one can define concrete concepts and properties, such as cumulative distribution functions, expected values, and higher moments.
