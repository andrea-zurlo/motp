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
    - [1. Ito stochastic integral](#1-ito-stochastic-integral)
    - [2. Ito stoch integral 2](#2-ito-stoch-integral-2)
    - [3. Ito differential](#3-ito-differential)
    - [4. Log-normal distribution](#4-log-normal-distribution)
    - [5. Geometric Brownian motion](#5-geometric-brownian-motion)
    - [6. Ito formula for 2 variables](#6-ito-formula-for-2-variables)
    - [7. Generalized Ornstein-Uhlenbeck](#7-generalized-ornstein-uhlenbeck)
    - [8. Ornstein-Uhlenbeck variance from PDF](#8-ornstein-uhlenbeck-variance-from-pdf)
    - [9. Brownian particle with harmonic potential](#9-brownian-particle-with-harmonic-potential)
    - [10. Poisson process mean](#10-poisson-process-mean)
    - [11. Radioactive decay](#11-radioactive-decay)

---

### 1. Ito stochastic integral

Show that for $\sigma$ non-anticipating function

$$ \int_0^t \sigma(s) dB^2(s) = \int_0^t \sigma(s) ds $$

---

### 2. Ito stoch integral 2

Assume that the stochastic process $g(t)$ depends on the B.m. $B(s)$ for any $s<t$, so $g$ is non-anticipating. Show that

$$ \mathbb{E}\left[ \left( \int_0^t g(s)dB(s) \right)^2 \right] = \mathbb{E}\left[ \int_0^t g^2(s)ds \right] $$

if we use the Ito convention. Hint: use the discretization

$$ \sum_{i=0}^{n-1} g(t_i)[ B(t_{i+1} - B(t_i)) ] $$

and after all the calculations, take the limit $n\to\infty$.

---

### 3. Ito differential

Calculate the Ito differential for $[B(t)]^n$ and show that

$$ dB_t^n = nB_t^{n-1} dB_t + \frac{n(n-1)}{2} B_t^{n-2} dt $$

and 

$$ \int_0^t B^n dB = \frac{B_t^{n+1}}{n+1} - \frac{n}{2}\int_0^t [B(s)]^{n-1} ds $$

---

### 4. Log-normal distribution

By using the Ito differential of 

$$ Y(B,t)=e^{\lambda B(t) - \frac{\lambda^2}{2}t} $$

and that $B(0)=0$, show that $Y(t) = Y(B,t)$ solves the Ito SDE

$$ \begin{cases}
dY(t) = \lambda Y(t) dB(t) \\
Y(0) = 1
\end{cases} $$

show that $\langle Y(t) \rangle = 1\ \forall t\geq 0$ and 

$$ p(y,t) = \frac{1}{\sqrt{2\pi\lambda^2 t}y}\exp{\left[ -\frac{(\ln y + \frac{\lambda^2t}{2})^2}{2\lambda^2 t} \right]} $$

This is called log-normal distribution.

---

### 5. Geometric Brownian motion

The stochastic process $x(t)$ satisfies the Ito SDE

$$ \begin{cases}
dx = \frac{x}{2}dt + xdB \\
x(0) = 1
\end{cases} $$

Show that the process $y=\ln x$ satisfies the Ito SDE

$$ \begin{cases}
dy = dB \\
y(0) = 0
\end{cases} $$

and therefore the solution of the original SDE is $x(t)=e^{B(t)}$.

---

### 6. Ito formula for 2 variables

Assume that the two processes $x(t)$ and $y(t)$ satisfies the two Ito SDEs 

$$ \begin{cases}
dx = \mu_x dt + \sigma_x dB \\
dy = \mu_y dt + \sigma_y dB
\end{cases} $$

By using the Ito rules, show that if $u(x,y)\in\mathcal{C}^2(x,y)$ then 

$$ du = \left( \frac{\partial u}{\partial x}\mu_x + \frac{\partial u}{\partial y} \mu_y + \frac{1}{2} \frac{\partial^2 u}{\partial x^2}\sigma_x^2 + \frac{1}{2} \frac{\partial^2 u}{\partial y^2} \sigma_y^2 + \frac{\partial^2 u}{\partial x \partial y} \sigma_x \sigma_y \right) dt + \left( \frac{\partial u}{\partial x}\sigma_x + \frac{\partial u}{\partial y}\sigma_y \right) dB $$

Take $u(x,y) = xy$, then one can write

$$ d(xy) = (x\mu_x + y\mu_y + \sigma_x\sigma_y) dt + (x\sigma_y + y\sigma_x) dB $$

and deduce the correlation between the two processes $x$ and $y$.

---

### 7. Generalized Ornstein-Uhlenbeck

Find the solution of the SDE 

$$ \begin{cases}
dx = (\beta - \mu x) dt + \sigma dB \\
x(0) = x_0
\end{cases} $$

---

### 8. Ornstein-Uhlenbeck variance from PDF

Show that the equation for the variance that one gets from the SDE is the same that one gets from the Fokker-Plank equation

$$ \dot{p} = -\frac{\partial}{d x} \left[ (-\mu x) p \right] + \frac{\sigma^2}{2} \frac{\partial^2}{\partial x^2} p $$

Verify that at stationarity the value is $\sigma^2/2\mu$.

---

### 9. Brownian particle with harmonic potential

---

### 10. Poisson process mean

$$\begin{cases}
\dot{p}_n = \lambda(p_{n-1} - p_n)\\
p_n(0) = \delta_{n,n_0}
\end{cases}$$

Show that the mean satisfies the equation $\frac{d}{dt} \langle n \rangle =\lambda $ and so $\langle n(t) \rangle = n_0 + \lambda t$.

---

### 11. Radioactive decay

$$\begin{cases}
\dot{p}_n = \gamma(n+1)p_{n+1} - \gamma n p_n \\
\dot{p}_{N_0} = -\gamma N_0 p_{N_0} \\
p_n(0) = \delta_{n,N_0}
\end{cases}$$

Show that $\langle n \rangle = N_0 e^{-\gamma t}$.