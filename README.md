# Spectral Theorem, Rayleigh Quotient, and Eckart–Young Theorem

## Overview

This project develops the mathematical foundations of **Principal Component Analysis (PCA)** using three fundamental results from linear algebra and matrix analysis:

- **Spectral Theorem**
- **Rayleigh Quotient**
- **Eckart–Young Theorem**

The project focuses on the mathematics behind PCA rather than treating it as a black-box computational method.

The theoretical results are first established through proofs and proof sketches, and are then **numerically verified using a from-scratch PCA implementation in R**.

## Mathematical Foundations

### 1. Spectral Theorem

The spectral theorem states that every real symmetric matrix can be orthogonally diagonalised:

\[
A = Q\Lambda Q^T.
\]

Since a covariance matrix is symmetric, this theorem guarantees that its eigenvalues are real and that its eigenvectors can be chosen to form an orthonormal basis.

This provides the mathematical foundation for the eigendecomposition used in PCA.

### 2. Rayleigh Quotient

For a covariance matrix \(\Sigma\) and a unit vector \(v\), the variance of the data projected onto \(v\) is

\[
v^T\Sigma v.
\]

The Rayleigh quotient establishes that

\[
\max_{\|v\|=1} v^T\Sigma v = \lambda_{\max}.
\]

Therefore, the eigenvector corresponding to the largest eigenvalue gives the direction of **maximum variance**.

The subsequent principal components are obtained from the remaining orthogonal eigenvectors.

### 3. Eckart–Young Theorem

PCA can also be viewed as a **low-rank approximation problem**.

Using the singular value decomposition,

\[
X = U\Sigma V^T,
\]

the first \(k\) singular components produce a rank-\(k\) approximation

\[
X_k = U_k\Sigma_kV_k^T.
\]

The Eckart–Young theorem shows that this truncated SVD provides an optimal rank-\(k\) approximation under the appropriate matrix norm.

This gives PCA a rigorous mathematical justification as a dimensionality-reduction and approximation method.

## Computational Verification

The R implementation performs PCA from scratch by:

1. Centering the data.
2. Computing the covariance matrix.
3. Performing eigendecomposition.
4. Ordering eigenvalues and eigenvectors.
5. Calculating explained variance.
6. Projecting observations onto principal components.
7. Reconstructing the data using reduced dimensions.
8. Comparing numerical results with the theoretical predictions.

The code is intended to **verify the mathematics rather than replace the proofs**.

## Key Learning Outcomes

This project demonstrates understanding of:

- Eigenvalues and eigenvectors
- Symmetric matrices
- Orthogonal diagonalisation
- Spectral theorem
- Rayleigh quotient
- Singular Value Decomposition
- Constrained optimisation
- Principal Component Analysis
- Low-rank approximation
- Eckart–Young theorem
- Numerical linear algebra
- Mathematical proof and verification

## Limitations

The proofs are presented primarily as **proof sketches** rather than fully formal textbook proofs. In particular, the Eckart–Young optimality argument is abbreviated.

A future version could strengthen the project by providing a complete proof of the theorem and a more detailed treatment of the assumptions and matrix norms involved.

## Purpose

This project is part of a **Pure Mathematics portfolio** and is designed to demonstrate the ability to connect abstract mathematical theory with computation.

The central principle is:

> **Prove the mathematics first, implement it second, and use computation to verify the theoretical result.**

## Tools

- R
- Base R linear algebra
- Eigendecomposition
- Singular Value Decomposition (SVD)
- Numerical verification
