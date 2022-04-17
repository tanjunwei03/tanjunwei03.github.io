---
layout: blog
title: Active and Passive Picture of Canonical Transformations
---
In Goldstein's Classical Mechanics, he talks about how if we interpret canonical transformations passively a function of the canonical variables changes in functional form, but not value, but if we interpret them actively then they change in value but not form. This is a bit confusing to me, so let's try out an actual example.

Consider the block attached by a spring to a cart moving at constant velocity \\(v\\). The Lagrangian is then
\\[L=\frac 12m\dot{x}^2+\frac 12k\left(x-vt\right)^2\\]
The momentum is given by \\(p=mv\\), and the Hamiltonian is
\\[\mathcal{H}=\frac{p^2}{2m}+\frac 12k\left(x-vt\right)^2\\]
In this case, we choose a generating function of the second kind, \\(F_2=(P+mv)(x-vt)\\). We then have \\(p=\frac{\partial F_2}{\partial x}=P+mv\\), and \\(Q=\frac{\partial F_2}{\partial P}=x-vt\\), and thus \\(x=Q+vt\\). The new Hamiltonian is given by
\\[\mathcal{H}'=\mathcal{H}+\frac{\partial F_2}{\partial t}=\frac{p^2}{2m}+\frac 12k\left(x-vt\right)^2-v(P-mv)\\]
\\[\mathcal{H}'=\frac{(P+mv)^2}{2m}+\frac 12 kQ^2-Pv\\]
Where we ignore an unimportant constant in the last line. The equations of motion are then
\\[\frac 1m(P+\cancel{mv})-\cancel{v}=\dot{Q}\\]
\\[\dot{P}=-kQ\\]
These are the familiar equations of motion in terms of the momentum and position in the moving frame. Now consider some function of the canonical coordinates, say the energy (which, in the original set of canonical variables, is identical to the Hamiltonian)
\\[E(x,p)=\frac{p^2}{2m}+\frac 12k\left(x-vt\right)^2\\]
In the passive picture, the energy changes in functional dependence but not in value; the new energy is
\\[E'(Q,P)=\frac{(P-mv)^2}{2m}+\frac 12kQ^2\\]
Now in the active picture, the energy changes in value, but not the functional dependence - we replace \\(x\\) with \\(Q\\) and \\(p\\) with \\(P\\). This then gives us
\\[E(Q,P)=\frac{P^2}{2m}+\frac 12k(Q-vt)^2\\]
This is of the same form, and if we imagine the \\(t\\) in the canonical transformation to be a parameter bringing \\(P\\) away from \\(p\\) and \\(Q\\) away from \\(x\\), this will give the energy at some time.