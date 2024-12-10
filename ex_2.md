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
  - [1. Reaction-diffusion – random walk](#1-reaction-diffusion--random-walk)
    - [1. Reaction-diffusion boundary conditions](#1-reaction-diffusion-boundary-conditions)
    - [2. Generating function for the random walk](#2-generating-function-for-the-random-walk)
    - [3. Turing pattern](#3-turing-pattern)
    - [4. Random walk solution](#4-random-walk-solution)
    - [5. Random walk average and variance from the solution](#5-random-walk-average-and-variance-from-the-solution)
    - [6. Fundamental solution](#6-fundamental-solution)
    - [7. Average and variance](#7-average-and-variance)
    - [8. More random walk](#8-more-random-walk)
    - [9. Diffusion equation with absorbing boundary conditions](#9-diffusion-equation-with-absorbing-boundary-conditions)
    - [10. Diffusion equation with reflecting boundary conditions](#10-diffusion-equation-with-reflecting-boundary-conditions)
  - [3. Stochastic processes](#3-stochastic-processes)
    - [1. Ornstein-Uhlenbeck process](#1-ornstein-uhlenbeck-process)
    - [2. Brownian bridge](#2-brownian-bridge)
    - [3. Another process](#3-another-process)
    - [4. Brownian motion and law of large numbers](#4-brownian-motion-and-law-of-large-numbers)
    - [5. Rescaling](#5-rescaling)
    - [6. Inversion](#6-inversion)
    - [7. Time reversal](#7-time-reversal)
    - [8. The Brownian motion is a Markov process](#8-the-brownian-motion-is-a-markov-process)
    - [9. The Brownian motion is a non-stationary Markov process](#9-the-brownian-motion-is-a-non-stationary-markov-process)
    - [8. Poisson process](#8-poisson-process)
    - [9. Chapman-Kolmogorov](#9-chapman-kolmogorov)
    - [10. Ornstein-Uhlenbeck process](#10-ornstein-uhlenbeck-process)
    - [11. Two-point correlation function](#11-two-point-correlation-function)
    - [12. Functional moment generating function](#12-functional-moment-generating-function)
    - [13. More on functionals](#13-more-on-functionals)

---

## 1. Reaction-diffusion – random walk

### 1. Reaction-diffusion boundary conditions

Redo all the calculations for the solutions of the reaction-diffusion equation

$$ \frac{\partial u}{\partial t} = D \frac{\partial^2 u}{\partial x^2} + f(u) $$

with

i) zero-flux boundary conditions

$$ \frac{\partial u}{\partial t}\bigg|_{x=0} = \frac{\partial u}{\partial t}\bigg|_{x=L} = 0 $$

ii) periodic boundary conditions 

$$ \frac{\partial u}{\partial t}\bigg|_{x=0} = \frac{\partial u}{\partial t}\bigg|_{x=L} $$

### 2. Generating function for the random walk

Determine an expression for the generating function for the random walk when the initial site is a generic site $i=i_0$ different from $i=0$.

---

### 3. Turing pattern

Determine the conditions for the diffusion driven instability (i.e. Turing patterns) for the Activator-Substrate Deplition model near the steady-state $(u_0,v_0)=(1,1)$.

$$ \begin{align*} 

2 U + V &\xrightarrow{\bar{\mu}} 3 U \\

U &\xrightarrow{\gamma} \emptyset \\

\emptyset &\xrightarrow{\beta} V \\

\end{align*} $$

---

### 4. Random walk solution

For the random walk find the solution $w_i(k)$ for $w_i(0)=\delta_{i,i_0}$ and then possibly for a generic initial condition $w_i(0)=g_i$.

---

### 5. Random walk average and variance from the solution

For the random walk with $w_i(0)=\delta_{i,i_0}$ calculate $\mu(k)$ and $\sigma^2(k)$ by using the explicit solution

$$ w_i(k) = 
\begin{cases}
{k\choose \frac{k+i}{2}}(p+)^{\frac{k+i}{2}}(p_0)^{\frac{k-i}{2}}\ -k\leq i \leq k \\
0\qquad \text{otherwise}
\end{cases}
$$

---

### 6. Fundamental solution

Show that the fundamental solution of $\partial_t w(x,t) = -v \partial_x w(x,t) + \frac{D}{2} \partial_x^2 w(x,t)$ is given by

$$ w_v(x,t) = \frac{1}{\sqrt{2\pi Dt}}\exp{\left[- \frac{(y-x-vt)^2}{2Dt} \right]} $$

---

### 7. Average and variance

Consider the previous exercise. Show that $\langle x(t) \rangle = y + v t, v\in\mathbb{R}$ and calculate the variance at time $t$: $\sigma^(t)=\langle x^2(t) \rangle - \langle x(t) \rangle^2$ and show that it scales linearly with time (like in the discrete case).

---

### 8. More random walk

Repeat all the calculations of the simple random walk with more then 2 steps (master equation, mean, variance, etc.).

---

### 9. Diffusion equation with absorbing boundary conditions

Solve the following problem with Fourier series

$$
\begin{cases}
\partial_t w_a(x,t) = \frac{D}{2} \partial_x^2 w_a(x,t) \qquad x\in R^+, t>0 \\
w_a(0,t) = 0 \qquad \forall t > 0 \\
w_a(x,0) = \delta(x-y) \qquad y>0
\end{cases}
$$

---

### 10. Diffusion equation with reflecting boundary conditions

Solve the following problem with the euristic method

$$
\begin{cases}
\partial_t w_a(x,t) = \frac{D}{2} \partial_x^2 w_a(x,t) \qquad x\in R^+, t>0 \\
w_a(0,t) = \partial_x w_r(x,t)\big|_{x=0}=0 \qquad \forall t>0 \\
w_a(x,0) = \delta(x-y) \qquad y>0
\end{cases}
$$

## 3. Stochastic processes

### 1. Ornstein-Uhlenbeck process

Define the following stochastic process

$$ V(t) = e^{-t} B(e^{2t}) $$

where $B(t)$ is a Brownian motion. Show that $\mathbb{E}[V] = 0$, $\mathbb{E}[V(t)V(s)] = e^{-\lvert t-s\rvert }$.

---

### 2. Brownian bridge

Define the following stochastic process

$$ V(t) = T B(t) - t B(t)\qquad t\in[0,T] $$

where $B(t)$ is a Brownian motion. Show that $\mathbb{E}[V] = 0$, $\mathbb{E}[V(t)V(s)] = T^2 \min (t,s) - T ts$ for $t,s \in [0,T]$.

---

### 3. Another process

Show that $\mathbb{E}[e^{-\lambda B(t)}] = e^{-\frac{\lambda^2}{2} t}$

---

### 4. Brownian motion and law of large numbers

With the help of the law of large numbers, considering that $B(t) = \sum_{i=t} \Delta B_i$, show that

$$ \lim_{t \to \infty} \frac{B(t)}{t} = 0 $$

(This is an almost sure convergence. The Brownian motion may diverge towards infinity but it does so less then linearly.)

---

### 5. Rescaling

Show that the process 

$$ Z(t) = \frac{1}{\sqrt{c}} B(ct),\quad c>0 $$

is distributed as a Brownian motion. It's enough to show what are the properties of $\mathbb{E}[e^{i\lambda z}]$.

---

### 6. Inversion

Show that the process $Z(t) = t B(1/t), t>0$ and $Z(0) = 0$ is distributed like a Brownian motion. You can user this property to prove also exercice 4.

---

### 7. Time reversal

Define $Z(t) = B(t) - B(T - t)$ for $t\in[0,T]$ and show that $Z$ and $B$ have the same distribution.

---

### 8. The Brownian motion is a Markov process

Consider the propagator of the Brownian motion

$$ p_{1|1}(x_1t_1|x_0t_0) = w(x_1t_1|x_0t_0) = \frac{1}{2\pi(t_1 - t_0)}e^{-\frac{(x_1 - x_0)^2}{2(t_1 - t_0)}} $$

show that the Brownian motion is a Markov process by checking that it satisfies the Chapman-Kolmogorov equation (CK1)

$$ p_{1|1}(x_2t_2|x_0t_0) = \int dx_1 p_{1|1}(x_2t_2|x_1t_1)p_{1|1}(x_1t_1|x_0t_0) $$ 

---

### 9. The Brownian motion is a non-stationary Markov process

Consider the previous exercice. Show that if you take $p_1(y_1,t_1=0)=\delta(y_1)$ the CK2 equation

$$ p_1(x_2t_2) = \int dx_1 p_{1|1}(x_2t_2|x_1t_1)p_1(x_1t_1) $$

gives

$$ p_1(y_2,t_2) = \frac{1}{\sqrt{2\pi t_2}} e^{-y_2^2/2t_2} $$

This generates a non-stationary Markov process.

---

### 8. Poisson process

Show that the Poisson process

$$ p_{1|1} = (x_2,t_2|n_1,t_1) = \frac{ (t_2-t_1)^{n_2 - n_1} }{(n_2 - n_1)!} e^{-(t_2 - t_1)} \qquad t_2 > t_1 $$

$$ p_1(n,0)=\delta_{n,0} \qquad\Rightarrow\qquad p_1(n,t) = \frac{t^n}{n!}e^{-t}$$

is a non-stationary Markov process.

---

### 9. Chapman-Kolmogorov

Show that for $x,y=\pm 1$ the function

$$ p_{1|1}(xt|yt') = \frac{1}{2}\left[ 1 + e^{-2\gamma(t-t')} \right]\delta_{x,y} + \frac{1}{2}\left[ 1 - e^{-2\gamma(t-t')} \right]\delta_{x,-y} $$

satisfies the Chapman-Kolmogorov equation (CK1)

$$ p_{1|1}(x_2t_2|x_0t_0) = \int dx_1 p_{1|1}(x_2t_2|x_1t_1)p_{1|1}(x_1t_1|x_0t_0) $$  

---

### 10. Ornstein-Uhlenbeck process

Show that the OU process defined by the propagator

$$ p_{1|1}(x,t|y,t') = \frac{1}{2\pi (1 - e^{-2|t-t'|})} \exp \left[ - \frac{(x - y e^{-|t-'t|})^2}{ 2(1 - e^{-2|t-t'|}) } \right] $$

and the distribution

$$ p_{1}(x) = \frac{1}{\sqrt{2\pi}} e^{-x^2/2} $$

is a stationary Markov process. (The stationary process of this is a Gaussian distribution) 

---

### 11. Two-point correlation function

Show that the 2-point correlation function of the Brownian motion $x(t)$ is

$$ \langle x(t_1) x(t_2) \rangle = x_0^2 + Dt_1\wedge t_2 \qquad \text{for }\ t_0<t_1<t_2,\ x(t_0)=x_0 $$

by means of the Wiener measure

$$ d\mathbb{P}_{t_1\dots t_n}(x_1,\dots,x_n|x_0t_0) = \Pi_i = w(x_it_i|x_0t_0)dx_1 $$

---

### 12. Functional moment generating function

Show that if $F(z)=e^{hz}$ we can obtain the moment generating function of $\int_0^T a(t)x(t)dt $ with the following

$$ \langle e^{\int_0^T a(t)x(t)dt} \rangle_{B.m.} = e^{\frac{D}{2}R(T)h^2} $$

---

### 13. More on functionals

Let $F(z)=e^z$ and $a(s) = h_1\delta(t_1 - s) + h_2\delta(t_2-s)$, $0<t_1,t_2<T$. Calculate $A(s)$, $R(T)$, $\int_0^T a(s)x(s)ds$, $Z(h_1h_2)$ and

$$ \frac{\partial^2 Z}{\partial h_1 \partial h_2}\bigg|_{h_1=h_2=0} = \langle x(t_1) x(t_2) \rangle_{B.m.} = D t_1\wedge t_2  $$