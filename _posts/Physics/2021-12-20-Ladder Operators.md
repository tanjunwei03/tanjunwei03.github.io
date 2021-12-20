---
layout: blog
title: Ladder Operators
---
It seems that the proof that if \\([N,X]=cX\\), where \\(c\\) is positive and real, then \\(X\\) is a raising operator for \\(N\\) that I find on wikipedia at the time of posting this post is missing part of it. The missing part is: Why does it immediately follow that \\(X^\dagger\\) is a lowering operator?

To look into this, we start from the equation
\\[NX-XN=cX\\]
Taking the hermitian conjugate yields
\\[X^{\dagger}N^{\dagger}-N^{\dagger}X^{\dagger}=c^{*}X^\dagger\\]

\\[[X^{\dagger},N^{\dagger}]=c^{*}X^{\dagger}\\]

If \\(N\\) is hermitian, then \\(N=N^\dagger\\). That \\(c\\) is real can be seen by contradiction. If \\(c\\) were not real, then we would be able to find complex eigenvalues for \\(N\\), contradicting the hermicity of \\(N\\). Thus, we take \\(c=c^{*}\\) to get
\\[-[N,X^{\dagger}]=cX^\dagger\\]
\\[[N,X^{\dagger}]=-cX^\dagger\\]

This is of the form as our very first equation, which shows that \\(X^\dagger\\) is a lowering operator for \\(N\\).	
