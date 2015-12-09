---
layout: default
---

## Cone calculation steps

- get $$\mu_{Geo}(R)$$ and $$\sigma(r^{\log})$$
- transform $$\mu_{Geo}(R)$$ to $$\mu(R)$$ under assumption of
  log-normality
- transform $$\mu(R)$$ to $$\mu(r^{\log})$$
- get quantiles for $$r_{n}^{\log}=\sum_{i=1}^{n}r_{i}^{\log}\sim
  \mathcal{N}$$
- translate quantiles to quantiles of $$R$$ through assumption of
  log-normality

## Discrete, gross and logarithmic return formulas

For gross return *R*, discrete percentage return $$r^{disc,\%}$$ and
logarithmic percentage return $$r^{\log,\%}$$ the following
transformation formulas hold.

#### Logarithmic percentage returns and gross returns

$$\begin{aligned}
R&=\exp\left( \frac{r^{\log,\%}}{100} \right)\\
r^{\log,\%}&=100\log(R)
\end{aligned}$$

#### Gross returns and discrete percentage returns

$$\begin{aligned}
R&=1+\frac{r^{disc,\%}}{100}\\
r^{disc,\%}&=100(R-1)
\end{aligned}$$

#### Logarithmic and discrete percentage returns

$$\begin{aligned}
r^{\log,\%}&=100\log\left( 1+\frac{r^{disc,\%}}{100} \right)\\
r^{disc,\%}&=100\left( \exp\left( \frac{r^{\log,\%}}{100} \right) -1 \right) 
\end{aligned}$$
 

## Geometric mean

The geometric mean of a sample is given by

$$
\mu_{Geo}(R)=\left( \prod_{i=1}^{n}R_{i} \right)^{\frac{1}{n}}
$$

Hence, if two assets have the same geometric mean for gross returns
they will have the exact same percentage price increase. This,
however, does neither hold for equal arithmetic gross returns nor for
arithmetic discrete returns.

However, matching arithmetic logarithmic means for two assets will
simultaneously also match geometric means.

$$
\begin{aligned}
\hat{\mu}_{Geo}(R)&=\left( \prod_{i=1}^{n}R_{i} \right)^{\frac{1}{n}}\\
&=\exp\left( \frac{1}{n}\sum_{i=1}^{n} \log(R_{i})\right) \\
&=\exp\left( \frac{1}{n}\sum_{i=1}^{n} r^{\log}_{i}\right)\\
&=\exp\left( \hat{\mu}(r^{\log})\right)
\end{aligned}
$$

Alternatively, if geometric means are matched instead of arithmetic
logarithmic means, geometric means still need to be converted to
arithmetic means at some point. This could be done by assuming
log-normally distributed returns, and will be shown in the next two
parts. 

### Special case: log-normal distribution

The geometric mean of a log-normally distributed random variable

$$
Y:=\exp(X)\text{, with } X\sim \mathcal{N}(\mu,\sigma^{2})
$$

is given by 

$$
\mu_{Geo}(Y)=\exp(\mu(Y))
$$

### Usage for returns

Given that $$r^{\log}\sim \mathcal{N}(\mu, \sigma^{2})$$, gross return
*R* follows a log-normal distribution:

$$
R=\exp(r^{\log})
$$

Hence, the formulas for geometric and arithmetic mean conversions
apply for gross returns *R*:

$$\begin{aligned}
\mu_{Geo}(R)&=\exp(\mu(R))&\Leftrightarrow \\
\mu(R)&=\log(\mu_{Geo}(R))
\end{aligned}$$


## Converting log, discrete and gross return moments

Although 

$$
\mathbb{E}[aX+b]=a \mathbb{E}[X]+b
$$

there is no such easy formula for more general transformations:

$$
\mathbb{E}[g(X)]\neq g(\mathbb{E}[X])
$$

### Converting return moments

Applied to returns this means that it is generally not possible to
translate a known value for $$\mu(R)$$ into $$\mu(r^{\log,\%})$$:

$$
\mu(r^{\log,\%})=\mu(100\log(R))\neq g(\mu(R)).
$$

One would need to have the distribution of *R*, apply the
transformation theorem and integrate over the newly derived density
function. The same reasoning also applies to standard deviations:

$$
\sigma(r^{\log,\%})=\sigma(100\log(R))\neq g(\sigma(R))
$$

### Special case: log-normal

For $$X\sim \mathcal{N}(\mu,\sigma^{2})$$, random variable 

$$
Y:=\exp(X)
$$

is log-normally distributed, and the moments of *Y* can be calculated
via

$$
\mu(Y)=\exp\left(\mu(X)+\frac{\sigma(X)^{2}}{2}\right)
$$

$$
\sigma^{2}(Y)=\left(\exp(\sigma(X)^{2})-1\right)\exp(2\mu(X)+\sigma(X)^{2})
$$


### Special case: log-normally distributed returns *R*

For the case of returns, this means: if
$$r^{\log,\%}\sim \mathcal{N}$$ (and hence also $$r^{\log}\sim \mathcal{N}$$),
*R* follows a log-normal distribution: 

$$
R=\exp\left(\frac{r^{\log,\%}}{100}\right) \text{ with } r^{\log,\%}\sim \mathcal{N}
$$

As a consequence, moments of $$r^{\log,\%}$$ can easily be translated
into moments of *R* and vice versa. And in turn, as *R* is linear in
$$r^{disc,\%}$$, $$\left(R=1+\frac{r^{disc,\%}}{100}\right)$$, moments
can also be translated between $$r^{\log,\%}$$ and $$r^{disc,\%}$$.

### Applied to cone calculation

With given values $$\sigma(r^{\log})$$ and $$\mu(R)$$ we can get
$$\mu(r^{\log})$$: 

$$
\begin{aligned}
\mu(R)&=\exp\left(\mu(r^{\log})+\frac{\sigma(r^{\log})^{2}}{2}\right) &\Leftrightarrow \\
\log(\mu(R))&=\mu(r^{\log})+\frac{\sigma(r^{\log})^{2}}{2}&\Leftrightarrow\\
\log(\mu(R))-\frac{\sigma(r^{\log})^{2}}{2}&=\mu(r^{\log})
\end{aligned}
$$

## Square-root-of-time scaling

Message: although variance scaling follows square-root-of-time scaling
for the case of iid logarithmic returns, this does not necessarily
apply to quantiles as well. In order to be able to infer quantiles
also, we should need the assumption of normally distributed
logarithmic returns.

For independent variables we get:

$$
\mathbb{V}\left( \sum_{i=1}^{n}X_{i} \right) = n \mathbb{V}(X_{i})
$$

However, variances only translate into quantiles with an
distributional assumption. For example, for the case of normally
distributed variables $$X_{i}$$, $$\sum_{i=1}^{n}X_{i}\sim
\mathbb{N}$$, so that quantile *z* for confidence level $$\alpha$$ can
be obtained by

$$
z = \mu + \sigma\Phi^{-1}(\alpha)
$$

A similar formula also exists for variables following a Student's *t*
distribution. However, while 

$$
\sum_{i=1}^{n}X_{i}\sim \mathcal{N}\text{ for } X_{i}\sim \mathcal{N},
$$

the distribution is generally not maintained under summation:

$$
\sum_{i=1}^{n}X_{i}\nsim t\text{ for } X_{i}\sim t, 
$$

as the sum of iid random variables converges to the normal
distribution: 


$$
\sum_{i=1}^{n}X_{i}\rightarrow \mathcal{N}.
$$


## Discrete price quantiles under normally distributed log returns

With $$\alpha=0.95$$ we get the following quantiles for logarithmic
multi-period returns:

$$
z_{n} = n\mu - 1.959963\sqrt{n}\sigma
$$

### Translating quantiles to discrete returns

For a transformation 

$$
Y:=g(X)
$$

the cdf $$F_{Y}(z)$$ can be derived according to:

$$\begin{aligned}
F_{Y}(z)&= \mathbb{P}(Y\leq z)\\
&= \mathbb{P}(g(X)\leq z)\\
&= \mathbb{P}(X \leq g^{-1}(z))\\
&= F_{X}(g^{-1}(z))
\end{aligned}$$

From this we can derive the inverse cdf $$F_{Y}^{-1}$$ of *Y* as a
transformation of $$F_{X_{n}}^{-1}=z_{n}$$:

$$
\begin{aligned}
F^{-1}_{Y}(\alpha)&=\left( F_{X}(g^{-1}(\alpha)) \right)^{-1} \\
&=g\left( F_{X}^{-1}(\alpha) \right)\\
&=g\left( n\mu-\Phi^{-1}(\alpha)\sqrt{n}\sigma \right) \\
&=\exp\left( n\mu-\Phi^{-1}(\alpha)\sqrt{n}\sigma \right)
\end{aligned}
$$
