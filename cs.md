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

- [1. Gaussian integral](#1-gaussian-integral)
- [2. Characteristic function](#2-characteristic-function)
- [3. Multidimensional Gaussian integral](#3-multidimensional-gaussian-integral)
- [4. Central limit theorem](#4-central-limit-theorem)
- [5. Laplace's method](#5-laplaces-method)
- [6. Stirling's formula](#6-stirlings-formula)
- [7. L-p norm](#7-l-p-norm)
- [Distributions](#distributions)

## 1. Gaussian integral

$$ \tag{1} \int_{-\infty}^{+\infty} e^{-\frac{ax^2}{2}}dx = \sqrt{\frac{2\pi}{a}} \qquad a>0 $$

$$ \tag{2-3} \int_{-\infty}^{+\infty} e^{-\frac{ax^2}{2}+bx}dx = \sqrt{\frac{2\pi}{a}}e^{\frac{b^2}{2a}} \qquad a>0, b\in\mathbb{{C}} $$

<!-- 

$n$-dimension

 -->

## 2. Characteristic function

Given a probability density function $p(x)$ we can calculate the characteristic function

$$ \tag{4} \varphi(k) = \langle e^{ikx} \rangle \equiv \int e^{ikx}p(x)\ dx $$ 

and the $n$-th moment, that is given by the $n$-th derivative of the characteristic function

$$ \tag{5} \langle x^n \rangle \equiv \int x^n p(x)\ dx = (-i)^n \frac{d^n \varphi}{d k^n}\bigg|_{k=0}$$

Characteristic function of a Gaussian distribution with variance $\sigma^2$

$$ \tag{6} \int_{-\infty}^{+\infty} \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{x^2}{2\sigma^2}}\ e^{ikx}\ dx = e^{-\frac{\sigma^2 k^2}{2}}$$

$n$-th moment of an (unnomralized) Gaussian distribution

$$ \tag{7} \int_{-\infty}^{+\infty} x^n e^{-\frac{ax^2}{2}}\ dx = \frac{\sqrt{2\pi}(n-1)!!}{a^{(n+1)/2}} \qquad a>0, n\ \text{even} $$

## 3. Multidimensional Gaussian integral

$$ \tag{8} Z(A) \equiv \int_{\mathbb{R}^n} \exp\left[{-\frac{1}{2}\vec{x}^T A \vec{x} } \right] dx^n = \frac{(2\pi)^{n/2}}{\sqrt{\det A}} $$

$$ \tag{9-10} Z(A,\vec{b}) \equiv \int_{\mathbb{{R}^n}} \exp\left[{-\frac{1}{2}\vec{x}^T A \vec{x} + \vec{x}^T \vec{b}} \right] dx^n = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}\exp\left( \frac{1}{2}\vec{b}^T A^{-1} \vec{b} \right) $$

Characteristic function of a multivariate Gaussian distribution

$$ \tag{11} \varphi(\vec{k}) \equiv \int_{\mathbb{R}^n} p(\vec{x}) e^{i\vec{k}\cdot\vec{x}}\ dx^n = \exp{\left[ -\frac{ \vec{k}^T A^{-1} \vec{k} }{2} \right]}$$

General $s$-point correlation function

$$ \tag{12} \langle \underbrace{x_i x_j \dots x_l}_{\text{s times}} \rangle \equiv \int_{\mathbb{R}^n} x_i x_j \dots x_l\ p(\vec{x})\ dx^n = (-i)^s \ \underbrace{ \frac{\partial}{\partial k_i} \frac{\partial}{\partial k_i} \dots \frac{\partial}{\partial k_i} }_{\text{s times}} \varphi(\vec{k}) $$

2-point correlation function for the Gaussian pdf

$$ \tag{13} \langle x_i x_j \rangle = (-i)^2 \frac{\partial}{\partial k_i} \frac{\partial}{\partial k_j} \varphi(\vec{k})\bigg|_{\vec{k}=\vec{0}} = (A^{-1})_{ij} $$

Wick's theorem

$$ \tag{14} \langle \underbrace{x_i x_j \dots x_l}_{\text{s times}} \rangle = \sum_{\mathcal{P}} (A^{-1})_{i_p j_p} \dots (A^{-1})_{n_p m_p} \qquad \text{\# of pairings }= (s-1)!! $$

## 4. Central limit theorem

The distribution of the sum of two independent and identically distributed (iid) random variables $x_1,x_2 \sim q(x)$ is given by the convolution

$$ \tag{15} x = x_1 + x_2 \qquad\qquad p(x) = \int q(x-y)q(y)\ dy $$

If the characteristic function of $q(x)$ is $\varphi_1(k)$, the characteristic function of $p(x)$ is

$$ \tag{16} \varphi(x) = \left[\varphi_1(k) \right]^2 $$



## 5. Laplace's method

Let us consider integral of the following form

$$ \tag{21} I(\lambda) = \int_{x_1}^{x_2} g(x) e^{\lambda f(x)} dx \qquad \lambda \in \mathbb{R}$$

If we assume the existence of a maximum $x_0\in [x_1,x_2]$ and that $g(x_0)\ne 0$, have the following cases:

a) max is an interior point. $x_0 \in (x_1,x_2)$ and $f'(x_0)=0, f''(x_0)<0$

$$ \tag{22} I(\lambda) \cong g(x_0)\frac{e^{\lambda f(x_0)}}{\sqrt{\lambda|f''(x_0)|}} \sqrt{2\pi} \qquad \lambda \to \infty $$

b) max is a flat endpoint. $x_1=x_0$ or $x_2=x_0$ and $f'(x_0)=0, f''(x_0)<0$

$$ \tag{23} I(\lambda) \cong g(x_0)\frac{e^{\lambda f(x_0)}}{\sqrt{\lambda|f''(x_0)|}} \frac{\sqrt{2\pi}}{2} \qquad \lambda \to \infty $$

c) max is a (not flat) endpoint. $x_1=x_0$ or $x_2=x_0$ and $f'(x_0)\ne 0$

$$\tag{24} I(\lambda) \cong g(x_0)\frac{e^{\lambda f(x_0)}}{ \lambda|f'(x_0)|} \qquad  \lambda \to \infty $$

## 6. Stirling's formula

Let us consider the Gamma function

$$ \tag{25} \Gamma(\lambda) = \int_0^{\infty} x^{\lambda-1} e^{-x}\ dx \qquad \lambda > 0 $$

Thanks to the Laplace's method we can approximate the factorial as 

$$ \tag{26} \lambda! = \Gamma(\lambda + 1) \cong \lambda^{\lambda+1} e^{-\lambda} \sqrt{\frac{2\pi}{\lambda}} \qquad \lambda \to \infty$$

## 7. L-p norm

$$ ||g||_p \equiv \left( \int_a^b |g(t)|^p\ dt\right)^p = \max_{t\in [a,b]} |g(t)| \left( 1 - \frac{\ln p}{2p} + \mathcal{O}\left(1/p\right) \right) \qquad p\to\infty$$

## Distributions