# Part 2 -- Vector Spaces and Linear Transformations

This part lifts the concrete tools from Part 1 into the abstract
setting where linear algebra truly lives.

Until now, "vector" has meant a list of $n$ real numbers, and
"matrix" has meant a rectangular grid of real numbers. Those are the
most familiar examples, but they are only examples. In Part 2 we
identify the structural features that make a set of objects act like
vectors, and the parallel features that make a function act like a
matrix. The abstract definitions free linear algebra from being
exclusively about lists of numbers, and they reveal that the
calculations of Part 1 were special cases of a much more general
story.

The arc of Part 2:

1. We define the **vector space**, the abstract setting that
   $\mathbb{R}^n$ is one example of. Many other things turn out to
   be vector spaces too: polynomials, continuous functions, the set
   of all $m \times n$ matrices, and more.
2. Within a vector space, certain subsets are themselves vector
   spaces. We call them **subspaces** and learn to recognize them.
3. We develop the core organizing concepts of linear algebra:
   **linear combinations**, **span**, **linear independence**,
   **basis**, and **dimension**. Together they pin down what it
   means for a set of vectors to be "minimal but sufficient" to
   describe everything in the space.
4. We introduce **coordinates** relative to a basis and learn what
   happens when we change to a different basis. The same vector has
   different coordinates depending on which basis we use.
5. We meet **linear transformations**, the right notion of
   "function" between vector spaces. A function is a linear
   transformation when it respects addition and scaling -- the two
   operations that define vector-space structure.
6. Every linear transformation between finite-dimensional vector
   spaces can be encoded as a **matrix**, but only after a choice of
   basis. Different bases give different matrices for the *same*
   transformation. This realization unifies matrices and linear
   transformations as two views of one object.
7. We meet the **four fundamental subspaces** of a matrix -- the
   column space, the row space, the null space, and the left null
   space -- and the central **rank-nullity theorem** that ties
   their dimensions together.

By the end of Part 2 you will see linear algebra as a single
coherent theory rather than a collection of computational tricks,
and you will see why matrices and linear transformations are the
same thing in different clothing.

## Table of contents

The marker next to each chapter shows whether it has been written:

- `[x]` written and available
- `[ ]` planned, not yet written

Chapters:

- [ ] Chapter 1 -- Vector Spaces
- [ ] Chapter 2 -- Subspaces
- [ ] Chapter 3 -- Linear Combinations and Span
- [ ] Chapter 4 -- Linear Independence
- [ ] Chapter 5 -- Bases and Dimension
- [ ] Chapter 6 -- Coordinates and Change of Basis
- [ ] Chapter 7 -- Linear Transformations
- [ ] Chapter 8 -- The Matrix of a Linear Transformation
- [ ] Chapter 9 -- Range, Null Space, and Rank
- [ ] Chapter 10 -- The Four Fundamental Subspaces
