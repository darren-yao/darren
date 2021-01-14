---
layout: post
title: Evaluating Divergent Series
date: 2021-01-13 
usemathjax: true
---

    "Divergent series are the invention of the devil, and it is a shame to base on them any 
    demonstration whatsoever" -Niels Henrik Abel

When discussing infinite series, we usually tend to classify them as convergent or divergent. A series $$\sum_{n=0}^{\infty} a_n$$ is convergent if $$\lim_{N\to\infty} \sum_{n=0}^{N} a_n$$ exists and is finite. A series where the limit doesn't exist (because it goes off to infinity, or oscillates forever) is considered divergent. For example, the series $$\sum_{n=0}^{\infty} \frac{n}{2^n}$$ converges to 2, while $$\sum_{n=0}^{\infty} \frac{1}{n}$$ and $$\sum_{n=0}^{\infty} (-1)^n$$ are divergent. Normally, in the study of infinite series, divergent series are simply marked off as divergent without any further investigation. However, there exist meaningful ways of assigning values to divergent series, which we will discuss here.

### Problems with Conventional Evaluation Methods

So, what happens if we try to "evaluate" a divergent series normally? Take the following series: $$ \sum_{n=0}^{\infty} (-1)^n. $$ Let's write it out:

\\[1-1+1-1+1-1+\cdots = (1-1)+(1-1)+(1-1)+(1-1)+\cdots = 0\\]

Now, if we pair up the terms a different way, we get 

\\[1-1+1-1+1-1+\cdots = 1+(-1+1)+(-1+1)+(-1+1)+\cdots = 1 \\]

This raises an obvious issue, as a series can't be equal to 0 and 1 at the same time. It turns out that we can't manipulate conditionally convergent series in this way, let alone divergent series. 

### Cesaro and (C, a) summation

One method of evaluating divergent series is called Cesaro summation, where we take the limit of the mean of the partial sums rather than the limit of the partial sums themselves.

**Definition:** If we use $$s_n$$ to denote the $$n^{th}$$ partial sum, then the Cesaro sum of a series is $$\sum_{n=0}^{\infty} {a_n} = \lim_{k\to\infty} \frac{1}{k} \sum_{n=1}^{k} s_n$$. 

Cesaro summation works well for evaluating series where the partial sums oscillate. For example, for the series $$\sum_{n=0}^{\infty} (-1)^n$$, the first few averages of partial sums are $$\frac{1}{1}, \frac{1}{2}, \frac{2}{3}, \frac{1}{2}, \frac{3}{5}$$, and so on. Approaching infinity, we have $$\lim_{k\to\infty} \frac{1}{k} \sum_{n=0}^{k} s_n = \frac{1}{2}$$, which is the Cesaro sum of this series.

However, if the limit of the partial sums goes to infinity, so does the limit of their averages, so in such cases Cesaro summation will not be useful.

Later, Cesaro generalized the concept of Cesaro summation to $$(C, a)$$ summation. The C stands for Cesaro, and $$a$$ is a nonnegative integer defining the order of this summation. $$(C, 0)$$ summation is just ordinary summation of a series, and $$(C, 1)$$ is ordinary Cesaro summation. The higher-degree summations are defined as follows:

**Definition:** Given a series $$\sum a_n$$, define $$A_n^{-1} = a_n$$ and $$A_n^a = \sum_{k=0}^{n} A_k^{a-1}$$ (where the upper indices do not denote exponents), and $$E_n^a$$ to be $$A_n^a$$ for the series $$1+0+0+0+\cdots$$. Then, the $$(C, a)$$ sum of $$\sum a_n$$ is defined as $$\lim_{n\to\infty} \frac{A_n^a}{E_n^a}$$. In fact, $$(C, a)$$ summation is just the result of iteratively applying Cesaro summation $$a$$ times.

As the value of $$a$$ increases, $$(C, a)$$ summation gets stronger. This means that if a series $$\sum a_n$$ can be evaluated using $$(C, a_1)$$ summation, then it can also be evaluated to the same value using $$(C, a_2)$$ summation for any $$a_2 > a_1$$.

### Analytic Continuation of the Zeta Function

Some interesting series are represented as a function of a variable, like the Riemann zeta function. However, these series generally only converge over part of their domain.

Normally, the zeta function only converges when $$Re(s) > 1$$. However, we can use analytic continuation to extend the domain of the function to the entire complex plane (except for $$s = 1$$). Usually, this happens when the function has a power series representation with a radius of convergence extending outside the originally defined domain. Let's introduce some necessary definitions first:

**Definition:** A function is an **analytic function** on a region R if it is complex differentiable on every point in R. 

**Definition:** Let $$f_1$$ and $$f_2$$ be analytic functions on domains $$\Omega_1$$ and $$\Omega_2$$, respectively, such that $$\Omega_1 \cap \Omega_2$$ is not empty and $$f_1 = f_2$$ on $$\Omega_1 \cap \Omega_2$$. Then, $$f_2$$ is called an **analytic continuation** of $$f_1$$ to $$\Omega_2$$ and vice versa. If it exists, this analytic continuation is unique. 

**Definition:** The **Riemann zeta function** is a function of a complex variable, defined for $$Re(s) > 1$$ as follows: $$\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s}$$. When $$Re(s) \leq 1$$, then $$\zeta (s)$$ is defined using analytic continuation. 

**Definition:** The **Bernoulli numbers** are a sequence of rational numbers defined as follows: $$B_m = \sum_{k=0}^{m} \sum_{v=0}^{k} (-1)^v \binom{k}{v} \frac{v^m}{k+1}$$. Alternatively, they are defined by the exponential generating function $$\frac{x}{e^x -1} = \sum_{n=0}^{\infty} \frac{B_n x^n}{n!}.$$ 

Now, we can present the following theorem that relates the Riemann zeta function to the Bernoulli numbers:

**Theorem¹ :**  $$\zeta(-s) = -\frac{B_{s+1}}{s+1}$$ after applying analytic continuation to the series definition of the zeta function. 

Interestingly, if we plug in $$s = 1$$ to this theorem, we can assign a value to the sum of the positive integers, which you may have seen from a popular Numberphile video: $$ \sum_{n=1}^{\infty} n = -\frac{1}{12}. $$

If we plug in $$s = 2$$, we get $$ \sum_{n=1}^{\infty} n^2 = 0. $$

### p-adic Number Systems

Instead of assigning a value to a divergent series based on its properties, we can simply use a number system in which the series in question actually converges. For exponential series, we can use the p-adic number system to do this.

In our normal decimal number system, we measure the distance between two numbers by the absolute value of their difference. Specifically, $$dist(x, y) = \lvert x-y \rvert$$. If we did the opposite and used a distance function such that numbers that differed by large prime powers were close together, then we can actually evaluate series that would normally diverge.

**Definition:** Let p be a prime. The **p-adic norm** of 0 is defined to be 0: $$\lvert 0 \rvert_p = 0$$. For any nonzero rational x, we write $$x = \frac{p^a r}{s}$$, where r and s are relatively prime to p, and a is maximized. Then, the **p-adic norm of x** is $$\lvert x \rvert_p = p^{-a}$$.

We can use this to sum the series $$\sum_{n=0}^{\infty} 2^n$$. For any positive integer N, $$\sum_{n=0}^{N} 2^n = 2^{N+1} - 1$$. Now, we'll show that the limit of these partial sums approaches $$-1$$. The difference between $$2^{N+1} - 1$$ and $$-1$$ is $$2^{N+1}$$, the norm of which is $$2^{-N-1}$$ when taken 2-adically. Thus, as $$N \to \infty $$, this difference goes to zero 2-adically. When two numbers differ by zero, then they are equal; thus we have $$\sum_{n=0}^{\infty} 2^n = -1$$.





References: 

- 1: [https://terrytao.wordpress.com/2010/04/10/the-euler-maclaurin-formula-bernoulli-numbers-the-zeta-function-and-real-variable-analytic-continuation/](https://terrytao.wordpress.com/2010/04/10/the-euler-maclaurin-formula-bernoulli-numbers-the-zeta-function-and-real-variable-analytic-continuation/)


\*The content of this post is primarily taken from an expository paper I wrote for the Euler Circle mathematics program a few semesters ago.