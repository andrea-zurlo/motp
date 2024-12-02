<link rel="stylesheet" type="text/css" href="https://tikzjax.com/v1/fonts.css">
<script src="https://tikzjax.com/v1/tikzjax.js"></script>

<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
    tex2jax: {
        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
        inlineMath: [['$','$']]
    }
    });
</script>
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>


# Exercises – Models of Theoretical Physics

- [Exercises – Models of Theoretical Physics](#exercises--models-of-theoretical-physics)
  - [1. Mathematical tools](#1-mathematical-tools)
    - [1. The uniform distribution](#1-the-uniform-distribution)
    - [2. The gamma distribution](#2-the-gamma-distribution)
    - [3. Bivariate Gaussian and correlation functions](#3-bivariate-gaussian-and-correlation-functions)
    - [4. Bivariate Gaussian with marginalization](#4-bivariate-gaussian-with-marginalization)
    - [5. Joint distribution of the sum](#5-joint-distribution-of-the-sum)
    - [6. Joint distribution of the product](#6-joint-distribution-of-the-product)
    - [7. Sum of n indpendent random variables](#7-sum-of-n-indpendent-random-variables)
    - [8. Central limit theorem](#8-central-limit-theorem)
    - [9. Laplace's method](#9-laplaces-method)
    - [10. Laplace's method on modified Bessel function](#10-laplaces-method-on-modified-bessel-function)
    - [11. Correlation function](#11-correlation-function)
    - [12. Stirling's formula](#12-stirlings-formula)
    - [13. An integral related to the Stirling's formula](#13-an-integral-related-to-the-stirlings-formula)
    - [14. Integrals](#14-integrals)
    - [15. Integral](#15-integral)
  - [2. Reaction dynamics](#2-reaction-dynamics)
    - [1. Binary reaction](#1-binary-reaction)
    - [2. Binary reversible reaction](#2-binary-reversible-reaction)
    - [3. Synthesis of water](#3-synthesis-of-water)
    - [4. Lotka-Volterra](#4-lotka-volterra)
    - [5. Michaelis-Menten (enzymatic reaction)](#5-michaelis-menten-enzymatic-reaction)
    - [6. Brusselator](#6-brusselator)
    - [7. Gene expression](#7-gene-expression)
    - [8. SIER model](#8-sier-model)

---

## 1. Mathematical tools

### 1. The uniform distribution

Let $x$ be a random variable drawn from $U([a,b])$, $a,b\in\mathbb{R}$, $b>a$. The pdf can be expressed as

$$ p(x)=\frac{1}{b-a} $$ 

Calculate the characteristic function of $p(x)$.
 
**Solution.**

---
### 2. The gamma distribution

Let $x$ be a random variable drawn from a distribution

$$ q(x|\alpha,\beta) = \frac{\beta^\alpha}{\Gamma(\alpha)} x^{\alpha-1} e^{-\beta x}, \qquad x\in[0,+\infty), \alpha, \beta\in\mathbb{R} $$

where

$$ \Gamma(z) = \int_0^{+\infty} t^{z-1} e^{-t} dt \qquad z\in\mathbb{R}, \mathcal{Re}(z)>0 $$

Requests:
1. check that $q$ is properly normalized;
2. calculate the characteristic function $\varphi(k)$ of $q$;
3. check that $\varphi(0)=1$.

**Solution.**

---

### 3. Bivariate Gaussian and correlation functions

Consider the following bivariate Gaussian distribution

$$ p(x_1, x_2) = \exp{\left[-\frac{3}{2}(x_1^2 + x_2^2) + x_1 x_2 \right]} $$

find the symmetric matrix $A$ such that the exponent can be expressed as $-\frac{1}{2} \vec{x}^T A \vec{x}$. Compute the integral and the following correlation functions: $\langle x_1^2 \rangle, \langle x_1 x_2 \rangle$.

**Solution.**

---
### 4. Bivariate Gaussian with marginalization

Consider the following bivariate Gaussian distribution

$$ p(x,y) = \frac{\sqrt{\det A}}{2\pi} \exp\left[ -\frac{1}{2} \left( a_{11}x^2 + 2a_{12}xy + a_{22}y^2 \right) \right] $$

where $a_{11},a_{22}>0, a_{12}=a_{21}$. Show that $p$ is normalized to 1 and that the marginalized distribution

$$ q(x) = \int_{\mathbb{R}} p(x,y)dy $$

is still a Gaussian pdf. Find the variance of the r.v. distributed as $q(x)$.

**Solution.**

---

### 5. Joint distribution of the sum

Calculate the distribution of $x=x_1 + x_2$ if $x_1, x_2$ are iid drawn from:
1. a uniform distribution $\mathcal{U}([0,1])$;
2. a Gaussian distribution $\mathcal{N}_x(\mu,\sigma)$;
3. an exponential distribution $q(x) = \lambda e^{-\lambda x}$.

---

### 6. Joint distribution of the product

Calculate the distribution of $x=x_1 x_2$ when $x_1$, $x_2$ are positive and iid.

---

### 7. Sum of n indpendent random variables

Calculate the characteristic function of $x=x_1+x_2+\dots+x_n$ when $x_i$ are independent but not identically distributed.

---

### 8. Central limit theorem

Show that

$$ \sum_{i=1}^{n} x_i \sim \mathcal{N}(n\mu, n\sigma^2); \qquad \frac{1}{n}\sum_{i=1}^{n} x_i \sim \mathcal{N} \left(\mu,\frac{\sigma^2}{n} \right) $$

---

### 9. Laplace's method

Show that a better approximation of $I(\lambda)$ as $\lambda\to\infty$ is given by

$$ I(\lambda) = e^{\lambda f(x_0)} \sqrt{ \frac{2\pi}{\lambda\lvert{f''(x_0)}\rvert } } \left( g(x_0) + \frac{c}{\lambda} \right) $$

where $c$ is a constant that depends on the derivatives of $f(x)$ up to the 4th order (at $x=x_0$) and $g(x_0), g'(x_0)$.

---

### 10. Laplace's method on modified Bessel function

Consider the modified Bessel function

$$ K_\nu(x) = \int_0^{\infty} e^{-x \cosh t} \cosh (\nu t) dt $$

show that

$$ K_\nu(x) \cong \sqrt{ \frac{\pi}{2x} } e^{-x} \left( 1 + \frac{c(\nu)}{x} + \dots \right), \qquad c(\nu) = \frac{2\nu^2 - 1}{8} $$

---

### 11. Correlation function

Let $x_1, x_2$ be two independent random variables with

$$ \langle x_i \rangle = 0,\ \langle x_i^2 \rangle = 0 \qquad i=1,2; \qquad \langle x_1 x_2 \rangle = 0 \qquad \text{(uncorrelated)} $$

Use $x_1, x_2$ to define two random variable $y_1, y_2$ that are correlated with

$$ \langle y_1 y_2 \rangle = \rho; \qquad \langle y_1^2 \rangle = \sigma_1^2, \langle y_2^2 \rangle = \sigma_2^2 $$

---

### 12. Stirling's formula

Show that a better estimate of the Stirling's formula si given by

$$ \lambda !\simeq \lambda^{\lambda+1}e^{-\lambda}\sqrt{\frac{2\pi}{\lambda}} \left( 1 + \frac{1}{12\lambda} \right) $$

---

### 13. An integral related to the Stirling's formula

Show that at leading order 

$$ \int_0^\infty e^{-\lambda t} e^{-1/t} dt = \frac{\sqrt{\pi}e^{-2\sqrt{\lambda}}}{\lambda^{3/4}} \qquad \text{as}\ \lambda \to \infty $$

---

### 14. Integrals

$$\begin{align*} \text{a)} &\quad \int_{-2}^{0} e^t e^{ \lambda (3t^3 + 2t^3)} dt = e^{\lambda - 1} \sqrt{\frac{\pi}{3\lambda}} \\
\\
\text{b)} &\quad \int_{0}^{1} e^t e^{ \lambda (3t^3 + 2t^3)} dt \simeq \frac{e^{5\lambda + 1}}{12 \lambda} \\
\\
\text{c)} &\quad \int_{0}^{1} \sqrt{t+1} e^{\lambda(2t - t^2)} dt \simeq e^{\lambda - 1} \sqrt{\frac{\pi}{2\lambda}} \\
\\
\text{d)} &\quad \int_{-1}^{2} e^{ \lambda (t^3 - 1)}(1+t^2) dt \simeq \frac{5e^{6\lambda}}{11\lambda} 
\end{align*}$$ 

---

### 15. Integral

Consider the integral

$$ G(\lambda) = \int_{x_1}^{x_2} g(t) e^{\lambda f(t)} dt $$

where $f$ is smooth in $[x_1,x_2]$ and has the shape given by

<script type="text/tikz">


\tikzset{every picture/.style={line width=0.75pt}} %set default line width to 0.75pt        

\begin{tikzpicture}[x=0.75pt,y=0.75pt,yscale=-1,xscale=1]
%uncomment if require: \path (0,238); %set diagram left start at 0, and has height of 238

%Straight Lines [id:da23526362934300482] 
\draw    (14.5,187) -- (278,187) ;
\draw [shift={(280,187)}, rotate = 180] [color={rgb, 255:red, 0; green, 0; blue, 0 }  ][line width=0.75]    (10.93,-3.29) .. controls (6.95,-1.4) and (3.31,-0.3) .. (0,0) .. controls (3.31,0.3) and (6.95,1.4) .. (10.93,3.29)   ;
%Straight Lines [id:da507394361412951] 
\draw    (34,213.5) -- (34,15.5) ;
\draw [shift={(34,13.5)}, rotate = 90] [color={rgb, 255:red, 0; green, 0; blue, 0 }  ][line width=0.75]    (10.93,-3.29) .. controls (6.95,-1.4) and (3.31,-0.3) .. (0,0) .. controls (3.31,0.3) and (6.95,1.4) .. (10.93,3.29)   ;
%Curve Lines [id:da38177544585289147] 
\draw [color={rgb, 255:red, 74; green, 144; blue, 226 }  ,draw opacity=1 ][line width=1.5]    (49.5,212) .. controls (71.5,45.5) and (102,59.5) .. (136,124) .. controls (170,188.5) and (196.5,190) .. (220.5,14.5) ;
%Straight Lines [id:da2561674175737174] 
\draw    (16.5,78.5) -- (279.5,78.5) ;
%Straight Lines [id:da45934936488879585] 
\draw    (211,18.5) -- (211,213) ;
%Straight Lines [id:da15160053107712046] 
\draw    (61,18) -- (61,212.5) ;
%Straight Lines [id:da7142987422529892] 
\draw    (95.5,79) -- (95.5,186.5) ;

% Text Node
\draw (63,185.4) node [anchor=north west][inner sep=0.75pt]    {$x_{1}$};
% Text Node
\draw (213,186.4) node [anchor=north west][inner sep=0.75pt]    {$x_{2}$};
% Text Node
\draw (95,187.4) node [anchor=north west][inner sep=0.75pt]    {$x_{0}$};


\end{tikzpicture}
</script>

what is the leading behaviour of $G(\lambda)$ as $\lambda\to\infty$?

## 2. Reaction dynamics

### 1. Binary reaction

### 2. Binary reversible reaction

### 3. Synthesis of water

### 4. Lotka-Volterra

### 5. Michaelis-Menten (enzymatic reaction)

### 6. Brusselator

### 7. Gene expression

### 8. SIER model
