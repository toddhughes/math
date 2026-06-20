# Chapter 5 -- The Derivative

This is the chapter where everything we have built so far pays off.
With limits in hand and continuity defined, we are ready to introduce
the central object of Part 1: the **derivative**.

A derivative is a single number that captures the **instantaneous
rate of change** of a function at a point. The whole goal of Part 1
has been to make that phrase precise. "Instantaneous" means "at one
specific instant, not averaged over an interval," and ordinary
arithmetic has no way of handling it. A limit does.

We will arrive at the derivative two ways at once. Geometrically, it
is the **slope of the line tangent to the graph at a point**.
Physically, it is the **rate at which a quantity is changing at one
specific moment**. These look like two different problems, but they
turn out to be the same problem in different clothing. The technique
that solves both is the same limit.

## Two problems that are secretly one

### Problem 1: the slope of a curve at a point

You learned long ago how to compute the slope of a *line*. Given two
points $(x_1, y_1)$ and $(x_2, y_2)$, the slope of the line through
them is

$$\text{slope} = \frac{y_2 - y_1}{x_2 - x_1}.$$

But a curve is not a line. A curve has a different slope at every
point. So what does "the slope of a curve at a point" even mean?

A natural answer: the slope of the curve at a point is the slope of
the **tangent line** at that point. The tangent line is the line that
just barely touches the curve at the one point in question, matching
the curve's direction there. If you zoomed in close enough at that
point, the curve would look almost identical to the tangent line.

That is a fine geometric picture, but it does not yet tell us how to
*compute* anything. The slope formula needs two points. We only have
one point on the tangent line: the point of contact.

### Problem 2: the instantaneous rate of change

Recall the car from the introduction. If the car drives at 60 mph
for one hour, the average speed is 60 mph, and the total distance is
60 miles. Average speed is easy: divide the total distance by the
total time.

But what if the speed is wobbling all trip? At the exact moment the
clock reads 27 minutes, what does the speedometer say?

You could measure the average speed over a tiny interval near the
27-minute mark, say from 26.9 minutes to 27.1 minutes. That would be
close, but not exact. Over any nonzero interval, the speed might
vary, so the average is only an approximation of the speed at a
single instant.

This is the same problem in different language. We want to talk
about something *at a single instant* (the speed at 27 minutes), but
the obvious calculation (distance over time) requires *two* moments
to compare.

## The bridge: the secant line

Both problems have the same shape, so the same trick solves both.

Pick a function $f$ and a specific input $x = a$. We want to know
the slope of the curve at the point $(a, f(a))$. We only have that
one point, so we cheat: we pick a *second* point on the curve
nearby and use it to compute a slope.

Place the second point a distance $h$ to the right of $a$. Its
coordinates are $\bigl(a + h,\; f(a + h)\bigr)$. The slope of the
line connecting the two points is:

$$\frac{f(a + h) - f(a)}{(a + h) - a} = \frac{f(a + h) - f(a)}{h}.$$

This expression has a name. It is the **average rate of change** of
$f$ over the interval $[a, a + h]$. Geometrically, it is the slope
of the **secant line** -- the line that cuts across the graph
through the two points $\bigl(a, f(a)\bigr)$ and $\bigl(a + h, f(a +
h)\bigr)$.

So far we have only used algebra. The trouble is, this is the slope
of a *secant*, not the slope of the *tangent*. The secant slope is
an average over an interval; the tangent slope is what we get at a
single point. The two are different in general.

But here is the key observation. If we let the second point slide
closer to the first, the secant line rotates. As the gap $h$ shrinks
toward 0, the second point gets closer to the first, and the secant
line rotates closer to being the tangent line. The secant slope
approaches the tangent slope.

In the language we now have:

$$\text{(tangent slope at } a) \;=\; \lim_{h \to 0} \frac{f(a + h) - f(a)}{h}.$$

This is the entire idea of the derivative. The whole machinery of
limits in the preceding chapters was building up to this single
expression.

Notice that direct substitution into the right-hand side gives
$\frac{f(a) - f(a)}{0} = \frac{0}{0}$, the indeterminate form. So
this is exactly the kind of limit Chapter 2 prepared us to handle:
the algebra is what will make it tractable.

## The definition

We are now ready for the formal definition.

> The **derivative** of $f$ at $x = a$, written $f'(a)$, is
>
> $$f'(a) = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h},$$
>
> provided this limit exists. When it does, we say $f$ is
> **differentiable** at $a$.

That is the whole definition. The number $f'(a)$ (read "$f$ prime
of $a$") is the slope of the tangent line to the graph of $f$ at
$x = a$.

A few things to note before we use it.

- The number $f'(a)$ is a slope. If it is positive, the function is
  increasing at $a$; if negative, decreasing; if zero, momentarily
  neither (a horizontal tangent).
- The number $f'(a)$ is also an instantaneous rate of change. If
  $f(x)$ describes the position of a car at time $x$, then $f'(a)$
  is the car's exact speed at time $a$. If $f(x)$ describes the
  temperature of a cup of coffee at time $x$, then $f'(a)$ is the
  exact rate at which the coffee is cooling at time $a$.
- The geometric interpretation and the physical interpretation are
  the *same number*, defined by the same limit. We just dress it
  up differently depending on the problem we are solving.

## Computing a derivative from the definition

Let us compute one to see the machinery in motion. We will find the
derivative of $f(x) = x^2$ at $x = 3$.

**Step 1.** Apply the definition. With $a = 3$ and $f(x) = x^2$:

$$f'(3) = \lim_{h \to 0} \frac{f(3 + h) - f(3)}{h} = \lim_{h \to 0} \frac{(3 + h)^2 - 9}{h}.$$

**Step 2.** Expand the square: $(3 + h)^2 = 9 + 6h + h^2$. So:

$$f'(3) = \lim_{h \to 0} \frac{9 + 6h + h^2 - 9}{h} = \lim_{h \to 0} \frac{6h + h^2}{h}.$$

**Step 3.** Factor $h$ out of the numerator:

$$f'(3) = \lim_{h \to 0} \frac{h(6 + h)}{h}.$$

**Step 4.** Cancel the $h$. This is legitimate because $h$ is
*approaching* 0, not equal to 0:

$$f'(3) = \lim_{h \to 0} (6 + h).$$

**Step 5.** Direct substitution finishes the job:

$$f'(3) = 6 + 0 = 6.$$

So the slope of the tangent line to $y = x^2$ at the point $(3, 9)$
is **6**.

If $f(x) = x^2$ were describing the position of a moving object at
time $x$, then $f'(3) = 6$ would say the object is moving at exactly
6 units per unit of time at the moment $x = 3$. Same number, two
meanings.

## The derivative as a function

The same calculation works for any input, not just $x = 3$. Let us
redo it leaving the input as a variable $x$, rather than pinning it
to 3.

$$f'(x) = \lim_{h \to 0} \frac{(x + h)^2 - x^2}{h}.$$

Expand: $(x + h)^2 = x^2 + 2xh + h^2$. So:

$$f'(x) = \lim_{h \to 0} \frac{x^2 + 2xh + h^2 - x^2}{h} = \lim_{h \to 0} \frac{2xh + h^2}{h} = \lim_{h \to 0} (2x + h) = 2x.$$

So for $f(x) = x^2$, the derivative is the function $f'(x) = 2x$.

This is a much more powerful result than the single number we got
before. With $f'(x) = 2x$ in hand, we know the slope of the graph
of $y = x^2$ at *every* point: at $x = 3$ the slope is $2 \cdot 3 =
6$ (matching what we just computed), at $x = 1$ the slope is 2, at
$x = -2$ the slope is $-4$, and so on.

The derivative is a function in its own right -- one function in,
one function out. From now on, when we speak of "the derivative of
$f$" without specifying a point, we mean this whole derivative
function.

## Two more worked examples

Here are two more computations from the definition. Each one leans
on one of the algebraic techniques from Chapter 2.

### Example: $f(x) = 1/x$ at $x = 2$

Set up the definition:

$$f'(2) = \lim_{h \to 0} \frac{f(2 + h) - f(2)}{h} = \lim_{h \to 0} \frac{\dfrac{1}{2 + h} - \dfrac{1}{2}}{h}.$$

The numerator is a difference of fractions. Combine them over a
common denominator (the technique from Chapter 2):

$$\frac{1}{2 + h} - \frac{1}{2} = \frac{2 - (2 + h)}{2(2 + h)} = \frac{-h}{2(2 + h)}.$$

Substituting back:

$$f'(2) = \lim_{h \to 0} \frac{-h}{2h(2 + h)} = \lim_{h \to 0} \frac{-1}{2(2 + h)} = \frac{-1}{2 \cdot 2} = -\frac{1}{4}.$$

So the slope of $y = 1/x$ at the point $(2, 1/2)$ is $-\frac{1}{4}$.
The function is decreasing at $x = 2$, which makes sense: $1/x$ is
decreasing everywhere on the positive side.

You may notice that we computed this exact limit back in Chapter 2,
as an exercise in combining fractions. It was secretly a derivative
all along.

### Example: $f(x) = \sqrt{x}$ at $x = 4$

$$f'(4) = \lim_{h \to 0} \frac{f(4 + h) - f(4)}{h} = \lim_{h \to 0} \frac{\sqrt{4 + h} - 2}{h}.$$

The numerator has a square root. Multiply top and bottom by the
conjugate $\sqrt{4 + h} + 2$:

$$\frac{\sqrt{4 + h} - 2}{h} \cdot \frac{\sqrt{4 + h} + 2}{\sqrt{4 + h} + 2} = \frac{(4 + h) - 4}{h\bigl(\sqrt{4 + h} + 2\bigr)} = \frac{h}{h\bigl(\sqrt{4 + h} + 2\bigr)}.$$

Cancel the $h$:

$$f'(4) = \lim_{h \to 0} \frac{1}{\sqrt{4 + h} + 2} = \frac{1}{\sqrt{4} + 2} = \frac{1}{4}.$$

So the slope of $y = \sqrt{x}$ at the point $(4, 2)$ is $\frac{1}{4}$.

These two examples together show something important: computing a
derivative from the definition does not require any *new* algebra.
It only repackages the limit techniques from Chapter 2 toward a
particular kind of $\frac{0}{0}$ limit -- the one that comes from
the slope of a secant.

## Notation

There are several common ways to write the derivative, and they are
all in active use. You should recognize all of them.

- $f'(x)$. The **prime notation**, due to Lagrange. The prime mark
  is the derivative operator. Read "$f$ prime of $x$." The most
  compact form, and the one we will use most often.
- $\displaystyle\frac{dy}{dx}$. The **Leibniz notation**. If
  $y = f(x)$, then $dy/dx$ is the derivative of $y$ with respect to
  $x$. The fraction-like shape is a visual reminder of what the
  derivative *is*: the limit of $\Delta y / \Delta x$ as the change
  in $x$ shrinks to zero.
- $\displaystyle\frac{df}{dx}$. The same Leibniz idea, written with
  the function name. Equivalent to $f'(x)$.
- $\displaystyle\frac{d}{dx}\bigl[f(x)\bigr]$. Used when we want to
  think of $\frac{d}{dx}$ as an *operator* that we apply to an
  expression. For instance, $\dfrac{d}{dx}\bigl[x^2\bigr] = 2x$.

All four refer to the same thing. Each one is convenient in
different contexts. The prime notation is shortest. The Leibniz
notation makes the geometric meaning visible at a glance, and it is
the more natural choice once we start composing functions and
handling change of variables.

## When the derivative fails to exist

The definition of the derivative is a limit, and limits can fail to
exist. So derivatives can fail to exist too. There are three
standard ways a function can fail to be differentiable at a point.

### Corners

The function $f(x) = |x|$ (the absolute value) is the canonical
example. It is continuous everywhere -- the graph is a "V" with the
corner at the origin, drawable without lifting the pencil. But what
is the slope at $x = 0$?

Approach from the right. For $x > 0$ the graph is the line $y = x$,
which has slope 1. So the secant slopes from the right approach 1.

Approach from the left. For $x < 0$ the graph is the line $y = -x$,
which has slope $-1$. So the secant slopes from the left approach
$-1$.

The two one-sided limits disagree, so $\displaystyle\lim_{h \to 0}
\frac{|0 + h| - |0|}{h}$ does not exist. The function has no single
tangent slope at the corner: from one side the tangent is rising,
from the other it is falling. We say $|x|$ is **not differentiable**
at $x = 0$, even though it is continuous there.

### Vertical tangents

The function $f(x) = \sqrt[3]{x}$ is continuous at $x = 0$, but its
tangent line at the origin is *vertical*. A vertical line has no
defined slope (the slope formula divides by zero). The limit
$\displaystyle\lim_{h \to 0} \frac{\sqrt[3]{h}}{h}$ is $+\infty$,
not a finite number, so the derivative does not exist at $x = 0$.
The tangent is geometrically there; it just happens to be vertical,
and the derivative cannot represent an infinite slope as a real
number.

### Discontinuities

If $f$ is not continuous at $a$, then it cannot be differentiable at
$a$ either. There is no single "tangent line" at a point where the
function jumps or blows up. (We will see in the next section why
this has to be so.)

These three categories -- corners, vertical tangents, and
discontinuities -- are the standard failure modes. Everywhere else,
where the function is smooth and continuous, the derivative usually
exists.

## Differentiability implies continuity

The relationship between continuity and differentiability is not
symmetric. We just saw that a function can be continuous without
being differentiable (the corner of $|x|$). The reverse direction,
however, *is* true:

> If $f$ is differentiable at $a$, then $f$ is continuous at $a$.

The reason is not hard to see informally. If the limit
$\displaystyle\lim_{h \to 0} \frac{f(a + h) - f(a)}{h}$ exists as a
real number $L$, then the numerator $f(a + h) - f(a)$ must head to
0 as $h$ does. (If it did not, we would be dividing a fixed nonzero
number by something shrinking to zero, and the limit would be
$\pm\infty$ or fail to exist altogether.) But "$f(a + h) - f(a) \to
0$ as $h \to 0$" is exactly the statement that $f$ is continuous
at $a$.

In short:

- Differentiable $\Rightarrow$ continuous.
- Continuous does **not** imply differentiable.

So differentiability is a *stronger* condition than continuity.
Every differentiable function is continuous, but a continuous
function with a corner, a vertical tangent, or some other oddity at
a point will fail to be differentiable there.

## What to take away from this chapter

- The **derivative** of $f$ at $a$ is the number
  $$f'(a) = \lim_{h \to 0} \frac{f(a + h) - f(a)}{h},$$
  when this limit exists. It captures both the **slope of the
  tangent line** to the graph of $f$ at $(a, f(a))$ (the geometric
  meaning) and the **instantaneous rate of change** of $f$ at $a$
  (the physical meaning). They are the same number.
- The derivative is itself a function: for each input $x$ where the
  limit exists, $f'(x)$ gives the slope of the tangent line at that
  point.
- Computing a derivative from the definition uses the same
  algebraic techniques as Chapter 2: factoring and canceling,
  combining fractions, and multiplying by the conjugate.
- Common notations for the derivative include $f'(x)$,
  $\dfrac{dy}{dx}$, $\dfrac{df}{dx}$, and $\dfrac{d}{dx}[f(x)]$.
  They all mean the same thing.
- A function can fail to be differentiable at a **corner**, at a
  **vertical tangent**, or at a **discontinuity**.
- **Differentiable implies continuous**, but not the other way
  around.

We now have the central object of Part 1 defined and computable from
first principles. Computing every derivative from the limit
definition is exhausting, though. The next chapter develops a small
set of rules that let us compute the derivatives of polynomials and
many other common functions almost instantly, without setting up the
limit by hand.

## Coming up next

[Chapter 6 -- Basic Derivative Rules](06-basic-derivative-rules.md) *(not yet written)*
