# Part 3 -- Eigenvalues, Orthogonality, and Decompositions

This part synthesizes the computational tools of Part 1 and the
abstract framework of Part 2 into the powerful results that make
linear algebra indispensable across science and computation.

Two big themes run through this part. The first is **eigenvalues
and eigenvectors**: every linear transformation has certain
"natural" directions in which it acts simply -- by stretching,
shrinking, or reflecting -- and those directions reveal the
transformation's underlying structure. The second is
**orthogonality**: the geometric notion of "perpendicular"
generalizes far beyond two and three dimensions, and it turns out to
be the secret ingredient behind many of the most useful algorithms
in numerical mathematics.

The arc of Part 3:

1. We define **eigenvalues** and **eigenvectors** and learn how to
   find them by way of the **characteristic polynomial**.
2. We introduce **diagonalization**: the process of choosing a basis
   of eigenvectors so that a transformation's matrix becomes
   diagonal. Diagonal matrices are dramatically easier to work with
   than general ones, and many problems become trivial once you
   diagonalize.
3. Some matrices have eigenvalues that are not real numbers but
   **complex numbers**. We extend the theory to handle them.
4. We generalize the dot product to **inner product spaces**, which
   let us talk about length and angle in vector spaces other than
   $\mathbb{R}^n$.
5. We meet **orthogonal sets** and **orthonormal bases**, and the
   **Gram-Schmidt process** for turning any basis into an orthonormal
   one.
6. We use orthogonality to develop **orthogonal projection** and
   **least squares**, the foundation of linear regression and many
   other applied techniques.
7. We arrive at the **spectral theorem** for symmetric matrices:
   every symmetric matrix can be diagonalized by an orthonormal
   basis of eigenvectors. This is one of the most important results
   in all of linear algebra.
8. We meet the **singular value decomposition** (SVD), which
   generalizes diagonalization to any matrix at all, not just square
   symmetric ones. SVD is the workhorse of modern numerical linear
   algebra and a cornerstone of data science.
9. The book closes with a tour of **applications**: how the tools
   we have built power computer graphics, search engines, machine
   learning, and more.

By the end of Part 3 you will have a complete and unified view of
linear algebra, from the concrete arithmetic of vectors to the deep
structural theorems that make it the backbone of so much of modern
science and engineering.

## Table of contents

The marker next to each chapter shows whether it has been written:

- `[x]` written and available
- `[ ]` planned, not yet written

Chapters:

- [ ] Chapter 1 -- Eigenvalues and Eigenvectors
- [ ] Chapter 2 -- The Characteristic Polynomial
- [ ] Chapter 3 -- Diagonalization
- [ ] Chapter 4 -- Complex Eigenvalues
- [ ] Chapter 5 -- Inner Product Spaces
- [ ] Chapter 6 -- Orthogonal Sets and Orthonormal Bases
- [ ] Chapter 7 -- The Gram-Schmidt Process
- [ ] Chapter 8 -- Orthogonal Projection and Least Squares
- [ ] Chapter 9 -- The Spectral Theorem
- [ ] Chapter 10 -- The Singular Value Decomposition
- [ ] Chapter 11 -- Applications of Linear Algebra
