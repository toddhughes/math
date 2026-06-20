# Chapter 1 -- The Idea of a Limit

In the introduction we said the whole subject of calculus rests on a
single technical move: learning how to talk about "infinitely small"
pieces in a way that gives reliable answers. The tool that makes this
possible is called the **limit**. This chapter is about what a limit
is, why we need one, and how to read the notation.

There is no formal proof-style material in this chapter. We are after
the *idea*; the formal definition can wait.

## The question a limit answers

A limit answers this question:

> As an input gets closer and closer to some value, where is the
> output heading?

That is it. Notice the careful wording. It does not ask, "What is the
output *at* that value?" It asks where the output is *heading*.
Sometimes those two are the same thing. Sometimes they are not. The
whole interest of limits is in the cases where they are not.

## The easy case

Start with a function you can already read. Suppose:

$$f(x) = x + 1.$$

What is $f$ doing near $x = 3$? Pick a few inputs close to 3 and see
what the function gives back:

| $x$    | $f(x) = x + 1$ |
|--------|----------------|
| 2.9    | 3.9            |
| 2.99   | 3.99           |
| 2.999  | 3.999          |
| 3.001  | 4.001          |
| 3.01   | 4.01           |
| 3.1    | 4.1            |

As $x$ creeps in on 3 from either side, $f(x)$ creeps in on 4. We
say:

$$\lim_{x \to 3}\,(x + 1) = 4.$$

Read this out loud as "the limit of $x + 1$ as $x$ approaches 3 is 4."

For this particular function, we could also have just plugged in
$x = 3$ and gotten $3 + 1 = 4$. Same answer. So why bother with a
limit? Because the next example cannot be handled that way.

## The case that forces us to use a limit

Now look at:

$$g(x) = \frac{x^2 - 1}{x - 1}.$$

What happens at $x = 1$? Let us try to plug it in:

$$g(1) = \frac{1^2 - 1}{1 - 1} = \frac{0}{0}.$$

Zero divided by zero is not a number. So $g$ is **undefined** at
$x = 1$. The function has, in a literal sense, a hole there. You
cannot point to a value of $g$ at that input.

But the limit question is different. It does not ask what $g$ *is* at
$x = 1$. It asks where $g$ is *heading* as $x$ creeps toward 1. Let
us tabulate.

| $x$    | $g(x) = (x^2 - 1)/(x - 1)$ |
|--------|----------------------------|
| 0.9    | 1.9                        |
| 0.99   | 1.99                       |
| 0.999  | 1.999                      |
| 1.001  | 2.001                      |
| 1.01   | 2.01                       |
| 1.1    | 2.1                        |

From both sides, $g$ is unmistakably heading toward 2. So we write:

$$\lim_{x \to 1}\,\frac{x^2 - 1}{x - 1} = 2.$$

This is the entire point of the idea. The function does not have a
value at $x = 1$, but the limit still has a perfectly clear answer.
The limit is a way of asking: "If I could not see the function
exactly *at* this input, what would I have to guess the value should
be, based on what is happening nearby?"

For the curious -- and only for the curious -- the reason the table
works so cleanly is that $x^2 - 1$ factors as $(x - 1)(x + 1)$. So
for any $x$ that is not equal to 1, the $(x - 1)$ on top cancels the
$(x - 1)$ on the bottom, leaving $x + 1$. That is why values of $x$
near 1 are giving us values of $g$ near 2. We will lean on this kind
of algebraic simplification later when we compute limits without
having to build a table.

## The notation, piece by piece

Here is the general form:

$$\lim_{x \to a} f(x) = L.$$

- $\lim$ means "the limit of."
- $x \to a$ means "as $x$ approaches the value $a$." The arrow is the
  key bit. It is not "equals," it is "approaches."
- $f(x)$ is the expression you are watching.
- $L$ is the value the expression is heading toward.

So you read the whole thing as:

> The limit of $f(x)$, as $x$ approaches $a$, is $L$.

Three small but important details that follow directly from this:

1. The value $a$ does not need to be in the domain of $f$. We saw
   that already with $g$ at $x = 1$.
2. The value $L$ is not a guess. Either the function has a definite
   heading or it does not.
3. The limit makes no claim about what happens *at* $x = a$. It only
   describes the behavior nearby.

## Approaching from two sides

Here is something subtle. When we wrote $x \to 1$, the table included
values just below 1 *and* values just above 1, and both columns gave
the same heading. That is what we want: the function agrees with
itself from both sides.

But that is not always how it goes. Some functions head one way as
you sneak up from the left, and a different way as you sneak in from
the right. When that happens, we say the limit *does not exist*.

Example. Imagine a function $s(x)$ that is the price of postage in
cents, as a function of the weight $x$ in ounces. For weights up to
and including 1 ounce, postage is 50 cents. The instant you cross 1
ounce, the price jumps to 75 cents.

- Approach $x = 1$ from below (0.9, 0.99, 0.999): the price is 50.
- Approach $x = 1$ from above (1.001, 1.01, 1.1): the price is 75.

The two sides disagree. There is no single value $s$ is "heading
toward" at $x = 1$. We say:

$$\lim_{x \to 1} s(x) \quad \text{does not exist.}$$

This is not a flaw in the idea of a limit. It is the idea working
correctly. The limit reports a heading, and a function with a sudden
jump has two different headings at the jump point. The honest answer
is "no single heading," and that is what "does not exist" means here.

## A worked example, end to end

Let us do one more, slowly. Consider:

$$h(x) = \frac{x^2 - 4}{x - 2}.$$

We want $\displaystyle\lim_{x \to 2} h(x)$.

**Step 1. Try the easy thing first.** Plug $x = 2$ into the
expression and see what comes out:

$$h(2) = \frac{2^2 - 4}{2 - 2} = \frac{0}{0}.$$

Undefined. So we cannot just read the answer off. We have to think
about heading.

**Step 2. Simplify the expression where you can.** Look at the top.
The expression $x^2 - 4$ is a difference of squares, and it factors
as $(x - 2)(x + 2)$. So:

$$h(x) = \frac{(x - 2)(x + 2)}{x - 2}.$$

**Step 3. Cancel, but with a careful note.** For any $x$ that is *not*
equal to 2, the factor of $(x - 2)$ on top and the factor of $(x - 2)$
on the bottom cancel each other, leaving:

$$h(x) = x + 2 \quad \text{for any } x \neq 2.$$

We are allowed to do this cancellation because $x$ is *approaching*
2, not equal to 2. Inside a limit, that distinction is exactly what
saves us.

**Step 4. Read off the heading.** Now the question is easy. As $x$
approaches 2, the expression $x + 2$ approaches $2 + 2 = 4$. So:

$$\lim_{x \to 2} \frac{x^2 - 4}{x - 2} = 4.$$

Notice what we did and did not do. We never plugged $x = 2$ into the
original $h(x)$. We did not have to. The limit asks about heading,
and the heading is 4.

## Why this matters

This may all feel like setup, and it is. Here is the payoff.

Calculus needs to talk about "the rate of change at one instant" and
"the area under a curve." Both ideas, when you try to write them down
honestly, involve dividing something by an interval that is shrinking
to zero, or adding up infinitely many pieces that are themselves
shrinking to zero. Neither thing makes sense in ordinary arithmetic.

The limit is the bridge. It is how we say "as the interval shrinks
toward zero" or "as the number of pieces grows toward infinity"
without ever having to actually reach zero or infinity. We sneak up
on the answer.

That is the whole game. The derivative, when we get to it, will be a
particular kind of limit. The integral will be a different particular
kind of limit. Once you have the idea of "where is this heading?",
you have the engine of the entire subject.

## What to take away from this chapter

- A **limit** asks: as the input creeps toward some value, where is
  the output heading?
- The limit may exist even when the function is undefined at the
  target value. This is the case we care about most.
- The notation is $\displaystyle\lim_{x \to a} f(x) = L$, read as
  "the limit of $f(x)$ as $x$ approaches $a$ is $L$."
- A limit only exists when the function heads toward the *same* value
  from both sides. Sudden jumps -- like the postage example -- mean
  the limit at the jump does not exist.
- Limits are the technical tool that will let us define both the
  derivative and the integral. Everything in calculus is downstream
  of this idea.

The central picture to carry forward is simple: *limits are about
heading, not arriving*. With that in hand, the next chapter shows
how to compute limits efficiently, without building a table every
time.

## Coming up next

[Chapter 2 -- Computing Limits Algebraically](02-computing-limits-algebraically.md)
