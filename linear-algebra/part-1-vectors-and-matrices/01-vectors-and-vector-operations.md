# Chapter 1 -- Vectors and Vector Operations

In the introduction we said a vector is "a list of numbers." That is
true, and it is the definition we will compute with, but it does not
yet say what a vector is *for*. A vector is the right tool whenever
you have a quantity that has both **magnitude** and **direction** --
something you cannot describe with a single number alone. This
chapter introduces vectors, the operations on them, and the two
complementary ways of picturing them.

By the end of the chapter you will be able to add vectors, scale
vectors, subtract vectors, and move comfortably between the
geometric picture and the algebraic computation.

## Why we need vectors

Many quantities in nature and engineering have a direction attached
to them.

- A car's **velocity** is not just "60 mph." It is "60 mph heading
  northwest." If you only know the speed, you cannot say where the
  car will be in five minutes.
- A **force** on an object is not just "10 newtons." It is "10
  newtons pushing to the right." Knowing the strength is not enough;
  you also need to know which way it is pushing.
- The **displacement** from your house to the grocery store is not
  just "2 miles." It is "2 miles, in *that* direction."

A single number cannot capture both magnitude and direction. We need
a richer object. That richer object is the **vector**.

## The geometric picture: vectors as arrows

The cleanest first picture of a vector is an arrow.

Imagine a 2D plane. Pick a starting point and an ending point, and
draw an arrow from one to the other. That arrow has two pieces of
information built in: how long it is (its magnitude) and which way
it points (its direction). That is a vector.

Two arrows represent the **same** vector if they have the same
length *and* the same direction. The starting point does not matter.
An arrow from $(0, 0)$ to $(3, 2)$ and an arrow from $(5, 1)$ to
$(8, 3)$ represent the same vector, because they have the same
length and point the same way.

This is a strange-feeling convention at first, especially if you are
used to arrows in physics where the starting point matters. In pure
linear algebra, only the displacement matters, not where you
started.

## The algebraic picture: vectors as lists of numbers

The geometric picture is good for intuition, but we cannot do
calculations with arrows. We need a way to record a vector that we
can plug into formulas.

Place the arrow with its tail at the origin. Its tip then lands at
some specific point, say $(3, 2)$. Those two coordinates, written
as a column, become the vector itself:

$$\mathbf{v} = \begin{pmatrix} 3 \\ 2 \end{pmatrix}.$$

The vector $\mathbf{v}$ above lives in $\mathbb{R}^2$, the set of
all lists of two real numbers. More generally:

- A vector in $\mathbb{R}^2$ has two entries (it lives in the 2D
  plane).
- A vector in $\mathbb{R}^3$ has three entries (it lives in 3D
  space).
- A vector in $\mathbb{R}^n$ has $n$ entries (it lives in
  $n$-dimensional space, which we cannot draw for $n \geq 4$ but
  which the algebra handles just fine).

The individual entries of a vector are called its **components**.
For $\mathbf{v} = \begin{pmatrix} 3 \\ 2 \end{pmatrix}$, the first
component is 3 and the second is 2.

We will always write vectors as column-shaped lists like the one
above. To save vertical space when discussing a vector inline, we
sometimes write it as a row in parentheses: $\mathbf{v} = (3, 2)$.
The two notations mean the same thing.

Throughout this book, **bold lowercase letters** denote vectors.
So $\mathbf{v}$, $\mathbf{w}$, $\mathbf{x}$ are vectors. Plain
letters like $v_1, v_2, c, k$ are ordinary numbers. In linear
algebra ordinary numbers are usually called **scalars**, because
they are used to scale vectors.

## Two views, one object

The geometric picture (arrow) and the algebraic picture (list of
numbers) are two views of the same thing. From now on, "the vector
$(3, 2)$" means simultaneously:

- The pair of numbers $(3, 2)$, written as a column.
- The arrow from $(0, 0)$ to $(3, 2)$ in the plane, or any parallel
  arrow of the same length.

Whenever we do something to a vector, we can think of it either way.
The algebra tells us *how* to compute. The picture tells us *why*
the answer makes sense. The agreement between the two is one of the
quiet pleasures of linear algebra.

## Vector addition

The first operation we need is addition. Given two vectors
$\mathbf{u}$ and $\mathbf{v}$, we want a third vector
$\mathbf{u} + \mathbf{v}$.

### The algebra

Adding vectors algebraically is simple: add them component by
component.

$$\begin{pmatrix} u_1 \\ u_2 \end{pmatrix} + \begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = \begin{pmatrix} u_1 + v_1 \\ u_2 + v_2 \end{pmatrix}.$$

A concrete example. If $\mathbf{u} = (3, 2)$ and $\mathbf{v} =
(1, 4)$, then:

$$\mathbf{u} + \mathbf{v} = \begin{pmatrix} 3 \\ 2 \end{pmatrix} + \begin{pmatrix} 1 \\ 4 \end{pmatrix} = \begin{pmatrix} 3 + 1 \\ 2 + 4 \end{pmatrix} = \begin{pmatrix} 4 \\ 6 \end{pmatrix}.$$

That is it. The sum of two vectors is the vector you get by adding
their components one at a time. Two vectors can only be added when
they have the same number of components: $\mathbb{R}^2$ vectors
combine only with other $\mathbb{R}^2$ vectors, and so on.

### The geometry: tip to tail

Geometrically, vector addition is the **tip-to-tail rule**. To
compute $\mathbf{u} + \mathbf{v}$:

1. Draw $\mathbf{u}$ as an arrow starting at the origin.
2. Without changing $\mathbf{v}$'s direction or length, place its
   tail at the tip of $\mathbf{u}$.
3. The arrow from the origin to the tip of $\mathbf{v}$ is the sum
   $\mathbf{u} + \mathbf{v}$.

An equivalent way to picture this is the **parallelogram rule**:
draw both $\mathbf{u}$ and $\mathbf{v}$ starting at the origin.
They form two sides of a parallelogram. The diagonal from the
origin to the opposite corner of the parallelogram is
$\mathbf{u} + \mathbf{v}$.

Both rules give the same answer, and both also match the algebraic
answer. If you walk 3 units right and 2 units up (the vector
$\mathbf{u}$), then 1 unit right and 4 units up (the vector
$\mathbf{v}$), you have walked a total of $3 + 1 = 4$ units right
and $2 + 4 = 6$ units up. The result $(4, 6)$ is exactly what the
component sum gives.

This is a beautiful feature of vectors: the algebra and the geometry
agree exactly, and each one explains the other.

### Properties of addition

Vector addition behaves the way ordinary number addition does:

- **Commutative**: $\mathbf{u} + \mathbf{v} = \mathbf{v} + \mathbf{u}$.
- **Associative**: $(\mathbf{u} + \mathbf{v}) + \mathbf{w} = \mathbf{u} + (\mathbf{v} + \mathbf{w})$.

Both follow directly from the fact that vector addition is defined
component by component, and ordinary number addition is commutative
and associative.

## Scalar multiplication

The second operation is **scalar multiplication**: multiplying a
vector by an ordinary number to stretch, shrink, or reverse it.

### The algebra

To multiply a vector by a scalar, multiply every component by that
scalar.

$$c \cdot \begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = \begin{pmatrix} c \cdot v_1 \\ c \cdot v_2 \end{pmatrix}.$$

For example, if $\mathbf{v} = (3, 2)$:

- $2\mathbf{v} = (6, 4)$.
- $\tfrac{1}{2}\mathbf{v} = \bigl(\tfrac{3}{2}, 1\bigr)$.
- $-1 \cdot \mathbf{v} = (-3, -2)$.
- $0 \cdot \mathbf{v} = (0, 0)$.

### The geometry

Geometrically, multiplying a vector $\mathbf{v}$ by a scalar $c$
does the following:

- If $c > 0$: scale the arrow by a factor of $c$, in the same
  direction. ($c = 2$ doubles its length; $c = \tfrac{1}{2}$
  halves it.)
- If $c < 0$: scale the arrow by $|c|$ and flip it to point in
  the opposite direction.
- If $c = 0$: collapse the arrow to a single point at the origin.
  The result is the **zero vector**, written $\mathbf{0}$.

So scalar multiplication changes a vector's *length* and possibly
*flips* it, but never rotates it to a new direction (other than the
exact reverse). A vector and any nonzero scalar multiple of it
point along the same line through the origin.

### Properties of scalar multiplication

For any vectors $\mathbf{u}, \mathbf{v}$ and any scalars $c, d$:

- $c(\mathbf{u} + \mathbf{v}) = c\mathbf{u} + c\mathbf{v}$ (a scalar
  distributes over a vector sum).
- $(c + d)\mathbf{v} = c\mathbf{v} + d\mathbf{v}$ (a sum of scalars
  distributes over a vector).
- $c(d\mathbf{v}) = (cd)\mathbf{v}$ (scalar multiplications compose
  by multiplying the scalars).
- $1 \cdot \mathbf{v} = \mathbf{v}$ (multiplying by 1 changes
  nothing).

Like the addition properties, all of these follow from the
component-by-component definition and the standard properties of
arithmetic with ordinary numbers.

## Vector subtraction and the zero vector

We get vector subtraction for free from the two operations already
defined.

The **negative** of a vector is $-\mathbf{v} = (-1) \cdot \mathbf{v}$
-- the same vector flipped to point the opposite way. Subtracting
one vector from another is just adding the negative:

$$\mathbf{u} - \mathbf{v} = \mathbf{u} + (-\mathbf{v}).$$

Component by component:

$$\begin{pmatrix} u_1 \\ u_2 \end{pmatrix} - \begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = \begin{pmatrix} u_1 - v_1 \\ u_2 - v_2 \end{pmatrix}.$$

For example, $(5, 7) - (1, 3) = (4, 4)$.

Geometrically, $\mathbf{u} - \mathbf{v}$ has a particularly clean
interpretation: if both vectors are drawn starting at the origin,
then $\mathbf{u} - \mathbf{v}$ is the arrow from the tip of
$\mathbf{v}$ to the tip of $\mathbf{u}$. This is the "displacement
from $\mathbf{v}$ to $\mathbf{u}$." It is consistent with the
algebra: translating that displacement back to start at the origin,
its tip lands at $\mathbf{u} - \mathbf{v}$.

The **zero vector**, written $\mathbf{0}$, has every component
equal to 0. It has no length and no direction. In $\mathbb{R}^2$ it
is $(0, 0)$; in $\mathbb{R}^3$ it is $(0, 0, 0)$; and so on. The
zero vector is the identity for addition:

$$\mathbf{v} + \mathbf{0} = \mathbf{v} \quad \text{for any vector } \mathbf{v},$$

and it is the unique vector that satisfies $\mathbf{v} - \mathbf{v}
= \mathbf{0}$ for every $\mathbf{v}$.

## Vectors in higher dimensions

Everything we have defined extends seamlessly to higher dimensions.
A vector in $\mathbb{R}^3$ has three components and represents an
arrow in 3D space:

$$\mathbf{v} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}.$$

We can add two such vectors component by component:

$$\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} + \begin{pmatrix} 4 \\ -1 \\ 0 \end{pmatrix} = \begin{pmatrix} 5 \\ 1 \\ 3 \end{pmatrix},$$

and we can scale them:

$$3 \cdot \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} = \begin{pmatrix} 3 \\ 6 \\ 9 \end{pmatrix}.$$

For $n \geq 4$ we can no longer draw a picture, but the algebra
works exactly the same way. Components multiply, add, and behave
just as you would expect. Linear algebra is genuinely a calculation
in $\mathbb{R}^n$ for any $n$, and the absence of a picture in high
dimensions never gets in the way of computing. Modern machine
learning routinely works with vectors in $\mathbb{R}^{1{,}000{,}000}$
and beyond.

## What "vector" will mean for now

For all of Part 1, "vector" will mean "a list of $n$ real numbers."
That is concrete and computational, and it is enough for everything
in Part 1.

In Part 2 we will discover that other things behave structurally
like vectors too -- polynomials, functions, even matrices themselves
-- and linear algebra will get a more general definition of
"vector" that captures all of them. But that comes later. For now,
vectors are columns of numbers, and they live in $\mathbb{R}^n$.

## What to take away from this chapter

- A **vector** is a quantity with both magnitude and direction.
  Concretely, it is a list of numbers, written as a column. A vector
  in $\mathbb{R}^n$ has $n$ components.
- Vectors have two complementary pictures: an **arrow** (geometric)
  and a **list of numbers** (algebraic). The two pictures always
  agree.
- **Vector addition** is component by component, or equivalently the
  tip-to-tail rule on arrows.
- **Scalar multiplication** multiplies every component by the same
  number. Geometrically, it scales the arrow's length and possibly
  reverses its direction.
- **Subtraction** is just adding the negative, where the negative of
  $\mathbf{v}$ is $-1 \cdot \mathbf{v}$.
- The **zero vector** $\mathbf{0}$ has all components equal to zero
  and is the identity for addition.
- Everything works in any dimension. We cannot draw vectors in
  $\mathbb{R}^n$ for $n \geq 4$, but the algebra is identical and
  computers handle it routinely.

In the next chapter we add a third operation to our toolkit: the
**dot product**. It will give us an algebraic way to measure the
length of a vector and the angle between two vectors -- the
geometry of $\mathbb{R}^n$ in algebraic form.

## Coming up next

[Chapter 2 -- The Dot Product, Length, and Angle](02-the-dot-product-length-and-angle.md) *(not yet written)*
