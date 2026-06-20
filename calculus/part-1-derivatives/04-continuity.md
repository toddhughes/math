# Chapter 4 -- Continuity

In Chapter 2 we leaned on a working rule: for most functions you
meet, the limit at a point is just the function's value at that
point. We called the technique **direct substitution** and used it
constantly. This chapter gives that rule its proper name. The
functions for which direct substitution works are called
**continuous**, and continuity is the property that makes most of
calculus work.

This chapter has two main goals. First, to pin down what "continuous"
means precisely, so we can decide it without guesswork. Second, to
catalog the standard ways a function can fail to be continuous --
the four shapes of **discontinuity** -- so we can recognize each one
when it appears. We close with a powerful consequence of continuity
called the Intermediate Value Theorem.

## The picture: a graph drawn without lifting your pencil

The intuitive picture of continuity is simple. A function $f$ is
continuous if you can draw its graph in one unbroken stroke, without
lifting your pencil from the paper. There are no holes, no jumps,
no vertical asymptotes, nothing surprising. Every point on the graph
sits right next to the points just to its left and just to its
right.

The picture is intuitive enough that you can usually tell continuity
at a glance from a graph. The work of this chapter is to translate
the picture into precise algebraic conditions, so we can decide
continuity without drawing anything.

## The formal definition

Pick a function $f$ and a point $x = a$. We say $f$ is **continuous
at $a$** if all three of the following are true:

1. **$f(a)$ is defined.** That is, $a$ is in the domain of $f$, and
   plugging it in gives a real number.
2. **$\displaystyle\lim_{x \to a} f(x)$ exists.** The function has a
   well-defined heading as $x$ approaches $a$ -- in particular, the
   two one-sided limits exist and agree on a finite value.
3. **The heading matches the value.** That is,
   $\displaystyle\lim_{x \to a} f(x) = f(a)$.

The whole package can be summarized in a single equation:

$$\lim_{x \to a} f(x) = f(a).$$

That one line packs all three conditions. Both sides must exist as
real numbers, and they must equal each other. If any of those fails,
the function is **discontinuous** at $a$.

The three-condition version is useful as a diagnostic checklist.
When a function fails to be continuous, it is helpful to know
*which* condition failed; that tells you what kind of discontinuity
you are looking at. We will come back to this when we catalog
discontinuities below.

A function is **continuous on an interval** if it is continuous at
every point of that interval. At an endpoint of the interval, we use
only the appropriate one-sided limit, since you can only approach
the endpoint from one side.

## Checking continuity at a point

Consider:

$$f(x) = \frac{x^2 - 4}{x - 2}.$$

Is $f$ continuous at $x = 2$? Apply the checklist:

1. **Is $f(2)$ defined?** Plug in: $\frac{4 - 4}{2 - 2} = \frac{0}{0}$,
   which is undefined. So $f(2)$ does not exist.

Condition 1 already fails, so $f$ is **not continuous at $x = 2$**.

It is worth going one step further. From Chapter 1 we know that
$\displaystyle\lim_{x \to 2} f(x) = 4$. So the limit *does* exist,
even though the value does not. This is a particular, gentle kind of
discontinuity that we will catalog in a moment.

A second example. Consider:

$$g(x) = \begin{cases} x + 1 & \text{if } x \neq 3, \\ 7 & \text{if } x = 3. \end{cases}$$

This function is defined **piecewise**: it equals $x + 1$ everywhere
except at $x = 3$, where it equals 7.

Is $g$ continuous at $x = 3$? Apply the checklist:

1. **Is $g(3)$ defined?** Yes: by the piecewise definition,
   $g(3) = 7$.
2. **Does the limit exist?** Near $x = 3$ but not at $x = 3$, $g$
   equals $x + 1$. So
   $\displaystyle\lim_{x \to 3} g(x) = 3 + 1 = 4$. The limit exists.
3. **Do they match?** The limit is 4, but $g(3) = 7$. They do not
   match.

So $g$ is **not continuous at $x = 3$**. The function has a definite
heading toward 4, but the actual value at $x = 3$ is 7. There is a
single isolated point that does not fit the surrounding behavior.

## The four kinds of discontinuity

When a function fails to be continuous at a point, the failure has a
shape. There are four standard shapes, and they correspond directly
to the ways the checklist can fail.

### Removable discontinuities

A **removable** discontinuity happens when condition 2 holds (the
limit exists) but condition 1 or condition 3 fails. The limit
exists, but either the value is missing or the value is wrong.

Both examples in the previous section were removable. The first one
($f(x) = (x^2 - 4)/(x - 2)$ at $x = 2$) had no value at all; the
second one ($g$ at $x = 3$) had a value that did not match the
limit.

They are called "removable" because you can *fix* the discontinuity
by redefining the function at that single point. If you set
$f(2) = 4$ in the first example, or $g(3) = 4$ in the second, both
functions become continuous. The discontinuity is just a hole or a
misplaced point in an otherwise well-behaved graph.

### Jump discontinuities

A **jump** discontinuity happens when condition 2 fails because the
two one-sided limits both exist but disagree. The function has a
definite heading on each side, but the two headings are different.
The graph literally jumps from one level to another.

The postage example from Chapter 1 is a jump:

$$\lim_{x \to 1^-} s(x) = 50, \qquad \lim_{x \to 1^+} s(x) = 75.$$

The graph drops up from 50 to 75 at $x = 1$. You cannot fix this by
redefining $s$ at one point; no value would make the function
continuous, because the function disagrees with itself from the two
sides.

### Infinite discontinuities

An **infinite** discontinuity happens at a vertical asymptote.
Condition 2 fails because at least one of the one-sided limits is
$\pm\infty$. Recall from Chapter 3 that $\infty$ is not a number, so
the limit does not exist in any literal sense.

The classic example is $f(x) = 1/x$ at $x = 0$. The right-side limit
is $+\infty$ and the left-side limit is $-\infty$. The function is
undefined at $x = 0$ as well; even if you tried to assign it a
value, the behavior nearby is unmanageable.

The function $1/x^2$ at $x = 0$ has an infinite discontinuity too,
even though both one-sided limits agree (both head to $+\infty$).
The function still blows up; there is no finite value the function
could be assigned at $x = 0$ to make it continuous.

### Oscillating discontinuities

The rarest case is an **oscillating** discontinuity, where the
function does not approach any single value but instead wiggles
between values infinitely many times as $x$ approaches $a$. The
standard example is $f(x) = \sin(1/x)$ near $x = 0$: as $x$ gets
close to 0, the value $1/x$ gets huge, and $\sin(1/x)$ oscillates
between $-1$ and $1$ faster and faster, never settling. There is no
heading; the function keeps changing its mind.

Oscillating discontinuities do not appear often in introductory
calculus, but it is worth knowing the case exists.

## Which functions are continuous?

You do not have to check the three conditions for every function you
meet. Most of the standard functions are continuous wherever they
are defined, and continuity is preserved by the usual ways of
combining functions. Here is the working knowledge.

**Standard functions, continuous on their natural domains:**

- Every **polynomial** (such as $x^2 - 3x + 5$) is continuous
  everywhere.
- Every **rational function** (a ratio of polynomials) is continuous
  everywhere its denominator is nonzero.
- $\sin x$ and $\cos x$ are continuous everywhere.
- $\tan x$, $\sec x$, $\csc x$, and $\cot x$ are continuous on their
  domains; they have discontinuities at the points where their
  denominators are zero.
- $e^x$ is continuous everywhere.
- $\ln x$ is continuous for all $x > 0$ (it is not defined for
  $x \leq 0$).
- $\sqrt[n]{x}$ is continuous everywhere if $n$ is odd, and for
  $x \geq 0$ if $n$ is even.

**Combinations of continuous functions are continuous.** If $f$ and
$g$ are both continuous at $a$, then so are:

- $f + g$, $f - g$, and $f \cdot g$.
- $f / g$, provided $g(a) \neq 0$.
- The composition $f(g(x))$, provided $g(a)$ is in the domain of
  $f$.

These rules follow directly from the limit laws of Chapter 2; they
are those laws restated through the definition of continuity.
Together they cover essentially every function you can build out of
elementary pieces.

This is a large practical shortcut. To check continuity of, say,

$$h(x) = \frac{\sin(x^2)}{x - 5}$$

at $x = 2$, you do not need to compute any limits. You just observe
that $h$ is built out of continuous functions (sine, the polynomial
$x^2$, and the polynomial $x - 5$) by composition and division. The
only place to worry about is wherever the denominator equals zero,
namely $x = 5$. Everywhere else -- including at $x = 2$ -- $h$ is
continuous, and direct substitution gives the limit.

## The Intermediate Value Theorem

We are going to meet several theorems in this book that rest on the
assumption of continuity. The first one, and the most intuitive, is
the **Intermediate Value Theorem** (often abbreviated IVT).

The statement:

> If $f$ is continuous on the closed interval $[a, b]$, and $N$ is
> any number between $f(a)$ and $f(b)$, then there exists at least
> one number $c$ in the open interval $(a, b)$ with $f(c) = N$.

In plain English: a continuous function cannot skip values. If it
starts at one height and ends at another, then somewhere along the
way it must take every height in between.

The intuition matches the no-lifting-the-pencil picture. If you
start your pencil at height $f(a)$ and end at height $f(b)$ without
ever lifting it, then at some point your pencil must have been at
every height between $f(a)$ and $f(b)$. Continuity is exactly what
guarantees this.

### A use: finding roots

Here is a small but useful application. Suppose you want to know
whether the equation

$$x^3 - x - 1 = 0$$

has a solution.

Let $f(x) = x^3 - x - 1$. This is a polynomial, so it is continuous
everywhere. Try two values:

- $f(1) = 1 - 1 - 1 = -1$.
- $f(2) = 8 - 2 - 1 = 5$.

So $f(1) < 0 < f(2)$. By the IVT, since $f$ is continuous on
$[1, 2]$ and $0$ is between $f(1) = -1$ and $f(2) = 5$, there must
be some number $c$ in $(1, 2)$ with $f(c) = 0$. The equation has a
root somewhere between 1 and 2.

The IVT does not tell us *where* the root is. It only guarantees
that one exists. But knowing a root exists is sometimes exactly what
you need, and the trick of checking signs of $f$ at two points is
the foundation of the standard numerical methods for finding roots
to any desired precision.

## What to take away from this chapter

- A function $f$ is **continuous at $a$** if
  $\displaystyle\lim_{x \to a} f(x) = f(a)$. This single equation
  carries three requirements: $f(a)$ exists, the limit exists, and
  the two are equal.
- A function fails to be continuous in one of four standard ways:
  - **Removable**: the limit exists but the value is missing or
    does not match.
  - **Jump**: the two one-sided limits exist but disagree.
  - **Infinite**: the function blows up at a vertical asymptote.
  - **Oscillating**: the function does not settle on any value.
- All standard functions (polynomials, rationals, trig, exp, log,
  roots) are continuous on their natural domains, and continuity is
  preserved by sums, differences, products, quotients (where the
  denominator is nonzero), and compositions. Most functions you can
  write down are therefore continuous wherever their expression
  makes sense.
- The **Intermediate Value Theorem** says that a continuous function
  on $[a, b]$ takes every value between $f(a)$ and $f(b)$ somewhere
  on $(a, b)$. It is the formal version of "you cannot skip a value
  if you cannot lift your pencil."

Continuity is the property that lets calculus work cleanly. With it
pinned down, we are ready to define the central object of Part 1 --
the **derivative** -- which is itself a particular kind of limit.

## Coming up next

[Chapter 5 -- The Derivative](05-the-derivative.md)
