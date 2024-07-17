# Amount of Information
## How to quantify the amount of Information?
Assume $I(x)$ is the quantification function of event $x$ with probabilty $p(x)$. It should have follow properties:

- if the event with small probability occurs, the amount of information is large;
- if the event with large probability occurs, the amount of information is small;
- When $p(x)$ = 1, $I(x)$ should be 0;
- When $p(x)$ =0, $I(x)$ should be $+\infty$;
- Amount of information of independent events can be summed.

It is not difficult to deduce that the only possible formulas for quantifying the amount of information that meet these requirements are logarithmic functions
$$I(x)=-log_b(P(x)).$$
Usually, $b$ is 2.
## Shannon Entropy
Formal defination: Expected amount of information of a probability distribution. It is also a measurement of uncertainty.

$$H(p)=\sum p_iI_i=-\sum p_ilog_2(p_i)$$

e.g. an uneven coin with $p(0)=0.2, p(1)=0.8$,
$$H(p)=-0.2\times log_20.2-0.8log_20.8=0.72$$