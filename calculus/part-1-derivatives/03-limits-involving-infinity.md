# Chapter 3 -- Limits Involving Infinity

Up to now, the limits we have computed have had two things in common:
the input was approaching a finite value, and the output was settling
on a finite value too. Both assumptions are reasonable for the kinds
of functions we have looked at, but they are not the only interesting
cases.

This chapter handles the cases where **infinity** enters the picture.
There are two genuinely different ways it can show up:

- The **output blows up**. As the input approaches some finite value,
  the function's value grows past every bound. The graph has a
  *vertical asymptote* there.
- The **input itself goes to infinity**. We ask what happens to the
  function as $x$ marches off toward $\infty$ or $-\infty$. The
  function may settle on a finite value (a *horizontal asymptote*),
  or it may grow without bound itself.

We will take these one at a time. They look similar in notation but
are genuinely different ideas, and we will keep them separate.

Throughout, keep one thing in mind: $\infty$ is **not a number**. You
cannot add to it, subtract from it, multiply by it, or plug it into a
function. It is shorthand for "growing without bound." We will come
back to this at the end of the chapter and pin down what the shorthand
really means, but it is worth knowing up front.

## When the output blows up

The classic example is the function

$$f(x) = \frac{1}{x^2}$$

near $x = 0$.

Try direct substitution: $\frac{1}{0^2} = \frac{1}{0}$, which is not
a number. This looks like trouble, but it is a *different* kind of
trouble from the $\frac{0}{0}$ indeterminate form. Here the
denominator is heading to zero while the numerator stays put at 1.
Dividing a fixed positive number by something tiny gives something
huge -- and the smaller the denominator, the larger the result.

A quick table makes it concrete:

| $x$    | $f(x) = 1/x^2$  |
|--------|-----------------|
| 0.1    | 100             |
| 0.01   | 10,000          |
| 0.001  | 1,000,000       |
| -0.001 | 1,000,000       |
| -0.01  | 10,000          |
| -0.1   | 100             |

From both sides, the function is heading toward $+\infty$. We write:

$$\lim_{x \to 0} \frac{1}{x^2} = \infty.$$

The equals sign here is informal. It does not mean the limit "exists
and equals a number called infinity." It means: as $x$ approaches 0,
the value of $1/x^2$ grows past every bound you might name. We will
come back to this point at the end of the chapter.

### One-sided limits, formally

Sometimes a function blows up only on one side of the trouble point,
or it blows up in different directions from each side. To talk
precisely about this, we introduce the **one-sided** limit notation.

- $\displaystyle\lim_{x \to a^+} f(x)$ means "the limit as $x$
  approaches $a$ from the **right**" -- that is, from values greater
  than $a$.
- $\displaystyle\lim_{x \to a^-} f(x)$ means "the limit as $x$
  approaches $a$ from the **left**" -- from values less than $a$.

The little $+$ and $-$ floating in the exponent position are read as
"from above" and "from below."

We mentioned in Chapter 1 that a two-sided limit
$\displaystyle\lim_{x \to a} f(x)$ exists exactly when the two
one-sided limits exist *and* agree. With the new notation, that fact
takes a clean form:

$$\lim_{x \to a} f(x) = L \quad \text{if and only if} \quad \lim_{x \to a^-} f(x) = L \;\text{ and }\; \lim_{x \to a^+} f(x) = L.$$

If the two sides disagree, or if either of them fails to exist, the
two-sided limit does not exist.

### Different blow-up on different sides

The cleanest example of disagreeing one-sided limits is $f(x) = 1/x$
near $x = 0$.

Approach from the right (positive values of $x$):

$$\frac{1}{0.1} = 10, \quad \frac{1}{0.01} = 100, \quad \frac{1}{0.001} = 1000, \;\ldots$$

Heading to $+\infty$. So:

$$\lim_{x \to 0^+} \frac{1}{x} = \infty.$$

Approach from the left (negative values of $x$):

$$\frac{1}{-0.1} = -10, \quad \frac{1}{-0.01} = -100, \quad \frac{1}{-0.001} = -1000, \;\ldots$$

Heading to $-\infty$. So:

$$\lim_{x \to 0^-} \frac{1}{x} = -\infty.$$

The two sides disagree about *which* infinity they are heading
toward. So the two-sided limit $\displaystyle\lim_{x \to 0} \frac{1}{x}$
**does not exist**. It would be misleading to write
$\lim_{x \to 0} \frac{1}{x} = \infty$ in this case, because the left
side is heading in the opposite direction.

### How to spot an infinite limit

In algebraic terms, the signal of an infinite limit is "**nonzero
over zero**" from direct substitution. That is, the denominator goes
to zero but the numerator does not.

Compare this with the indeterminate form $\frac{0}{0}$ from Chapter 2.
The two look superficially similar but mean very different things:

- $\frac{0}{0}$ from direct substitution: the algebra is unfinished.
  Rewrite and try again. The limit could be anything.
- $\frac{C}{0}$ with $C \neq 0$: this is an infinite limit. The
  function is blowing up. You only need to figure out the sign
  (whether it heads to $+\infty$ or $-\infty$, and whether the two
  sides agree).

To figure out the sign, look at the signs of the numerator and
denominator near the trouble point.

A quick example. Compute $\displaystyle\lim_{x \to 2} \frac{1}{(x - 2)^2}$.

Direct substitution gives $\frac{1}{0}$, nonzero over zero, so it is
an infinite limit. The numerator is 1, which is positive. The
denominator is $(x - 2)^2$, which is a square, so it is always
positive (and tiny near $x = 2$). Positive divided by tiny positive
is a large positive number, so:

$$\lim_{x \to 2} \frac{1}{(x - 2)^2} = \infty.$$

Both sides give the same answer because the square does not care
which side $x$ is on.

Now a trickier example where the two sides disagree. Compute
$\displaystyle\lim_{x \to 3} \frac{x + 1}{x - 3}$.

Direct substitution gives $\frac{4}{0}$. Infinite limit. The
numerator is $x + 1$, which is close to 4 near $x = 3$, so it is
positive on both sides. The denominator is $x - 3$, which is positive
when $x$ is slightly greater than 3 and negative when $x$ is slightly
less.

- Approach from the right: positive over tiny positive, heading to
  $+\infty$. So $\displaystyle\lim_{x \to 3^+} \frac{x + 1}{x - 3} = \infty$.
- Approach from the left: positive over tiny negative, heading to
  $-\infty$. So $\displaystyle\lim_{x \to 3^-} \frac{x + 1}{x - 3} = -\infty$.

The two sides disagree, so the two-sided limit does not exist.

### Vertical asymptotes

When a function blows up at a point $x = a$, the vertical line
$x = a$ is called a **vertical asymptote** of the graph. The graph
hugs that line but never touches it.

- The function $1/x^2$ has a vertical asymptote at $x = 0$, with both
  branches of the graph shooting upward toward it.
- The function $1/x$ also has a vertical asymptote at $x = 0$, but
  the right branch heads up to $+\infty$ while the left branch dives
  down to $-\infty$.

In general, a rational function has a vertical asymptote at every
value of $x$ that makes the denominator zero, assuming no common
factor between numerator and denominator that would cancel the
trouble.

## When the input goes to infinity

The other way infinity enters a limit is in the input. We ask: as
$x$ grows without bound, what happens to $f(x)$?

The notation is:

$$\lim_{x \to \infty} f(x) = L,$$

read as "the limit of $f(x)$ as $x$ approaches infinity equals $L$."
The same warning applies as before: $x$ does not actually *reach*
infinity. The notation is shorthand for "as $x$ grows past every
bound."

### The fundamental building block

The most useful single limit at infinity is:

$$\lim_{x \to \infty} \frac{1}{x} = 0.$$

The intuition is just the converse of what we saw at $x = 0$. When
the denominator is huge, the fraction is tiny, and "tiny" approaches
zero. A small table makes this clear:

| $x$        | $1/x$       |
|------------|-------------|
| 10         | 0.1         |
| 100        | 0.01        |
| 1,000      | 0.001       |
| 1,000,000  | 0.000001    |

Unmistakably heading to 0.

The same is true for higher powers. For any positive integer $n$:

$$\lim_{x \to \infty} \frac{1}{x^n} = 0.$$

The higher the power, the faster the fraction shrinks, but they all
head to zero.

### Rational functions at infinity

The most common situation in practice is a ratio of two polynomials,
and the question is what happens far out. The technique is uniform:
**divide every term on the top and the bottom by the highest power
of $x$ that appears in the denominator.** That step turns every
term into either a constant or something of the form $1/x^n$, all of
which we know how to handle.

Here is the technique in action three times, illustrating three
different outcomes.

**Equal degrees: the leading coefficients win.** Compute:

$$\lim_{x \to \infty} \frac{3x^2 + 5}{x^2 + 2x + 1}.$$

The highest power of $x$ in the denominator is $x^2$. Divide every
term by $x^2$:

$$\frac{3x^2 + 5}{x^2 + 2x + 1} = \frac{\dfrac{3x^2}{x^2} + \dfrac{5}{x^2}}{\dfrac{x^2}{x^2} + \dfrac{2x}{x^2} + \dfrac{1}{x^2}} = \frac{3 + \dfrac{5}{x^2}}{1 + \dfrac{2}{x} + \dfrac{1}{x^2}}.$$

Now take the limit. Every $1/x^n$ term goes to 0:

$$\lim_{x \to \infty} \frac{3 + \dfrac{5}{x^2}}{1 + \dfrac{2}{x} + \dfrac{1}{x^2}} = \frac{3 + 0}{1 + 0 + 0} = 3.$$

So $\displaystyle\lim_{x \to \infty} \frac{3x^2 + 5}{x^2 + 2x + 1} = 3$.

**Smaller top: the denominator wins.** Compute:

$$\lim_{x \to \infty} \frac{2x + 1}{x^2 - 5}.$$

The highest power in the denominator is $x^2$. Divide:

$$\frac{2x + 1}{x^2 - 5} = \frac{\dfrac{2x}{x^2} + \dfrac{1}{x^2}}{\dfrac{x^2}{x^2} - \dfrac{5}{x^2}} = \frac{\dfrac{2}{x} + \dfrac{1}{x^2}}{1 - \dfrac{5}{x^2}}.$$

Take the limit:

$$\lim_{x \to \infty} \frac{\dfrac{2}{x} + \dfrac{1}{x^2}}{1 - \dfrac{5}{x^2}} = \frac{0 + 0}{1 - 0} = 0.$$

So $\displaystyle\lim_{x \to \infty} \frac{2x + 1}{x^2 - 5} = 0$.

**Larger top: the function blows up.** Compute:

$$\lim_{x \to \infty} \frac{x^3 + 1}{x^2 - 4}.$$

The highest power in the denominator is still $x^2$. Divide:

$$\frac{x^3 + 1}{x^2 - 4} = \frac{\dfrac{x^3}{x^2} + \dfrac{1}{x^2}}{\dfrac{x^2}{x^2} - \dfrac{4}{x^2}} = \frac{x + \dfrac{1}{x^2}}{1 - \dfrac{4}{x^2}}.$$

Now look at what happens as $x \to \infty$. The top contains a bare
$x$, which itself heads to $+\infty$. The bottom heads to 1. So the
whole expression heads to $\infty$:

$$\lim_{x \to \infty} \frac{x^3 + 1}{x^2 - 4} = \infty.$$

The function grows without bound.

### The three-degree pattern

The three examples above illustrate a general fact about rational
functions at infinity. Write

- $p$ = the degree (highest power) of the numerator polynomial,
- $q$ = the degree of the denominator polynomial.

Then $\displaystyle\lim_{x \to \infty} \frac{\text{numerator}}{\text{denominator}}$
depends only on the comparison of $p$ and $q$:

- **$p < q$**: the limit is 0. The denominator wins.
- **$p = q$**: the limit is the ratio of the leading coefficients.
  Top and bottom balance.
- **$p > q$**: the limit is $\pm\infty$. The numerator wins.

You do not need to memorize this. If you can do the divide-by-highest-power
algebra, you can derive the right answer fresh every time. But once
you see the pattern, you can often read the limit off by glancing at
the degrees.

### Limits as $x \to -\infty$

Everything above also makes sense if $x$ grows in the negative
direction:

$$\lim_{x \to -\infty} f(x) = L$$

is read as "the limit of $f(x)$ as $x$ approaches negative infinity
equals $L$." The technique is identical: divide by the highest power
in the denominator and let each $1/x^n$ go to zero. The fact that
$1/x^n \to 0$ holds whether $x$ is large positive or large negative.

The one thing to be careful about is sign. If the limit turns out to
involve a bare $x$ or an odd power of $x$, the sign of the answer
depends on whether $x$ is heading to $+\infty$ or $-\infty$. For the
third example above, $x^3$ heads to $+\infty$ as $x \to \infty$ but
to $-\infty$ as $x \to -\infty$. So:

$$\lim_{x \to -\infty} \frac{x^3 + 1}{x^2 - 4} = -\infty.$$

### Horizontal asymptotes

If $\displaystyle\lim_{x \to \infty} f(x) = L$ for some finite $L$,
the horizontal line $y = L$ is called a **horizontal asymptote** of
the graph. As you move out to the right, the graph approaches that
horizontal level and stays close to it. Likewise on the left, if
$\displaystyle\lim_{x \to -\infty} f(x)$ is finite.

A function can have a horizontal asymptote on the right, on the
left, on both sides (possibly at different heights), or on neither
side. The asymptotes you find by computing the two limits at
infinity describe the global, far-out behavior of the function.

## Infinity is not a number

We have been writing equations like $\lim_{x \to 0} \frac{1}{x^2} = \infty$
freely, but it is worth being explicit about what that equals sign is
doing.

$\infty$ is not a number. It is not somewhere on the number line
between, say, $10^{100}$ and "even bigger." It is shorthand for the
behavior "growing without bound." Anything you might try to do
arithmetically with infinity -- adding, subtracting, dividing -- is
either undefined or requires careful, separate justification.

When we write $\lim_{x \to a} f(x) = \infty$, the equals sign is
informal. We are using it to describe *how* the limit fails to exist
as a real number. Technically, the limit does not exist; we are
using the $\infty$ symbol to give a more informative reason than "it
does not exist." Compare:

- $\displaystyle\lim_{x \to 4} (x + 1) = 5$: the limit *exists* and
  *equals* the real number 5. The equals sign is literal.
- $\displaystyle\lim_{x \to 0} \frac{1}{x^2} = \infty$: the limit
  *does not* exist as a real number. The equals sign is informal
  shorthand for "the function grows past every bound."
- $\displaystyle\lim_{x \to \infty} \frac{1}{x} = 0$: the limit
  *exists* and *equals* the real number 0. The equals sign is
  literal here too. Even though the $\infty$ on the left is informal,
  the 0 on the right is a real number.

This distinction matters for one practical reason: the limit laws
from Chapter 2 (limit of a sum, product of limits, and so on) apply
only when all the limits involved are finite. They can go wrong if
you try to apply them to infinite limits. For example,

$$\text{``}\infty - \infty\text{''} = \;?$$

has no well-defined value. It is another kind of indeterminate form,
and it requires real work to evaluate. We will meet such forms again
much later, when we discuss L'Hôpital's rule.

## What to take away from this chapter

- $\infty$ is not a number. It is shorthand for "growing without
  bound."
- An **infinite limit**, $\lim_{x \to a} f(x) = \pm\infty$, describes
  the case where the *output* of the function blows up as the input
  approaches a finite value. The graph has a **vertical asymptote**
  at that point.
- The algebraic signal of an infinite limit is "nonzero over zero"
  from direct substitution. This is *not* the same as the
  indeterminate form $\frac{0}{0}$.
- **One-sided limits** $\lim_{x \to a^+}$ and $\lim_{x \to a^-}$ let
  us describe behavior approaching from the right and the left,
  which often differ near a vertical asymptote.
- A **limit at infinity**, $\lim_{x \to \pm\infty} f(x) = L$,
  describes the case where the *input* grows without bound. If $L$
  is finite, the graph has a **horizontal asymptote** at $y = L$.
- The building block for limits at infinity is
  $\displaystyle\lim_{x \to \pm\infty} \frac{1}{x^n} = 0$ for any
  positive integer $n$.
- For rational functions, divide every term by the highest power of
  $x$ in the denominator, then apply the building block. The three
  outcomes depend on how the degree of the top compares with the
  degree of the bottom.

## Coming up next

[Chapter 4 -- Continuity](04-continuity.md)
