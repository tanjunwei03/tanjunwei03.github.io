---
layout: blog
title: Density Matrices for Composite Systems
---
This was originally intended to be content in the previous blog post, but after realising I had many (rather deep) misconceptions about density matrices for composite systems I decided to make it its own blog post.
**General Form of a Two-Body Density Matrix**
It is well known that in general, we cannot express a state \\(\ket{\psi}\in\mathcal{H}_1\otimes\mathcal{H}_2\\) as a product \\(\ket{\psi}\otimes\ket{\phi}\\). This corresponds to the fact that a rank-two tensor is, in general, not the tensor product of two rank one tensors.

**Composite Systems and the Partial Trace**
For a two body system, the density matrix generalises simply
\\[\rho=\sum_{ij}p_{ij}\left(\ket{\psi_i}\otimes\ket{\phi_j}\right)\left(\bra{\psi_i}\otimes\ket{\phi_j}\right)\\]

Where \\(\ket{\psi}\\) denotes a state belonging to the first Hilbert space, and \\(\ket{\phi}\\) denotes a state belonging to the second Hilbert space. It should be noted that this is equal to \\(\sum_{ij} p_{ij}(\ket{\psi_i}\bra{\psi_i})\otimes(\ket{\phi_j}\bra{\phi_j})\\). This can be seen by considering its action on an arbitrary state \\(\ket{\psi}\otimes\ket{\phi}\\)

We are interested in measurement statistics if we were to perform some form of measurement on a subsystem. Without loss of generality, we can take this to be the first subsystem. The mathematical operation that allows to do this is known as the <em>partial trace</em>