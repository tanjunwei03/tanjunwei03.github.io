---
layout: blog
title: Strogatz Asymptotic Analysis - Lectures 1-5
---
I've been watching the [lectures](https://www.youtube.com/watch?v=KZsk8B_z8pI&list=PL5EH0ZJ7V0jV7kMYvPcZ7F9oaf_YAlfbI) by Strogatz on asymptotic analysis recently - here is my summary of the first 5 lectures. 

**Definitions**
Here are some definitions. Note that these definitions are all true "as \\(x\rightarrow x_0\\)":
1. \\(f(x)\\) is <em>asymptotically equal</em> to \\(g(x)\\), or\\(f(x)~g(x)\\) if and only if \\(\lim_{x\rightarrow x_0}\frac{f(x)}{g(x)}=1\\)
2. \\(f(x)=O(g(x))\\) if and only if \\(0<\lim_{x\rightarrow x_0}\frac{f(x)}{g(x)}<\infty\\)
3. \\(f(x)<<g(x)\\) if and only if \\(\lim_{x\rightarrow x_0}\frac{f(x)}{g(x)}=0\\)
4. \\({\phi_j}\\) is an asymptotic sequence if \\(\phi_{j+1}<<\phi_j\\)
5. We call \\(f~a_1\phi_1+a_2\phi_2+a_3\phi_1+...\\) an <em>asymptotic expansion</em> of \\(f\\) if and only if \\({\phi_j}\\) is an asymptotic sequence and \\(f-\sum_{k=1}^n a_k\phi_k<<\phi_n\\)

**Laplace's Method**
Laplace's method is a technique to evaluate definite integrals of the form \\(\int_a^b f(t)\exp(xg(t))dt\\) where \\(x\rightarrow\infty\\). Note that \\(g(t)\\) must have a local maximum on \\((a,b)\\). In this case, as \\(x\\) increases, the integral would become more "sharply peaked" around this local maximum, and the integral would begin to depend (asymptotically) only on points within a small neighbourhood of this peak. 

Example (as in the lecture):
\\[I(x) = \int_{-\infty}^{\infty}\exp(-x\cosh t)dt\\]
The peak of this integral is clearly at \\(x=0\\). Since we are working only in a small neighbourhood of this point, we can expand \\(\cosh t=1+\frac{t^2}{2}+O(t^3)\\). The integral then becomes \\(I(x)=\exp(-x)\int_{-\infty}^{\infty}\exp(-xt^2/2)dt\\). This integral can be easily evaluated (for example, using polar coordinates), and gives \\(I(x)=\exp(-x)\sqrt{\frac{2\pi}{x}}\\)