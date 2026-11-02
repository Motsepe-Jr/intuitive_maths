# Factoring Polynomials: A Geometric Way to See It

Factoring can look like a symbol trick: a long expression goes in, tidy parentheses come out. But the parentheses tell us something useful about how the polynomial is built—and where its graph meets the $x$-axis.

Take this example:

$$
P(x) = (x+6)(x^2+3x-18).
$$

One factor is linear, $x+6$. The other is quadratic, $x^2+3x-18$. Multiplying them gives a cubic:

$$
P(x) = x^3+9x^2-108.
$$

(The missing $x$ term has coefficient zero.) We can understand this product in two ways: by looking at values, and by arranging area pieces.

## Multiplying the heights

For any chosen $x$, each factor has a value—a height on its graph. The product of those two values is the height of $P(x)$ at that same $x$.

For example, at $x=0$:

$$
(x+6)=6, \qquad x^2+3x-18=-18,
$$

so their product is $6(-18)=-108$. Substituting $x=0$ into the expanded cubic also gives $-108$.

At $x=1$:

$$
(x+6)=7, \qquad x^2+3x-18=-14,
$$

and their product is $7(-14)=-98$. The expanded form gives $1+9-108=-98$ as well.

This is what multiplication of functions means here: at each input, multiply their outputs. The factors’ signs and sizes combine to make the cubic’s graph.

## Seeing the quadratic as a rectangle

Now focus on the quadratic:

$$
x^2+3x-18.
$$

Its factorization is

$$
x^2+3x-18=(x+6)(x-3),
$$

because multiplying the two binomials gives $x^2-3x+6x-18=x^2+3x-18$.

There is a useful area picture behind this. An $x^2$ square represents the first term. The $6x$ and $-3x$ pieces combine to give $3x$, and the $-18$ represents eighteen negative unit pieces. Arranged as a **signed-area** rectangle, the dimensions are $x+6$ and $x-3$.

The word *signed* matters: negative pieces are part of an algebra model, not ordinary positive lengths or physical holes. The picture helps us remember why the terms combine; multiplying the side expressions verifies the factorization exactly.

## Where polynomial division fits

Since the cubic was built as

$$
P(x)=(x+6)(x^2+3x-18),
$$

dividing $P(x)$ by $x+6$ gives back the quadratic:

$$
\frac{x^3+9x^2-108}{x+6}=x^2+3x-18.
$$

Polynomial long division is a systematic way to recover that missing factor when it is not already visible. It is not literally slicing a physical 3D block; it works because multiplication and division of polynomials undo one another, just as they do with numbers.

Factor the quadratic one more time, and the whole expression becomes

$$
P(x)=(x+6)^2(x-3).
$$

## What the factors tell us about the graph

A product is zero whenever at least one of its factors is zero. So the roots are

$$
x=-6 \quad\text{and}\quad x=3.
$$

The factor $(x+6)$ appears twice, so $x=-6$ is a **double root**. The graph touches the axis there and turns back rather than crossing it. The factor $(x-3)$ appears once, so the graph crosses the axis at $x=3$.

That is the payoff of factoring: it reveals the places where the graph is zero and whether it crosses or just touches the axis. The parentheses are not decoration—they expose the polynomial’s structure.
