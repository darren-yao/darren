---
layout: post
title: Assume the Most Convenient Case
date: 2021-02-19 
usemathjax: true
---

A useful contest trick, particularly for the AMC.

Sometimes, problems will give some general category, and ask you to find a property that holds true for everything in that category. In such cases, one can simply assume a convenient case in order to "fakesolve" the problem.

The best way of demonstrating this is with examples:

### Some Random Puzzle from AoPS:

[Source](https://artofproblemsolving.com/keeplearning)

Five rectangles. The tilted black rectangle has area 16. What's the shaded area?

![Problem Diagram]({{site.baseurl}}/assets/img/MarkerProblem3.png)

### Solution: 

The problem gives no conditions on the rectangles, so we can simply assume all the rectangles are squares. Then, we have the following diagram:

![Problem Diagram]({{site.baseurl}}/assets/img/MarkerProblem3Sol.png)

By inspection, this yields an answer of $$\boxed{16}$$.

### 2021 AMC 12B Problem 16 / AMC 10B Problem 18:

Let $$g(x)$$ be a polynomial with leading coefficient $$1,$$ whose three roots are the reciprocals of the three roots of $$f(x)=x^3+ax^2+bx+c,$$ where $$1<a<b<c.$$ What is $$g(1)$$ in terms of $$a,b,$$ and $$c?$$

\\[ \textbf{(A) }\frac{1+a+b+c}c \qquad \textbf{(B) }1+a+b+c \qquad \textbf{(C) }\frac{1+a+b+c}{c^2}\qquad \textbf{(D) }\frac{a+b+c}{c^2} \qquad \textbf{(E) }\frac{1+a+b+c}{a+b+c} \\]

### Solution:

Because the problem doesn't specify what the coefficients of the polynomial actually are, we can just plug in any arbitrary polynomial that satisfies the constraints. Let's take $$f(x) = (x+5)^3 = x^3+15x^2+75x+125$$. Then $$f(x)$$ has a triple root of $$x = -5$$. Then $$g(x)$$ has a triple root of $$-\frac{1}{5}$$. Because $$g(x)$$ is monic, we have $$g(x) = \left(x+\frac{1}{5}\right)^3 = x^3 + \frac{3}{5} x^2 + \frac{3}{25} x + \frac{1}{125} = \frac{125x^3+75x^2+15x+1}{125}$$. We can see that this is $$\frac{1+a+b+c}{c}$$, which is answer choice $$\boxed{(A)}$$.

### 2021 AMC 12A Problem 10 / AMC 10A Problem 12:

Two right circular cones with vertices facing down as shown in the figure below contains the same amount of liquid. The radii of the tops of the liquid surfaces are $$3$$ cm and $$6$$ cm. Into each cone is dropped a spherical marble of radius $$1$$ cm, which sinks to the bottom and is completely submerged without spilling any liquid. What is the ratio of the rise of the liquid level in the narrow cone to the rise of the liquid level in the wide cone?

![Problem Diagram]({{site.baseurl}}/assets/img/2021AMC12A_10.png)

\\[ \textbf{(A) }1 \qquad \textbf{(B) }\frac{47}{43} \qquad \textbf{(C) }2 \qquad \textbf{(D) }\frac{40}{13} \qquad \textbf{(E) }4 \\]

### Solution:

Note that the problem doesn't say what the height of the water in the cones are. We can assume that the heights are very large numbers, so as $$h_1, h_2 \to \infty$$, the additional heights of water from the added marble satisfy $$\Delta h_1, \Delta h_2 \to 0$$. Furthermore, as height increases, changes in height lead to smaller and smaller percentage changes in the width of the cone at that point. Essentially, this means that the behavior of the "additional" segment of water, in each cone, approaches a very thin cylinder. Using this cylinder approximation, since the top area of the first cone is one-fourth the top area of the second cone, adding the same marble to each results in four times the height increase for the first cone, which is answer choice $$\boxed{(E)}$$.