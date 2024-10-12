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

---

### 1. The uniform distribution

Let $x$ be a random variable drawn from $U([a,b])$, $a,b\in\mathbb{R}$, $b>a$. The pdf can be expressed as
$$ p(x)=\frac{1}{b-a} $$ 
Calculate the characteristic function of $p(x)$.
 
**Solution.** First we check the normalization

$$ \int_{a}^{b} p(x)dx = \int_{a}^{b} \frac{dx}{b-a} = \frac{x}{b-a}\bigg\rvert_{a}^{b} = 1 $$

We apply the definition of c.f.

$$ \varphi{(t)} \equiv \int_{a}^{b} e^{itx} p(x) dx = \int_{a}^{b} \frac{e^{itx}}{b-a} dx = \frac{e^{itx}}{it(b-a)}\bigg\rvert_{a}^{b} = \frac{e^{itb} - e^{ita}}{it(b-a)} $$

By Taylor expansion we can show that $\varphi(0)=1$

$$ \lim_{t\to 0} \varphi(t) = \lim_{t\to 0} \frac{e^{itb} - e^{ita}}{it(b-a)} = \lim_{t\to 0} \frac{1 + itb + o(itb) - (1 + itb + o(itb) ) }{it(b-a)} = $$
$$ = \lim_{t\to 0} \frac{itb - ita}{it(b-a)} = 1 $$

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

**Solution.** Considering the change of variable $\beta x = t$  

$$ \int_0^{+\infty} x^{\alpha-1} e^{-\beta x} dx = \int_0^{+\infty} \frac{t^{\alpha-1}}{\beta^{\alpha-1}} e^{-t} \frac{dt}{\beta} = \frac{1}{\beta^\alpha} \int_0^{+\infty} t^{\alpha -1} e^{-t} dt = \frac{\Gamma(\alpha)}{\beta^{\alpha}} $$

Characteristic function

$$ \varphi(k) = \langle e^{ikx} \rangle = \int_0^{+\infty} \frac{\beta^{\alpha}}{\Gamma(\alpha)} x^{\alpha - 1} e^{-\beta x} e^{ikx} dx = \frac{\beta^{\alpha}}{\Gamma(\alpha)} \int_0^{+\infty} x^{\alpha - 1} e^{-(\beta-ik) x} dx $$

change of variable $\beta - ik = s$

$$ \varphi(k) = \frac{\beta^{\alpha}}{\Gamma(\alpha)} \int_0^{+\infty} x^{\alpha - 1} e^{-s x} dx = \frac{\beta^{\alpha}}{\Gamma(\alpha)} \frac{\Gamma(\alpha)}{s^{\alpha}} = \frac{\beta^\alpha}{(\beta - ik)^\alpha} = \left(1 - i\frac{k}{\beta}\right)^{-\alpha} $$

finally 
$$ \varphi(0) = \left(1 - i\frac{0}{\beta}\right)^{-\alpha} = 1 $$

---

### 3. Bivariate Gaussian and correlation functions

Consider the following bivariate Gaussian distribution
$$ p(x_1, x_2) = \exp{\left[-\frac{3}{2}(x_1^2 + x_2^2) + x_1 x_2 \right]} $$
find the symmetric matrix $A$ such that the exponent can be expressed as $-\frac{1}{2} \vec{x}^T A \vec{x}$. Compute the integral and the following correlation functions: $\langle x_1^2 \rangle, \langle x_1 x_2 \rangle$.

**Solution.** It is easy to see that
$$ A = \begin{pmatrix} 
3 & -1 \\
-1 & 3
\end{pmatrix} $$
Considering the multivariate Gaussian integral

$$ \int_{\mathbb{R}^n} \exp{\left( -\frac{1}{2}\vec{x}^T A \vec{x} \right) } dx^n = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}$$

for $n=2$ we get

$$ \int_{\mathbb{R}} dx_1 \int_{\mathbb{R}} p(x_1,x_2)\ dx_2\ = \frac{2\pi}{\sqrt{8}} = \frac{\pi}{\sqrt{2}} $$

In order to calculate the correlation function we need $A^{-1}$

$$ \left(\begin{matrix}
3 & -1 \\
-1 & 3
\end{matrix}\ \Bigg\vert\ \begin{matrix}
1 & 0 \\
0 & 1
\end{matrix}\right) \sim 

\left(\begin{matrix}
1 & 0 \\
0 & 1
\end{matrix}\ \Bigg\vert\ \begin{matrix}
3/8 & 1/8 \\
1/8 & 3/8
\end{matrix}\right)$$

The general formula for a 2-point correlation function is $ \langle x_i x_j \rangle = (A^{-1})_{ij} $, thus we have

$$ \langle x_1^2 \rangle = \frac{3}{8} \qquad \qquad \langle x_1 x_2 \rangle = \frac{1}{8} $$

---
### 4. Bivariate Gaussian with marginalization

Consider the following bivariate Gaussian distribution
$$ p(x,y) = \frac{\sqrt{\det A}}{2\pi} \exp\left[ -\frac{1}{2} \left( a_{11}x^2 + 2a_{12}xy + a_{22}y^2 \right) \right] $$
where $a_{11},a_{22}>0, a_{12}=a_{21}$. Show that $p$ is normalized to 1 and that the marginalized distribution
$$ q(x) = \int_{\mathbb{R}} p(x,y)dy $$
is still a Gaussian pdf. Find the variance of the r.v. distributed as $q(x)$.

**Solution.** From the multivariate Gaussian integral

$$ \int_{\mathbb{R}^n} \exp\left(-\frac{1}{2} \vec{x}^T A \vec{x} \right) dx^n = \frac{(2\pi)^{n/2}}{\sqrt{\det A}} $$

We can define the matrix of the coefficients in order to get

$$ \det A = \begin{vmatrix}
a_{11} & a_{12} \\
a_{12} & a_{22}
\end{vmatrix} = a_{11}a_{22} - a_{12}^2 $$

we find that $p(x,y)$ is normalized to 1, since

$$ \int_{\mathbb{R}}dx \int_{\mathbb{R}} dy \exp\left[ -\frac{1}{2} \left( a_{11}x^2 + 2a_{12}xy + a_{22}y^2 \right) \right] = \frac{2\pi}{\sqrt{\det{A}}} $$

Now let us compute the marginalized distribution

$$ q(x) = \int_{\mathbb{R}} p(x,y)\ dy = \frac{\sqrt{\det A}}{2\pi} e^{ -\frac{1}{2}a_{11} x^2} \int_{-\infty}^{+\infty} \exp \left[-\frac{a_{22}}{2}y^2 - a_{12}xy \right] dy $$

here we can exploit the 1-dim Gaussian integral with $a=a_{22}$ and $b=-a_{12}x$, we get

$$ q(x) = \frac{\sqrt{\det A}}{2\pi} e^{ -\frac{1}{2}a_{11} x^2} \sqrt{\frac{2\pi}{a_{22}}}\exp\left[\frac{(-a_{12}x)^2}{2a_{22}}\right] = $$
$$ = \frac{1}{\sqrt{2\pi}} \sqrt{a_{11} - \frac{a_{12}^2}{a_{22}}}\exp\left[-\frac{1}{2} \left(a_{11} - \frac{a_{12}^2}{a_{22}} \right)x^2\right] = \frac{1}{\sqrt{2\pi}\sigma} e^{-\frac{x^2}{2\sigma^2}}$$

where we have defined the variance of the marginalized distribution as

$$ \frac{1}{\sigma^2} = \left(a_{11} - \frac{a_{12}^2}{a_{22}}\right) $$

proving that it is still a Gaussian pdf.

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
