# Amount of Information
## How to quantify the amount of Information?
Assume $I(x)$ is the quantification function of event $x$ with probabilty $p(x)$. It should have follow properties:

- if the event with small probability occurs, the amount of information is large;
- if the event with large probability occurs, the amount of information is small;
- When $p(x)$ = 1, $I(x)$ should be 0;
- When $p(x)$ =0, $I(x)$ should be $+\infty$;
- Amount of information of independent events can be summed.

It is not difficult to deduce that the only possible formulas for quantifying the amount of information that meet these requirements are logarithmic functions
$$I(x)=log_b(P(x)),$$
Usually, $b$ is 2.
