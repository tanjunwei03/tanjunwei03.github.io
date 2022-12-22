---
layout: blog
title: Density Matrices and Measurements
---
I have recently been studying density matrices seriously for the first time in Nielsen and Chuang, and I found that I did not sufficiently understand many of the concepts. The only solution was, of course, for me to work through all the theorems again.

**Measurements**
A <em>measurement</em> is defined by a set of measurement operators \\(M_m\\) that satisfy the <em>normalisation condition</em> \\(\sum_i M_m^\dagger M_m=I\\), where \\(I\\) is the identity matrix. The subscript \\(m\\) refers to the set of <em>measurement outcomes</em>. Consider a measurement on a state \\(\ket{\psi}\\).  The probability that we have a measurement outcome \\(m\\) is given by \\(\bra{\psi}M_m^\dagger M_m\ket{\psi}\\). The state after measurement is given (up to normalisation) by \\(M\ket{\psi}\\)

A special case of this is known as <em>projective measurement</em>, where instead of a general operator \\(M_m\\) we have <em>projectors</em> \\(P_m\\). Recall that a projector is a Hermitian operator which squares to itself (i.e. it is idempotent). The normalisation condition is satisfied if and only if the subspaces that we are projecting on are orthogonal - that is, \\(P_jP_i=P_i\delta_{ij}\\). It should be noted that projective measurements, augmented by unitary operators, are actually equivalent to the general measurement postulate.

Of particular usefulness is the POVM formalism, which can be used when we are interested in the measurement outcomes, but not the states after measurement. This occurs more frequently than expected. For example, in a quantum computer, it is always possible to shift the measurement operations to the end of a circuit, after which we do not really care about the state of the qubits. The mathematical formulation of the POVM operation is rather easy - we simply consider \\(A_m=M_m^\dagger M_m\\) instead of the measurement operators \\(M_m\\) themselves. Thus, the probability of a measurement result \\(m\\) is just \\(\bra{\psi}A_m\ket{\psi}\\). 

Clearly, specifying the POVM elements \\(A_i\\) does not allow us to uniquely determine the state after measurement. If we define new set of measurement operators \\(M'_m=UM_m\\) for unitary \\(U\\), it is clear to see that these two sets of measurement operators have the same POVM elements. However, the state after measurement by these two sets are different (related by a unitary).

**Density Matrices**
A density matrix is given by \\(\sum_i p_i\ket{\psi_i}\bra{\psi_i}\\), where \\(p_i\\) is the probability that our system is in state \\(\ket{\psi_i}\\). It should be noted that this is <em>not related</em> to the concept of superposition. It is not the case that the state is in a superposition of the \\(\ket{\psi_i}\\). It is in <em>any</em> of them. We simply do not know which. It should also be noted that the \\(\ket{\psi_i}\\) need not be orthogonal. After all, since this is a reflection of our lack of knowledge, there is no physical basis for there to be any kind of restriction on the states in the ensemble.

In particular, if we have a state \\(\ket{\psi_j}\\) in the ensemble, it is not true that ths state is an eigenvector of the density matrix with eigenvalue \\(p_j\\). We can write this out explicitly:

\\[\rho\ket{\psi_j}=\left[\sum_i p_i\ket{\psi_i}\bra{\psi_i}\right]\ket{\psi_j}=\sum_i p_i\ket{\psi_i}\braket{\psi_i}{\psi_j}\neq\sum_i p_i\ket{\psi_i}\delta_{ij}\\]

The last (inequality) would only be true if the states are orthogonal.

Under measurement with measurement operators \\(M_m\\), each state \\(\ket{\psi}\\) becomes \\(M_m\ket{\psi}\\). Thus, if we know that we performed a measurement and obtained a result \\(m\\), the resulting density matrix would be \\(\rho'=\sum_i p_i \frac{M_m\ket{\psi_i}\bra{\psi_i}M_m^\dagger}{\bra{\psi_i}M_m^\dagger M_m\ket{\psi_i}}\\) (with appropriate normalisation). If we do not know what measurement result we obtained, then we must sum over all possible measurement results too. The density matrix then takes the rather neat form
\\[\rho'=\sum_{i,m}M_m\ket{\psi_i}\bra{\psi_i}M_m^\dagger\\]

Given a density matrix, a natural question to ask is if we can determine the probability of a certain measurement result \\(m\\). To do so, we need to prove the following theorem

\\[\bra{\psi}M_m^\dagger M_m\ket{\psi}=Tr(M_m^\dagger M_m\ket{\psi}\bra{\psi})\\]

We evaluate the right hand side:
\\[Tr(M_m^\dagger M_m\ket{\psi}\bra{\psi})=\sum_i \bra{v_i}M_m^\dagger M_m\ket{\psi}\braket{\psi}{v_i}\\]
Where \\(\ket{v_i}\\) is some orthonomal basis. The right hand side can be rearranged to form
\\[\sum_i \braket{\psi}{v_i}\bra{v_i}M_m^\dagger M_m\ket{\psi}=\bra{\psi}\left[\sum_i\ket{v_i}\bra{v_i}\right]M_m^\dagger M_m\ket{\psi}=\bra{\psi}M_m^\dagger M_m\ket{\psi}\\]
Thus proving the theorem. Note that the orthonomal basis \\(\ket{v_i}\\) can always be computed using the gram-schmidt procedure, thus it always exists.

Hence, the probability that a measurement has result \\(m\\) is given by \\(\sum_i p_i\bra{\psi_i}M_m^\dagger M_m\ket{\psi_i}=Tr\left(\sum_i p_i M_m^\dagger M_m\ket{\psi_i}\bra{\psi_i}\right)=Tr\left(M_m^\dagger M_m\rho\right).