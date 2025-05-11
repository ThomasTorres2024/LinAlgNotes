---
title: Spectral Theorem Definition and Proof
draft: 
tags:
---
- - -
<h3 align="center">Spectral Theorem Definition </h3>
The spectral theorem states that for all Hermitian Matrices, that is for matrices where $A \in \mathbb{R}^{n \times n}$ and  $A^H=A$ that:
1.  $A$ has real eigen values
2.  Eigenvectors corresponding to distinct eigen values in $A$ are orthogonal 
3. $A$ is orthogonally diagonalizable
- - - 
<h3 align="center">Proof that Eigen Values are Real for Symmetric Matrix A</h3>
Given that $\lambda$ is an eigen value of $A$ and that $\vec{v}$ is a corresponding eigen vector $\lambda$ , we want to show that $\lambda = \overline{\lambda}$, that $\lambda \not \in \mathbb{C}$.  Suppose that $\lambda \in \mathbb{C}$.

Begin with the original identity, and apply the Transpose operator. Then right multiply everything by $\overline{\vec{v}}$.

$$A \vec{v} = \lambda \vec{v} \Longleftrightarrow (A\vec{v})^T = (\lambda \vec{v})^T \Longleftrightarrow \vec{v}^TA^T = \overline{\lambda} \vec{v}^T \Longleftrightarrow \vec{v}^TA = \lambda \vec{v}^T $$
$$\begin{equation}\tag{1} v^TA \overline{v}^ = \lambda v^T \overline{v} \end{equation}$$
We will consider what happens when we apply the conjugate of both sides of $A \vec{v} = \lambda \vec{v}$, which in turn results in $A \overline{{v}} = \overline{\lambda v}$. A remains $A$ as we know $A \in \mathbb{R}^{n \times n}$ and its conjugate is simply itself.

Substituting:
$$\begin{equation}\tag{2} v^TA \overline{v} = v^T \overline{\lambda v} = \overline{\lambda} v^T \overline{v} \end{equation}$$
Note that $\vec{v} \neq \vec{0}$ since $\vec{v}$ is an eigen vector, and eigen vectors are by definition non-zero.
Notice that both $(1)$ and $(2)$ are equivalent so we can write that: 
$$\lambda v^T \overline{v} = \overline{\lambda} v^T \overline{v} \Longleftrightarrow \lambda<v,v> = \overline{\lambda}<v,v> \Longleftrightarrow \lambda = \overline{\lambda} $$
Since $\lambda = \overline{\lambda}$ it follows that $\lambda \in \mathbb{R}$

 - - - 
$$\Large \text{Proof that the eigen vectors of A form a basis of } \mathbb{R}^n $$
  For symmetric matrices $A$, $\exists$ an orthogonal matrix $R$ such that $R^{-1}AR$ is diagonal. 
Let $\lambda \in \mathbb{R}$ and is an eigen value of $A$ with corresponding eigen vector $\vec{v}_{1}$. Consider $\vec{v}_{1}$ which is normalized. 

We wish to extend $\vec{v}_{1}$ to be extended to a basis of $\mathbb{R}^n$ which will make use of $\{ v_{1}, u_{2}, u_{3}, \dots , u_{n}  \}$ where we have a basis consisting of eigen values corresponding to each eigen value that are not normalized denoted by $u_{k}$. We will then run the Gram-Schmidt process on this basis to force orthonormality.

The matrix, $P = [ v_{1},v_{2}, \dots , v_{n} ]$ is the matrix obtained by running the Gram-Schmidt process on the above basis.  Note that $P$ is an orthogonal matrix, so we know that $P^T = P^{-1}$ and that as well $PP^T = P^TP=I_{n \times n}$.

Note the similarity transformation $B = P^T A = P$. We want to argue that $B$ is a symmetric matrix. 
We can determine this easily by considering $B^T$:
$$B = P^T A P \Longleftrightarrow B^T = P^TA^TP \Longleftrightarrow B^T = P^TA P$$
  Since $B=B^T$ it is symmetric.

We can further show that $B$ must be a diagonal matrix. Consider multiplying it by $e_{k}$
 where $k \in \mathbb{N}$. $e_{k}$ is the $k$th identity vector.

$$Be_{k}=P^TAP{e_{k}}=P^TAv_{k}= \lambda_{k} P^Tv_{k} = \lambda_{k} e_{k}$$
Note, the reason we can do the last step comes from thinking of multiplication of $v_{k}$ by the rows of $P$, which results in $0$ at all indices other than 1 due to properties of the inner product. 

Thus, since each column of $B$ consists of $e_{k} \cdot \lambda_{k}$ it follows that $B$ is a diagonal matrix consisting of the eigen values of each eigen vector.

We can prove this inductively using this line of argument but I will not put it here. 

- - -
