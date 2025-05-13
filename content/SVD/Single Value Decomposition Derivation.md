---
title: SVD Introduction
draft: 
tags:
---
- - -
## Definition
We can decompose all matrices into a factorization given by $A = U \Sigma V^T$ where $A \in \mathbb{R}^{m \times n}$, 
$U \in \mathbb{R}^{m \times m}$ and is orthogonal, and $V \in \mathbb{R}^{n \times n}$ and is orthogonal, and $\Sigma \in \mathbb{R}^{m \times n}$ and is a diagonal matrix.  

	The matrix $V$ comes from the row space of $A$ and the matrix $U$ comes from the Column space of $A$ 

If $A$ is symmetric positive definite, $A$ has a much simpler SVD:
$$A=Q \wedge Q^T$$
where $Q, \wedge \in \mathbb{R}^{n \times n}$ and $Q$ is orthogonal. 
- - -
We can think of SVD as taking an orthonormal set $V$ and multiply it by matrix $A$ such that the result is another orthonormal set where each resulting value is scaled by the diagonal entries, $\sigma$ from the matrix $\Sigma$. 
$$AV=U\Sigma$$
$$\Longleftrightarrow A \begin{bmatrix}  
\vec{v_{1}} & \vec{v_{2}} & \dots & \vec{v_{m}}\\   
\end{bmatrix} = \begin{bmatrix} \vec{u_{1}} & \vec{u_{2}} & \dots & \vec{u_{n}}  \end{bmatrix} \begin{bmatrix} \sigma_{1}\vec{e_{1}} & \sigma_{2}\vec{e_{2}} & \dots & \sigma_{n}\vec{e_{n}}  \end{bmatrix}$$
$$\Longleftrightarrow A\begin{bmatrix}  
\vec{v_{1}} & \vec{v_{2}} & \dots & \vec{v_{m}}\\    
\end{bmatrix} = \begin{bmatrix} \sigma_{1}\vec{u_{1}} & \sigma_{2}\vec{u_{2}} & \dots & \vec{\sigma_{3}u_{n}}  \end{bmatrix}$$
 If it turns out that $A$ is not full rank and instead only has dimension $r$ then the remaining $n-r$ vectors will consist of the basis of the null space. 
 - - -
Our goal here is to make our vectors of $U$ disappear. We achieve this by left multiplying $A^T$.

Note that $A^TA$ is a symmetric positive definite matrix. 

$$A=U\Sigma V^T \Longleftrightarrow A^T= V \Sigma^T U^T$$
$$A^TA=V \Sigma ^T(U^TU) \Sigma V^T=V \Sigma^T \Sigma V^T$$
$$\Longleftrightarrow A^TA=V  \begin{bmatrix} \sigma_{1}^2\vec{e_{1}}& \sigma_{2}^2\vec{e_{2}} & \dots &\sigma_{n}^2\vec{e_{n}} \end{bmatrix} V^T$$
Just for the sake of convenience I will call the matrix sandwiched between $V$ and $V^T$ as $\Sigma_{v}$.
Thus:
$$A^TA=V\Sigma_{v}V^T$$
Notice that the vectors in $V$ are the eigen vectors of $A^TA$ and $\Sigma_{v}$ consists of the eigen values of $A^TA$.

Likewise the right multiplication of $AA^T$ results in:
$$\Longleftrightarrow AA^T=U  \begin{bmatrix} \sigma_{1}^2\vec{e_{1}}& \sigma_{2}^2\vec{e_{2}} & \dots &\sigma_{n}^2\vec{e_{m}} \end{bmatrix} U^T$$
$$\Longleftrightarrow AA^T=U\Sigma_{u}U^T$$


- - -
## Example
$$A=\begin{bmatrix} 4 & 4\\ -3 & 3 \end{bmatrix}$$
We will look for our $\vec{v_{1}}$,$\vec{v_{2}}$ in the row space of $A$, which is $\mathbb{R}^2$
We will look for our $\vec{u_{1}}$,$\vec{u_{2}}$ in the column space of $A$, which is $\mathbb{R}^2$
And for $\sigma_{1} > 0, \sigma_{2} >0$
$$A \vec{v_{1}}= \sigma_{1} \vec{u_{1}}$$
$$A \vec{v_{2}}= \sigma_{2} \vec{u_{2}}$$
We must compute $A^TA$ and $AA^T$:

$$AA^T= \begin{bmatrix} 32 & 0 \\0 & 18 \end{bmatrix}$$
The eigen values and eigen vectors that correspond to $AA^T$ are:
$\begin{bmatrix} 1 & 1 \end{bmatrix}^T$ with $\lambda_{1} = 32$ and $\begin{bmatrix} 1 & -1 \end{bmatrix}^T$ with $\lambda_{2} = 18$ 
$$A^TA= \begin{bmatrix}25 & 7\\ 7 & 25 \end{bmatrix}$$
The eigen values and eigen vectors that correspond to $A^TA$ are:
$\begin{bmatrix} 1 & 0 \end{bmatrix}^T$ with $\lambda_{1} = 32$ and $\begin{bmatrix} 0 & 1 \end{bmatrix}^T$ with $\lambda_{2} = 18$ 

We can normalize these vectors and thus construct our vector $V$:
$$V=\begin{bmatrix} \sqrt{2} & \sqrt{2}\\ \sqrt{2} & -\sqrt{2} \end{bmatrix}$$

We can use our computed eigen values and eigen vectors to compute our $U$:

$$A=\begin{bmatrix} 4 & 4\\ -3 & 3 \end{bmatrix} = U \Sigma V^T  $$
$$ \Longleftrightarrow A=\begin{bmatrix} 4 & 4\\ -3 & 3 \end{bmatrix} = \begin{bmatrix} 1 & 0\\ 0 & 1 \end{bmatrix} \begin{bmatrix} \sqrt{32} & 0\\ 0 & \sqrt{18} \end{bmatrix} \begin{bmatrix} \sqrt{2} & \sqrt{2}\\ \sqrt{2} & \sqrt{2} \end{bmatrix}  $$