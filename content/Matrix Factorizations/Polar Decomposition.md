---
title: Polar Decomposition
draft: "false"
tags:
---
# Polar Decomposition 

Every matrix, $A$ can be factored into some $SQ$ where $S$ is a symmetric matrix and $Q$ is an orthogonal matrix. 

We can obtain this result from SVD:
$$A= U \Sigma V^T = U \Sigma U^T U V^T$$
Notice that $U \Sigma U^T$ is a symmetric matrix and that $UV^T$ is orthogonal because the product of two orthogonal matrices is another orthogonal matrix. 
