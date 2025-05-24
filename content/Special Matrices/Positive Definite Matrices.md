---
title: Positive Definite Matrices
draft: "false"
tags:
---
# Definition of Positive Definite Matrix

A Positive Definite matrix, $A$ is defined as $A \in \mathbb{R}^{n \times n}$  and $A^T=A$, where $x^TAx>0$ except for $x=0$ which yields $x^TAx = 0$.

Some equivalent conditions for $A$ being positive definite given that $A^T=A$

1. $A$ has a Cholesky factorization
2. $A$ has an LDV factorization where each $D_{ii}>0$
3. All submatrices of $A$ are positive definite
4. All eigen values of $A$ are positive 

---
# Properties 

### $AA^T$ and $A^TA$ are SPD 
For any matrix $A \in \mathbb{R}^{n \times m}$ the matrix $A^TA$ and $AA^T$ are both positive definite matrices. Suffice to say, this class of matrices is commonly used and extremely important.  We make use of this when deriving the SVD of any matrix $A$.

$$x^TA^TAx=(Ax)^T(Ax)= \|A\vec{x} \|_{2}^2 \geq 0$$

Which is to say that the inner product of $A\vec{x}$ with itself is guaranteed to be greater than or equal to zero.  Note that this is essentially the same line of argument that $A$ having a Cholesky factorization is equivalent to being $SPD$.
### Sum of SPD matrices is SPD 
Consider $A$ and $B$ which are SPD:

$$x^T(A+B)x=x^TAx + x^TBx>0$$

Since $x^T(A+B)x >0$ then $A+B$ is also SPD>
#### Inverse of SPD matrix is SPD
We also know that for a SPD matrix $A$ that $A^{-1}$ is another SPD matrix. For any eigen value $\lambda \in \wedge(A)$, it follows that $A\vec{x}=\lambda\vec{x}$. But since we know that $A^{-1}\vec{x}=\frac{1}{\lambda}\vec{x}$, we can conclude that $A^{-1}$ must be another symmetric positive definite matrix since every $\lambda > 0$ for a SPD matrix, so $\frac{1}{\lambda} > 0$, which indicates that $A^{-1}$ must also be SPD. 

### Tr($A$) $>0$ and Det($A$)>0

Since all $\lambda \in \wedge(A) >0$, it follows that:

$$\text{det}(A)=\prod_{i=1}^{n}\lambda_{i}>0$$
$$\text{det}(A)=\sum_{i=1}^{n}\lambda_{i}>0$$

---
