---
title: Schur's Triangularization
draft: "false"
tags:
---
# Schur's Triangularization Theorem 
Schur's Triangularization Theorem state that's any $A \in \mathbb{C}^{n \times n}$ can be written as the product of an orthogonal matrix, $U \in \mathbb{C}^{n \times n}$ and upper triangular matrix $T_{A} \in \mathbb{C}^{n \times n}$:

$$A=UT_{A}U^H$$

It is possible for $T_{A}$ to be a diagonal matrix, which implies that $A$ is then unitarily diagonalizable, but generally it is 

This is a similarity transformation and we can derive various theorem about the determinant and the eigen values of $A$ from it. 
- - -
# Proof 

We can prove this result via induction. We will prove that any square $A$  can be expressed as $A=UT_{A}U^H$ where $A,U,T \in \mathbb{R}^{n \times n}$, $U$ is orthogonal, and $T_{A}$ is upper triangular. 

Consider the base case where $A \in \mathbb{R}^{1}$. Then consider $U$=1 and $T_{A}=A$ so we get the result that:

$$A=1 \cdot A \cdot 1^T = A$$
Since $U=1$ is orthogonal, $A$ is upper triangular, which implies that the base case of $n=1$ is true. 

For the inductive hypothesis, we assume that the result will hold for matrices of size $(n-1) \times (n-1)$.

Consider the characteristic polynomial of $A$ given by $P_{A}(\lambda).$ $P_{A}(\lambda)$ has $n$ roots, but allow us to consider the root $\lambda_{1}$ which is an eigen-value of $A$ with corresponding vector $\vec{v_{1}}$.

We can assume that $\| \vec{v_{1}} \| =1$ since, without loss of generality, any $\vec{v_{1}} \cdot c, c \in \mathbb{C}$ is still an eigen-vector. We know that $\dfrac{\vec{v_{1}} }{\| \vec{v_{1}}\|}$ is a unit vector. 

Using the Gram-Schmidt process we can convert the eigen-vectors of $A$ to be a set of orthonormal vectors. If we run out of eigen-vectors, we can consider their orthogonal complement and add them to the matrix. 

In total we have $n$ vectors that we will use to construct our orthogonal matrix, $V$.

Consider:
$$V =  \{ \vec{v_{1}} \vec{v_{2}} \dots \vec{v_{n}} \} = 
\left[
\begin{array}{c|c}
\vec{v_{1}} & V_{2} 
\end{array}
\right]
$$
where $V_{2} \in \mathbb{R}^{n\times(n-1)}$, which consists of all of the columns of $V$ except for the first vector $\vec{v_{1}}$. 

We will show that $U=V$ and that $T_{A}$ is an upper triangular matrix. Since we have established that $A=UT_{A}U^H$ we can see that $T_{A}=U^HAU$. We can more easily show this triangular result here. We will make the $U=V$ substitution below: 

$$U^HAU=\left[
\begin{array}{c|c}
\vec{v_{1}}^H\\ V_{2}^H 
\end{array}
\right]A\left[
\begin{array}{c|c}
\vec{v_{1}} & V_{2} 
\end{array}
\right]=\left[
\begin{array}{c|c}
\vec{v_{1}}^H\\ V_{2}^H 
\end{array}
\right]\left[
\begin{array}{c|c}
\vec{Av_{1}} & AV_{2} 
\end{array}
\right]=\left[
\begin{array}{c|c}
\vec{v_{1}}^HA\vec{v_{1}} & \vec{v_{1}}^HAV_{2} \\
\hline
V_{2}^HA\vec{v_{1}} & V_{2}^HAV_{2}
\end{array}
\right]$$
We know that $A \vec{v_{1}} = \lambda_{1} \vec{v_{1}}$ so $\vec{v_{1}}^H A \vec{v_{1}} = \lambda_{1}<\vec{v_{1}},\vec{v_{1}}> = \lambda_{1}$. 

Note also that since $V$ is an orthogonal matrix, by definition all $<\vec{v_{i}},\vec{v_{j}}>=0$ when $i \neq j$. So, $V_{2}^HA\vec{v_{1}}$ = 0.

Lastly notice that $V_{2}^HAV_{2}$ = $U_{2}T_{A_{2}}U^H$

$$\left[
\begin{array}{c|c}
\vec{v_{1}}^HA\vec{v_{1}} & \vec{v_{1}}^HAV_{2} \\
\hline
V_{2}^HA\vec{v_{1}} & V_{2}^HAV_{2}
\end{array}
\right]=\left[
\begin{array}{c|c}
\lambda_{1} & \vec{v_{1}}^HAV_{2} \\
\hline
0 & U_{2}T_{A_{2}}U^H
\end{array}
\right]$$

This matrix is nearly triangular, but notice that we can express it as a product of matrices which turns out to be of a triangular form: 

$$\left[
\begin{array}{c|c}
\lambda_{1} & \vec{v_{1}}^HAV_{2} \\
\hline
0 & U_{2}T_{A_{2}}U^H
\end{array}
\right]= \begin{bmatrix} 1 & 0\\0 & U_{2} \end{bmatrix} \left[
\begin{array}{c|c}
\lambda_{1} & \vec{v_{1}}^HAV_{2} \\
\hline
0 & T_{A_{2}}
\end{array}
\right] \begin{bmatrix} 1 & 0\\0 & U_{2}^H \end{bmatrix} $$
From this expression we can clearly see that the matrix in the center is an upper triangular matrix, and the matrices on the sides are both orthogonal. We see that the inductive hypothesis holds for $n$. In turn, we have obtained the result that $A$ can indeed be factored into a corresponding $UT_{A}U^H$

In turn, all entries of $T_{A}$ are the eigenvalues of $A$. 

---
# Important Corollaries 

For any $A \in \mathbb{C}^{n  \times n}$ we can obtain the following results: 

1. $\text{tr}(A)= \sum_{i=1}^n$




