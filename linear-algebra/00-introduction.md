# Linear Algebra

Welcome. This is a read-along introduction to linear algebra written
for a true beginner. There are no homework problems and no exercises
to do alone. Each chapter walks you through ideas in plain English,
then shows worked examples step by step.

You should be comfortable with everyday arithmetic and basic algebra
(solving equations, manipulating expressions, working with functions).
There is no calculus prerequisite; the two subjects reinforce each
other in many places but neither requires the other.

The rest of this page is two things: a tour of what linear algebra
is and what it is for, and a map of how the book is organized.

## The one-sentence answer

Linear algebra is the mathematics of **linear systems** -- equations,
transformations, and spaces in which adding inputs and scaling them
behaves in a predictable, geometric way.

"Linear" is a deceptively simple word. It means, roughly, that if
you double an input the output doubles too, and if you add two
inputs the outputs add. That sounds restrictive, and in some sense
it is. But linear things are by far the cleanest objects in
mathematics. They are the only kind we really understand in full
generality, and they show up so often in science, engineering, and
computation that an entire branch of mathematics is devoted to them.

## The original problem: solving systems of equations

The original problem that drove the development of linear algebra
is solving systems of equations. Consider:

$$\begin{aligned}
3x + 2y &= 7, \\
x - y &= 1.
\end{aligned}$$

You probably learned in school how to solve a small system like this
by substitution or elimination. But what if you had 10 equations in
10 unknowns? Or 100? Or 1,000,000, which is routine in modern
engineering and machine learning? You need a systematic method that
works no matter how large the system gets.

The systematic answer requires a new object: the **matrix**, a
rectangular grid of numbers that encodes the coefficients of a system
in compact form. Once you have matrices, questions like "does this
system have a solution? how many?" become algebraic questions about
the matrix, and there is a clean algorithm (Gaussian elimination)
that handles any system you throw at it.

## What else linear algebra is good for

That is the original problem. Here are some of the others.

**Geometry and graphics.** Every rotation, reflection, scaling, and
projection in 2D or 3D is a **linear transformation** -- a function
that takes vectors to vectors in a way that respects addition and
scaling. Linear algebra is the language behind computer graphics,
computer vision, and robotics. When a 3D model rotates on your
screen, every vertex is being multiplied by a 3-by-3 matrix.

**Data and prediction.** Modern data analysis is largely linear
algebra in disguise. If you have data about houses (square footage,
age, location, school district) and want to predict prices, the
standard approach is linear regression -- which is the linear
algebra question "find the vector of coefficients that best fits the
data." Principal Component Analysis, the workhorse method for
reducing high-dimensional data to a few key directions, is another
linear algebra technique.

**Engineering and physics.** Structural analysis (will this bridge
stand?), electrical circuits (Kirchhoff's laws form a linear system),
and signal processing (the Fourier transform is linear) all reduce
to linear algebra problems. In quantum mechanics, the entire theory
is built on vectors and operators -- linear algebra in infinite
dimensions.

**Search and recommendation.** Google's original PageRank algorithm
is an eigenvalue computation on a giant matrix encoding the web's
link structure. The recommendation systems on Netflix and Spotify use
matrix factorization (another linear algebra technique) to predict
what you will enjoy.

The thread running through all of this: most useful systems in the
world are *complicated* in detail, but *approximately linear* over
small enough regions. Linear algebra is what lets you analyze that
local linear behavior precisely. Once you have linear algebra,
calculus extends it to nonlinear settings, machine learning
generalizes it to high-dimensional data, and quantum mechanics
generalizes it to infinite dimensions.

## A first peek at notation

You will see two kinds of objects all the way through this book.
There is no need to memorize the notation now, but it is worth
seeing it once.

A **vector** is a list of numbers. We typically write it as a column:

$$\mathbf{v} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}.$$

The vector $\mathbf{v}$ above lives in $\mathbb{R}^3$, read "R-three"
-- the set of all lists of three real numbers. More generally,
$\mathbb{R}^n$ ("R-n") is the set of all lists of $n$ real numbers.
The vector $\mathbf{v}$ has three entries, so it lives in
$\mathbb{R}^3$. Bold lowercase letters denote vectors throughout
this book.

A **matrix** is a rectangular grid of numbers. We typically write it
with a capital letter:

$$A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}.$$

The matrix $A$ has 2 rows and 3 columns, so we call it a
"$2 \times 3$ matrix" (read "two by three"). Matrices encode linear
systems, linear transformations, and many other useful objects.

Much of linear algebra is the study of how these two kinds of
objects interact: multiplying a matrix by a vector, multiplying two
matrices, decomposing a matrix into simpler pieces, and so on.

## How this book is organized

The book is in three parts. Each part is its own folder with its
own introduction and chapters. Read the parts in order; each builds
on the one before.

**[Part 1 -- Vectors, Matrices, and Linear Systems](part-1-vectors-and-matrices/00-introduction.md)**
is the concrete computational foundation. We start with vectors and
their geometry, then turn to systems of linear equations and the
matrix algebra needed to solve them. By the end of Part 1 you will
be able to solve any system of linear equations, perform matrix
arithmetic confidently, decide whether a matrix is invertible, and
reason geometrically about lines and planes in any dimension.

**[Part 2 -- Vector Spaces and Linear Transformations](part-2-vector-spaces/00-introduction.md)**
lifts those concrete tools into the abstract setting where linear
algebra truly lives. We introduce the **vector space**, the general
object that $\mathbb{R}^n$ is just one example of, and the **linear
transformation**, the function type that respects vector-space
structure. We meet the organizing concepts of the subject: linear
independence, span, basis, dimension, and rank. By the end of Part
2 you will see why matrices and linear transformations are the same
thing in different clothing.

**[Part 3 -- Eigenvalues, Orthogonality, and Decompositions](part-3-eigenvalues-and-orthogonality/00-introduction.md)**
synthesizes Parts 1 and 2 into the powerful results that make
linear algebra indispensable across science and computation. We meet
**eigenvalues and eigenvectors**, **inner product spaces**,
**orthogonal projection** and **least squares**, the **spectral
theorem** for symmetric matrices, and the **singular value
decomposition** -- one of the most useful results in all of applied
mathematics. The part closes with a tour of how the tools we have
built power graphics, machine learning, and more.

## How to read this book

- Read the parts in order, and the chapters within each part in
  order. Each piece builds on the last.
- Take your time. Re-read anything that does not click.
- The table of contents in each part's introduction shows which
  chapters have been written so far.

## Where to start

Begin with [Part 1 -- Vectors, Matrices, and Linear Systems](part-1-vectors-and-matrices/00-introduction.md).
