---
title: Normal Matrices
draft: "false"
tags:
---
# Normal Matrices 

A normal matrix, $A \in \mathbb{C}^{n \times n}$ is normal if $A^HA=AA^H$. 

We know that unitary matrices, Hermitian matrices, skew-Hermitian matrices, and  diagonal matrices are also normal matrices.

If $A$ is a unitary matrix, then $A^HA=I_{n}$ and $AA^H=I_{n}$ then $A^HA=AA^H=I_{n} \implies A$ is normal. 

If $A$ is Hermitian then $A^H=A$, so $A^HA=A^2$ and $AA^H=A^2$ so $AA^H=A^HA=A^2 \Longrightarrow A$ is normal

If $A$ is Skew-Hermitian then $A^H=-A$ so $A^HA=-A^2$ and $AA^H=-A^2 \implies AA^H=A^HA=-A^2$ is normal  

If $A$ is Diagonal then $A^H=A$, so $A$ is Hermitian, so $A$ is normal

---

# Complex Spectral Decomposition 

Suppose $A \in \mathbb{C}^{n \times n}$ then exists a unitary matrix $U,D \in \mathbb{C}^{n\times n}$ where $U$ is orthogonal and $D$ is a diagonal matrix such that we can express $A$ as:

$$A=UDU^H$$

$\textbf{if and only if } A$ is normal. 

## Proof 

Case 1. If $A=UDU^H$ then $A$ is normal:

$$AA^H=(UDU^H)(UDU^H)^H=UDU^HUD^H=U$$

