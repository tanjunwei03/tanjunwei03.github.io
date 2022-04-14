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

At this point, it should be noted that Laplace's method is suited to evaluating higher order terms too - for example,  the quadratic expansion of \\(\cosh t\\) suggests the (exact) change of variable \\(\cosh t=1+\tau^2\\), or \\(\sinh t dt=2\tau d\tau\\). Then  \\(dt=\frac{2\tau}{\sinh t}d\tau=\frac{2\tau}{\cosh^2 t-1}d\tau=\frac{2\tau}{(1+\tau^2)^2-1}\\). AFter some more working, the integral becomes
\\[\sqrt{2}e^{-x}\int_{-\infty}^\infty\frac{e^{-x\tau^2}}{\sqrt{1+\frac 12\tau^2}}d\tau\\]
It is at this point that we invoke Laplace's method - as \\(x\rightarrow\infty\\), the integral becomes more sharply peaked around \\(\tau=0\\), and thus only the points close to that point will matter. We can then expand the denominator in powers of \\(\tau\\) for \\(\tau\\) close to \\(0\\), and we get
\\[I(x)~\sqrt{2}e^{-x}\int_{-\infty}^\infty e^{-x\tau^2}\left(1-\frac{1}{4}\tau^2+\frac{3}{32}\tau^4+...\right)d\tau\\]
These terms can then be integrated - the first gives us the first order term that we obtainde earlier from Laplace's method, and the other terms give the higher order terms (powers of \\(1/x\\))

**Method of Stationary Phase**

While in Laplace's method we investigated integrands of the form \\(f(t)e^{-xg(t)}\\), where \\(f\\) and \\(g\\) are real, now we investigate integrands of the form \\(f(t)e^(ixg(t))\\). Now the integral, instead of taking the form of a function sharply peaked around the extrema of \\(g\\), takes the form of an oscillatory function, modulated by \\(f\\), with the frequency determined by \\(xg(t)\\). As \\(x\rightarrow\infty\\), the frequency increases, and we will have an oscillatory cancellation. However, the frequency is still zero at all points where \\(g\\) is stationary. Thus, we expect the main contribution of the integral to come from such points.