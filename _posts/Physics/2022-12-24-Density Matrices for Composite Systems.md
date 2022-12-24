---
layout: blog
title: Density Matrices for Composite Systems
---
This was originally intended to be content in the previous blog post, but after realising I had many (rather deep) misconceptions about density matrices for composite systems I decided to make it its own blog post.

**General Form of a Two-Body Density Matrix**

It is well known that in general, we cannot express a state \\(\ket{\eta}\in\mathcal{H}_1\otimes\mathcal{H}_2\\) as a product \\(\ket{\psi}\otimes\ket{\phi}\\). This corresponds to the fact that a rank-two tensor is, in general, not the tensor product of two rank one tensors. However, it was not clear what this correspondence (or lack thereof) meant in terms of the density matrix. 

Following in the steps of Nielsen and Chuang, let us consider the density matrix for the Bell state \\(\left(\frac{\ket{00}+\ket{11}}{\sqrt{2}}\right)\left(\frac{\bra{00}+\bra{11}}{\sqrt{2}}\right)\\). Expanding, we get the density matrix
\\[\rho=\frac{\ket{00}{\bra{00}+\ket{11}\bra{00}+\ket{00}\bra{11}+\ket{11}\bra{11}}{2}\\]
This is quite clearly not the sum of product states \\((\ket{\psi}\bra{\psi})\otimes(\ket{\phi}\bra{\phi})\\). Now, this may seem clear in hindsight, but for reasons unknown to me, I was under the impression that states in the aforementioned form spanned the entire space of density operators. Perhaps the misconception arose from the fact that due to the already rather complicated looking form of \\((\ket{\psi}\bra{\psi})\otimes(\ket{\phi}\bra{\phi})\\), it is not clear that this form is restrictive. The correct general form of a term in the density matrix (in terms of product states) is \\(p(\ket{\psi_1}\bra{\psi_2})\otimes(\ket{\phi_1}\bra{\phi_2}).

Now, it is to be emphasized that this expression does not have any physical meaning in terms of the measurement statistics. We cannot, for example, say anything about the chances of finding subsystem \\(1\\) in \\(\ket{\psi_1}\\). The fundamental quantity is still the (non product) state \\(p\ket{\eta}\bra{\eta}\\). The probability that our system is in state \\(\ket{\eta}\\) is \\(p\\). From there, the probabilities of finding it in \\(\ket{\psi_1}\\) can be determined by projective measurement. 

**Composite Systems and the Partial Trace**

For a two body system, a term in the density matrix made of product states would take the form
\\[\left(\ket{\psi}\otimes\ket{\phi}\right)\left(\bra{\psi}\otimes\bra{\phi}\right)\\]

Where \\(\ket{\psi}\\) denotes a state belonging to the first Hilbert space, and \\(\ket{\phi}\\) denotes a state belonging to the second Hilbert space. It should be noted that this is equal to \\(\sum_{ij} p_{ij}(\ket{\psi_i}\bra{\psi_i})\otimes(\ket{\phi_j}\bra{\phi_j})\\). This can be seen by considering its action on an arbitrary state \\(\ket{\psi}\otimes\ket{\phi}\\)

We are interested in measurement statistics if we were to perform some form of measurement on a subsystem. Without loss of generality, we can take this to be the first subsystem. The mathematical operation that allows to do this is known as the <em>partial trace</em>. The partial trace is defined by \\(Tr_B(\ket{\psi_1}\bra{\psi_2}\otimes\ket{\phi_1}\bra{\phi_2})=(\ket{\psi_1}\bra{\psi_2})Tr(\ket{\phi_1}\bra{\phi_2})=(\ket{\psi_1}\bra{\psi_2})\braket{\phi_2}{\phi_1}\\). 

The partial trace is useful because this gives us the correct measurement statistics of a measurement on subsystem 1. Consider a POVM measurement on subsystem 1, denoted by an operator \\(M\\). If performed on the product space, the correct operator would be a product operator \\(M\otimes I_2\\). We seek a density operator \\(\rho^A\\) such that
\\[Tr\left(M\rho^A\right)=Tr\left((M\otimes I_2)\rho^{AB}\right)\\]

Clearly, if we simply define \\(\rho^A=Tr_B\left(\rho^B\right)\\), this will be satisfied.

(proof may be added if I can find the time to type it out)