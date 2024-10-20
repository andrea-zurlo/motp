- [Arguments](#arguments)
  - [1. Gaussian integrals](#1-gaussian-integrals)
  - [2. Characteristic function](#2-characteristic-function)
  - [3. Correlation function](#3-correlation-function)
  - [4. Convergence of random variables](#4-convergence-of-random-variables)
  - [5. Laplace's method](#5-laplaces-method)
  - [6. Stirling's formula](#6-stirlings-formula)
  - [7. L-p norm](#7-l-p-norm)
- [Distributions](#distributions)


## Arguments

### 1. Gaussian integrals

One dimension

$$ \int_{-\infty}^{+\infty} e^{-\frac{ax^2}{2}+bx}dx = \sqrt{\frac{2\pi}{a}}e^{\frac{b^2}{2a}} \qquad a>0, b\in\mathbb{{C}} $$

$$ \int_{-\infty}^{+\infty} x^n e^{-\frac{ax^2}{2}}dx = \sqrt{2\pi}\frac{(n-1)!!}{a^{(n+1)/2}} \qquad a>0, n\ \text{even} $$

$n$-dimension

$$ Z(A,\vec{b}) = \int_{\mathbb{{R}^n}} \exp\left[{-\frac{1}{2}\vec{x}^T A \vec{x} + \vec{x}^T \vec{b}} \right] dx^n = \frac{(2\pi)^{n/2}}{\sqrt{\det A}}\exp\left( \frac{1}{2}\vec{b}^T A^{-1} \vec{b} \right) $$

### 2. Characteristic function

### 3. Correlation function

General s-point

$$ \langle \underbrace{x_i x_j \dots x_l}_{\text{s times}} \rangle = (-i)^s \ \underbrace{ \frac{\partial}{\partial k_i} \frac{\partial}{\partial k_i} \dots \frac{\partial}{\partial k_i} }_{\text{s times}} \varphi(\vec{k}) $$

Gaussian 2-point with matrix of coefficients $A$

$$ \langle x_i x_j \rangle = (-i)^2 \frac{\partial}{\partial k_i} \frac{\partial}{\partial k_j} \varphi(\vec{k})\bigg|_{\vec{k}=\vec{0}} = (A^{-1})_{ij} $$

### 4. Convergence of random variables

### 5. Laplace's method

$$ I(\lambda) = \int_{x_1}^{x_2} g(x) e^{\lambda f(x)} dx \qquad \lambda \to \infty $$

i) max is an interior point

$$ I(\lambda) \cong g(x_0)\frac{e^{\lambda f(x_0)}}{\sqrt{\lambda|f''(x_0)|}} \sqrt{2\pi} $$

ii) max is a flat endpoint

$$ I(\lambda) \cong g(x_0)\frac{e^{\lambda f(x_0)}}{\sqrt{\lambda|f''(x_0)|}} \frac{\sqrt{2\pi}}{2} $$

iii) max is an endpoint not flat

$$ I(\lambda) \cong g(x_0)\frac{e^{\lambda f(x_0)}}{ \lambda|f'(x_0)|}$$

### 6. Stirling's formula

### 7. L-p norm


## Distributions