# Chapter 2 -- Computing Limits Algebraically

In Chapter 1 we found limits by building tables of values and watching
where the function was heading. That worked, but it is slow, and a
table never quite *proves* what is happening. This chapter teaches
the algebraic shortcuts that let us compute limits in seconds rather
than minutes, and that give us answers we can fully trust.

The plan is straightforward. We start with the easiest case (plug in
and read off the answer), introduce a few rules for combining limits,
and then turn to the troublesome cases where plugging in gives
$\frac{0}{0}$. For those, we will learn three reliable techniques:
factoring, rationalizing, and combining fractions.

## The first thing to try: just plug in

For most functions you will meet, the limit at a point is simply the
function's value at that point. That is, if you can plug in $a$ and
get an ordinary number out, that number *is* the limit:

$$\lim_{x \to a} f(x) = f(a).$$

This is called **direct substitution**. It is the first thing to try
every time, because when it works it gives the answer instantly.

A quick example. Compute:

$$\lim_{x \to 2} (3x^2 + 5).$$

Plug $x = 2$ into the expression: $3(2)^2 + 5 = 12 + 5 = 17$. Done.
The limit is 17.

Another:

$$\lim_{x \to 1} \frac{x + 2}{x - 3}.$$

Plug $x = 1$ into the expression: $\frac{1 + 2}{1 - 3} = \frac{3}{-2}
= -\frac{3}{2}$. The limit is $-\frac{3}{2}$.

Two observations are worth pulling out.

First, direct substitution works for any **polynomial**. If $f$ is a
polynomial, then $\lim_{x \to a} f(x) = f(a)$ for any value of $a$
you like, no exceptions.

Second, direct substitution works for **rational functions** (ratios
of polynomials) as long as the denominator does not become zero. In
the last example, plugging in $x = 1$ gave a denominator of $-2$,
which is fine. If we had asked for the limit at $x = 3$, plugging in
would give us a denominator of zero, which is a different kind of
problem. We will come back to it.

Why does direct substitution work? Because the functions we deal with
are mostly "well-behaved" -- there are no surprise jumps or holes for
the kinds of expressions you build out of arithmetic, powers, roots,
and the standard functions. We will pin this idea down in Chapter 4
under the name **continuity**. For now, take it as a working rule: if
you can plug in and the arithmetic comes out clean, the limit is
whatever you got.

## The limit laws

Sometimes the expression inside a limit is complicated, and breaking
it into pieces is easier than tackling the whole thing at once. The
**limit laws** are the rules that say which kinds of breaking-apart
are allowed. They are essentially: *limits play nicely with
arithmetic*.

In words:

- The limit of a **sum** is the sum of the limits.
- The limit of a **difference** is the difference of the limits.
- The limit of a **product** is the product of the limits.
- The limit of a **quotient** is the quotient of the limits, provided
  the bottom limit is not zero.
- The limit of a **constant times** something is that constant times
  the limit.
- The limit of a **power** is the power of the limit.

In symbols, if $\displaystyle\lim_{x \to a} f(x) = L$ and
$\displaystyle\lim_{x \to a} g(x) = M$, then:

$$\lim_{x \to a} \bigl[f(x) + g(x)\bigr] = L + M.$$

$$\lim_{x \to a} \bigl[f(x) \cdot g(x)\bigr] = L \cdot M.$$

$$\lim_{x \to a} \frac{f(x)}{g(x)} = \frac{L}{M} \quad \text{(provided } M \neq 0\text{).}$$

$$\lim_{x \to a} c \cdot f(x) = c \cdot L \quad \text{for any constant } c.$$

$$\lim_{x \to a} \bigl[f(x)\bigr]^n = L^n.$$

You should not memorize these as rules to recite. The intuition is
enough: anything that does not involve dividing by something heading
to zero can be split apart and reassembled.

An example of how this looks in practice. Compute:

$$\lim_{x \to 4} \frac{x^2 + 3}{\sqrt{x}}.$$

The pieces, taken separately:

- $\displaystyle\lim_{x \to 4} (x^2 + 3) = 16 + 3 = 19$
- $\displaystyle\lim_{x \to 4} \sqrt{x} = \sqrt{4} = 2$

The quotient rule then says:

$$\lim_{x \to 4} \frac{x^2 + 3}{\sqrt{x}} = \frac{19}{2}.$$

In practice you would just plug in 4 and get $19/2$ directly. The
point of going through the laws is to know that you *can* split a
limit apart whenever it helps.

## When direct substitution fails

The interesting case is when plugging in gives you something that is
not a number. Most often, that "something" is $\frac{0}{0}$ -- the
numerator and the denominator both head to zero. We saw this already
in Chapter 1 with

$$\lim_{x \to 1} \frac{x^2 - 1}{x - 1}.$$

Plugging in gives $\frac{0}{0}$, which is meaningless on its own. But
it is also a *signal*: it tells you that the limit is worth a closer
look, and that the algebra has more to say.

A $\frac{0}{0}$ result is called an **indeterminate form**. The name
is fitting. It does not determine an answer on its own. The limit
*might* be zero, or it might be any finite nonzero number, or it
might not exist at all. You cannot tell from $\frac{0}{0}$ alone. You
have to rewrite the expression.

The "rewriting" almost always means: massage the algebra so the
thing that was making the expression $\frac{0}{0}$ can be canceled.
Three techniques handle the vast majority of cases. We will take them
one at a time.

## Technique 1: factor and cancel

When the expression is a ratio of polynomials and direct substitution
gives $\frac{0}{0}$, factoring is usually the move. If both the top
and the bottom equal zero at $x = a$, then both must contain
$(x - a)$ as a factor. Pulling it out and canceling clears the
trouble.

We saw the pattern in Chapter 1. Here is one more example so it is
fresh.

Compute:

$$\lim_{x \to 3} \frac{x^2 - 9}{x - 3}.$$

**Step 1. Try direct substitution.** $\dfrac{9 - 9}{3 - 3} = \dfrac{0}{0}$.
Indeterminate; we need to rewrite.

**Step 2. Factor what you can.** The numerator is a difference of
squares: $x^2 - 9 = (x - 3)(x + 3)$. So:

$$\frac{x^2 - 9}{x - 3} = \frac{(x - 3)(x + 3)}{x - 3}.$$

**Step 3. Cancel the common factor.** For any $x \neq 3$:

$$\frac{(x - 3)(x + 3)}{x - 3} = x + 3.$$

The cancellation is legitimate because $x$ is *approaching* 3, not
equal to 3.

**Step 4. Apply direct substitution to the simplified expression:**

$$\lim_{x \to 3} (x + 3) = 3 + 3 = 6.$$

So $\displaystyle\lim_{x \to 3} \frac{x^2 - 9}{x - 3} = 6$.

The pattern is always the same: the $(x - a)$ that was making the
bottom zero shows up in the top too. Cancel it, and what is left is
well-behaved.

## Technique 2: rationalize with a conjugate

When the expression involves a square root and direct substitution
gives $\frac{0}{0}$, factoring usually does not work directly.
Instead, we multiply the top and the bottom by something carefully
chosen to kill the square root. That something is the **conjugate**.

If you have $\sqrt{A} - B$, its conjugate is $\sqrt{A} + B$.
Multiplying them gives a difference of squares, $A - B^2$, with no
square root in sight. That cancellation is the whole point.

A standard example. Compute:

$$\lim_{x \to 0} \frac{\sqrt{x + 1} - 1}{x}.$$

**Step 1. Try direct substitution.** $\dfrac{\sqrt{1} - 1}{0} = \dfrac{0}{0}$.
Indeterminate.

**Step 2. Multiply the top and bottom by the conjugate of the
numerator,** $\sqrt{x + 1} + 1$:

$$\frac{\sqrt{x + 1} - 1}{x} \cdot \frac{\sqrt{x + 1} + 1}{\sqrt{x + 1} + 1}.$$

Multiplying by $\frac{A}{A}$ is multiplying by 1, so we have not
changed the value of the expression. We have only changed its
appearance.

**Step 3. Multiply out the top.** The product
$(\sqrt{x + 1} - 1)(\sqrt{x + 1} + 1)$ is a difference of squares, so
it equals $(x + 1) - 1 = x$. The bottom is now $x(\sqrt{x + 1} + 1)$:

$$\frac{x}{x \bigl(\sqrt{x + 1} + 1\bigr)}.$$

**Step 4. Cancel the common factor of $x$.** For any $x \neq 0$:

$$\frac{x}{x \bigl(\sqrt{x + 1} + 1\bigr)} = \frac{1}{\sqrt{x + 1} + 1}.$$

**Step 5. Apply direct substitution to the simplified expression:**

$$\lim_{x \to 0} \frac{1}{\sqrt{x + 1} + 1} = \frac{1}{\sqrt{1} + 1} = \frac{1}{2}.$$

So $\displaystyle\lim_{x \to 0} \frac{\sqrt{x + 1} - 1}{x} = \frac{1}{2}$.

The conjugate trick is a small piece of algebraic cleverness, but it
is exactly the right tool for square-root limits. Whenever you see a
square root inside an indeterminate form, multiplying by the
conjugate is almost always the move.

## Technique 3: combine the fractions first

A third indeterminate-form pattern looks like this: a complicated
fraction sitting in the numerator (or denominator) of a larger
fraction. The cure is to combine the inner fractions first, *then*
simplify and cancel.

This pattern shows up constantly in derivative work, so it is worth
seeing now.

Compute:

$$\lim_{h \to 0} \frac{\dfrac{1}{2 + h} - \dfrac{1}{2}}{h}.$$

**Step 1. Try direct substitution.** The top is $\frac{1}{2} - \frac{1}{2} = 0$;
the bottom is $0$. Indeterminate.

**Step 2. Combine the two fractions in the numerator over a common
denominator.** The common denominator of $\frac{1}{2 + h}$ and
$\frac{1}{2}$ is $2(2 + h)$:

$$\frac{1}{2 + h} - \frac{1}{2} = \frac{2}{2(2 + h)} - \frac{2 + h}{2(2 + h)} = \frac{2 - (2 + h)}{2(2 + h)} = \frac{-h}{2(2 + h)}.$$

**Step 3. Substitute back into the original expression.** Dividing by
$h$ is the same as multiplying by $\frac{1}{h}$:

$$\frac{\dfrac{-h}{2(2 + h)}}{h} = \frac{-h}{2(2 + h)} \cdot \frac{1}{h} = \frac{-h}{2h(2 + h)}.$$

**Step 4. Cancel the common factor of $h$.** For any $h \neq 0$:

$$\frac{-h}{2h(2 + h)} = \frac{-1}{2(2 + h)}.$$

**Step 5. Apply direct substitution:**

$$\lim_{h \to 0} \frac{-1}{2(2 + h)} = \frac{-1}{2 \cdot 2} = -\frac{1}{4}.$$

So $\displaystyle\lim_{h \to 0} \frac{\dfrac{1}{2 + h} - \dfrac{1}{2}}{h} = -\frac{1}{4}$.

This kind of limit is going to appear over and over in the next few
chapters, when we define the derivative. It is not a coincidence that
the variable here is called $h$ instead of $x$.

## A workflow for computing limits

Here is the order to try things in, distilled into a short list:

1. **Try direct substitution.** Plug $a$ into the expression. If you
   get an ordinary number, that is the limit. Stop.
2. **If you get $\frac{0}{0}$ (or any other indeterminate form),
   rewrite.** Pick the technique that fits the expression's shape:
   - A **polynomial ratio**? Factor and cancel.
   - A **square root**? Multiply by the conjugate.
   - A **fraction inside a fraction**? Combine the inner fractions
     first.
3. **After rewriting, try direct substitution again.** If the rewrite
   did its job, the simplified expression will give you an ordinary
   number.

That is essentially the whole game for the kinds of limits you will
meet through the rest of Part 1. There are stranger cases too --
limits involving infinity, limits where the denominator heads to zero
but the top does not, limits involving $\sin x / x$ -- and those are
the subjects of the next chapter and the one after.

## What to take away from this chapter

- The first thing to try when computing a limit is **direct
  substitution**: plug in and see what happens.
- For polynomials and most rational functions, direct substitution
  gives the right answer immediately.
- The **limit laws** say that limits respect sums, differences,
  products, quotients (when the denominator's limit is not zero),
  constant multiples, and powers. They let you break a complicated
  limit into easier pieces.
- A $\frac{0}{0}$ result from direct substitution is called an
  **indeterminate form**. It does not give an answer on its own; it
  tells you to rewrite.
- The three most useful rewriting techniques are **factor and
  cancel** (for polynomial ratios), **multiply by the conjugate**
  (for square roots), and **combine the fractions first** (for
  fractions inside fractions). After any of these, direct
  substitution finishes the job.

The whole workflow -- substitute first, rewrite only if you must,
then substitute again -- is enough to compute essentially every
limit you will meet through the rest of Part 1.

## Coming up next

[Chapter 3 -- Limits Involving Infinity](03-limits-involving-infinity.md)
