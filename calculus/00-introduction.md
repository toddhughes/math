# Calculus

Welcome. This is a read-along introduction to calculus written for a
true beginner. There are no homework problems and no exercises to do
alone. Each chapter walks you through ideas in plain English, then
shows worked examples step by step.

You should be comfortable with everyday arithmetic and basic algebra.
Anything beyond that will be introduced as we go.

The rest of this page is two things: a tour of what calculus actually
*is* and what it is *for*, and a map of how the book is organized.

## The one-sentence answer

Calculus is the mathematics of **change** and the mathematics of
**accumulation**.

That is the whole subject in one line. Everything else -- every rule,
every symbol, every technique -- exists to make those two ideas
precise and useful.

## What "change" and "accumulation" mean

It is easier to feel these two ideas than to define them, so let us
look at a familiar situation: a car on a road.

**Change** is about how fast something is happening *right now*.

- If you glance at the speedometer in a car and it reads 60 mph, you
  are reading a rate of change. It tells you how fast the car's
  position is changing at that exact instant.
- Notice the speedometer does not care where you started, where you
  are going, or how long you have been driving. It only describes
  *this moment*.

**Accumulation** is about adding up small contributions over time to
get a total.

- If the car drives at 60 mph for one hour, it covers 60 miles. The
  total distance is an accumulation of all that motion.
- In real life, speed is rarely constant. You speed up, you slow down,
  you stop at lights. The total distance is still the accumulation of
  whatever speed you had, moment by moment, over the whole trip.

These two ideas -- the instantaneous rate, and the total built up over
time -- are the two halves of calculus. They are studied by two tools:

- The **derivative** is the tool for measuring instantaneous change.
- The **integral** is the tool for measuring accumulation.

For now, just hold on to the picture: derivatives are about *right
now*, integrals are about *so far*. Each gets its own part of this
book.

## Why this is a whole subject

You might reasonably ask: if I want a rate, I divide. If I want a
total, I add. Why does this need a whole branch of mathematics?

Because both of those operations get hard the moment things stop being
constant.

Suppose a car drives 60 mph for 1 hour. Total distance:

$$\text{distance} = 60 \text{ mph} \times 1 \text{ hour} = 60 \text{ miles}.$$

Easy. But the speedometer is almost never sitting on one number. Now
suppose the car's speed wobbles up and down all trip. How far did it
go? Plain multiplication does not work anymore, because there is no
single speed to multiply by.

Same problem in reverse. If you know the total distance after one
hour, you can compute an *average* speed. But what was the car's
speed at the exact moment the clock read 27 minutes? "Average speed
over a tiny slice of time" gets you close, but the slice has to be
infinitely small to be exact -- and infinitely small slices are not
something ordinary arithmetic knows how to handle.

Calculus is the toolkit invented to handle exactly these situations:
rates and totals when things are *not* constant. The whole subject is
built on one big technical move, which is learning how to talk about
"infinitely small" pieces in a rigorous, predictable way. That move is
called the **limit**, and it is where the book begins in earnest.

## Sample problems calculus can solve

Here is a small gallery of questions calculus is good at. You are not
expected to solve any of these yet. The goal is to give you a feel for
the shapes of problems the subject handles.

**Questions a derivative can answer (instantaneous change):**

- A baseball is thrown straight up. How fast is it moving at the
  exact moment it reaches the highest point?
- A company's revenue is growing. What is its growth rate this
  quarter, not just on average but right at the end of the quarter?
- A hot cup of coffee is cooling in a room. How quickly is its
  temperature dropping at the moment it hits 150 F?
- A roller coaster track is described by an equation. How steep is
  the track at any specific point?

**Questions an integral can answer (accumulation):**

- A car's speedometer reading is recorded every second for a trip.
  How far did the car travel in total?
- Water flows into a tank at a rate that changes over time. How much
  water is in the tank after ten minutes?
- A field has an irregular, curvy boundary. What is its exact area?
- A solid object has a complicated shape. What is its volume?

**Questions a series can answer (infinite approximation):**

- How does your calculator compute $\sin(1.7)$ when it can only add,
  subtract, multiply, and divide?
- Can a function be rebuilt from how it behaves at a single point?
- A repeating decimal like $0.\overline{142857}$ is an infinite sum.
  When does an infinite sum settle on a finite value, and when does
  it not?

**Questions multivariable calculus can answer (more than one input):**

- A hiker stands on a hillside. Which direction should they walk to
  climb the fastest?
- A box is being designed with a fixed surface area. What dimensions
  give the largest possible volume?
- Water flows through a region of space in a swirling pattern. How
  much fluid passes through a given surface per second?

**Questions that need several tools at once:**

- A factory wants to design a cylindrical can that holds exactly 12
  ounces using the least possible aluminum. What dimensions should
  it use? (Derivatives find the minimum; integrals compute volume
  and surface area.)
- A rocket burns fuel at a changing rate as it ascends. How high
  will it go before running out? (Derivatives describe rates of
  climb, integrals add them up into altitude.)

The thread running through all of these is the same: *something is
changing, and we want to say something exact about either the rate
or the total*. Calculus is what makes the word "exact" possible.

## A first peek at notation

You will see two symbols all the way through this book. There is no
need to memorize them now, but it is worth seeing them once so they
are not strangers when they reappear.

The derivative of a quantity $y$ with respect to $x$ is written:

$$\frac{dy}{dx}.$$

Read it out loud as "the derivative of $y$ with respect to $x$" or
"$dy$ over $dx$." The fraction-like shape is a hint at what it means:
"a tiny change in $y$ divided by a tiny change in $x$" -- a rate.

The integral of a quantity $f(x)$ over an interval from $a$ to $b$ is
written:

$$\int_{a}^{b} f(x) \, dx.$$

Read it as "the integral of $f$ of $x$ from $a$ to $b$." The tall
S-shape is literally an old-fashioned letter S, standing for "sum."
That is your hint: an integral is, at heart, a sum of infinitely many
infinitely small pieces.

## How this book is organized

The book is in four parts. Each part is its own folder with its own
introduction and chapters. Read the parts in order; each builds on
the one before.

**[Part 1 -- Derivatives](part-1-derivatives/00-introduction.md)** is
about *instantaneous change*. It begins with the **limit**, the
technical idea that makes calculus possible. From there it builds the
derivative, the rules for computing derivatives quickly, and the most
useful ways derivatives get applied: optimization, related rates,
curve sketching, and rescuing limits that ordinary arithmetic cannot
handle.

**[Part 2 -- Integrals](part-2-integrals/00-introduction.md)** is
about *accumulation*. It introduces the antiderivative, the definite
integral as a limit of sums, and the **Fundamental Theorem of
Calculus** -- the result that binds Parts 1 and 2 together by showing
that derivatives and integrals are essentially inverse operations.
From there it builds the techniques for computing integrals and
applies them to areas, volumes, work, and the first taste of
differential equations.

**[Part 3 -- Series](part-3-series/00-introduction.md)** is about
representing functions as *infinite sums*. We meet sequences and
series, learn the tests for deciding when an infinite sum has a
finite total, and arrive at the **Taylor series** -- the recipe that
lets you rebuild a function from its derivatives at a single point.
This is the result that ties Part 3 back to Part 1, and it is the
reason your calculator can compute $\sin(1.7)$.

**[Part 4 -- Multivariable Calculus](part-4-multivariable/00-introduction.md)**
lifts the whole machine into higher dimensions. Functions now take
in vectors and may return vectors. Derivatives become partial
derivatives and gradients; integrals become double and triple
integrals; whole new objects appear, like vector fields and surface
integrals. The part culminates in the major theorems of vector
calculus -- Green's theorem, the divergence theorem, and Stokes'
theorem -- which reveal that the Fundamental Theorem of Calculus
from Part 2 was only one face of a much bigger result.

## How to read this book

- Read the parts in order, and the chapters within each part in
  order. Each piece builds on the last.
- Take your time. Re-read anything that does not click.
- The table of contents in each part's introduction shows which
  chapters have been written so far.

## Where to start

Begin with [Part 1 -- Derivatives](part-1-derivatives/00-introduction.md).
