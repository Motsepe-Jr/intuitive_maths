# Functional Equations Are Just Systems of Equations in Disguise

The first time I saw something like

$$
f(x) + 3f(-x) = 2x + 4
$$

and was asked to "find $f(x)$", I froze. My instinct was to solve for $x$. Years of school maths trained me that $x$ is the thing you hunt down.

But here $x$ isn't the target at all. The equation is true for *every* $x$. What I'm actually looking for is the rule $f(\square)$, the machine itself.

Once I saw that, and connected it to the "line things up and cut away the matching piece" idea from my [previous post](systems_of_equations_by_alignment.md), these problems stopped being scary. This is how I think about them now.

## The function is a machine, not a number

A function is a fixed machine. Whatever goes in the slot, it applies the same rule:

```
   input  ──►  [  f(□)  ]  ──►  output
```

It doesn't care what I call the input. If the equation is true when I put $x$ in the slot, it's also true when I put $-x$ in the slot, or $5$, or anything else. The rule is the rule.

That freedom is the key. I'm allowed to feed the equation a different input and get a *new* true statement out of it for free.

## An analogy first: the translation box

Before numbers, here's how I first convinced myself this works.

Imagine a box that translates words. I don't know its internal rule, but I know one fact about it. For any word $W$:

$$
\text{Out}(W) + 2 \times \text{Out}(\text{opposite of } W) = \text{length of } W
$$

I drop in **"HOT"**. Its opposite is "COLD", and "HOT" has 3 letters:

$$
\text{Out(HOT)} + 2\,\text{Out(COLD)} = 3
$$

Stuck. One equation, two unknowns.

Now I flip it. I drop in **"COLD"**. Its opposite is "HOT", and "COLD" has 4 letters. Same box, same rule:

$$
\text{Out(COLD)} + 2\,\text{Out(HOT)} = 4
$$

Call $H = \text{Out(HOT)}$ and $C = \text{Out(COLD)}$. I now have:

$$
\begin{aligned}
H + 2C &= 3\\
2H + C &= 4
\end{aligned}
$$

That's just an ordinary two-unknown system, the exact thing from the beams-and-blocks post. Double the first: $2H + 4C = 6$. Line it up against the second and cut away the matching $2H$:

```
2 × first:   [2H] | 4C  = 6
second:      [2H] | 1C  = 4
             ----
             cut     3C = 2   →   C = 2/3
```

Then $H = 3 - 2C = 5/3$.

What made this work wasn't anything clever about words. It was that **HOT and COLD point at each other**. Opposite of HOT is COLD, opposite of COLD is HOT. Looking at the box from both sides of that pair gave me exactly two equations about exactly the same two unknowns.

## Now the real one: the sign flipper

$$
f(x) + 3f(-x) = 2x + 4 \qquad \text{(1)}
$$

### Step 1: Spot the pair

Inside the function I see two inputs: $x$ and $-x$. They're partners the same way HOT and COLD were, because flipping twice brings me back:

$$
x \;\xrightarrow{\text{flip}}\; -x \;\xrightarrow{\text{flip}}\; -(-x) = x
$$

### Step 2: Feed in the partner

Equation (1) holds for every input. So I'm allowed to replace *every* $x$ with $-x$. Every single one, including the ones on the right-hand side:

$$
f(-x) + 3f(-(-x)) = 2(-x) + 4
$$

Clean up $-(-x) = x$:

$$
f(-x) + 3f(x) = -2x + 4 \qquad \text{(2)}
$$

This is the "drop in COLD instead" move. Same machine, viewed from the other end of the pair.

### Step 3: Stop treating them as functions

This is the mental shift that unlocked it for me. For a fixed $x$, $f(x)$ is just some number and $f(-x)$ is just some other number. So I give them plain names:

$$
A = f(x), \qquad B = f(-x)
$$

and the two equations become

$$
\begin{aligned}
A + 3B &= 2x + 4 \qquad \text{(1)}\\
3A + B &= -2x + 4 \qquad \text{(2)}
\end{aligned}
$$

Now it's a beams-and-blocks problem. The right-hand sides have $x$ in them, but that's fine, they're just "the total weight", which happens to depend on $x$.

### Step 4: Line up and cut

I want the $A$ pieces to match, so I triple equation (1):

$$
3A + 9B = 6x + 12
$$

Lay it over (2):

```
3 × (1):   [3A] + 9B  =  6x + 12
(2):       [3A] + 1B  = -2x + 4
           ----
           cut    8B  =  8x + 8
```

$$
8B = 8x + 8 \implies B = x + 1
$$

So $f(-x) = x + 1$. Put that back into (1):

$$
A + 3(x + 1) = 2x + 4 \implies A = 2x + 4 - 3x - 3 = -x + 1
$$

$$
\boxed{f(x) = 1 - x}
$$

### Step 5: Check it, because I don't trust myself

If $f(x) = 1 - x$ then $f(-x) = 1 + x$, and

$$
f(x) + 3f(-x) = (1 - x) + 3(1 + x) = 1 - x + 3 + 3x = 2x + 4. \checkmark
$$

Also notice $B = f(-x) = x + 1$ is consistent: plug $-x$ into $1 - x$ and you get $1 + x$. The two answers agree with each other, which is a good sign the system was set up right.

## Why the pair has to close

I asked myself: why does this only work with certain substitutions? Why $-x$ and not, say, $x + 1$?

Because flipping twice has to bring me back to where I started. If I apply the swap and get a *new* input I've never seen, I get a new unknown, and then I'd need another equation, which brings another unknown, forever. With $x \to x+1$:

```
x  →  x+1  →  x+2  →  x+3  →  ...   (never closes, unknowns keep piling up)
```

With $x \to -x$:

```
x  →  -x  →  x                      (closes after two steps: two unknowns, two equations)
```

The fancy name for a swap that undoes itself is an **involution**. The common ones I look for:

| Swap $T(x)$ | Apply twice | The pair |
|---|---|---|
| $-x$ | $-(-x) = x$ | $x \leftrightarrow -x$ |
| $\dfrac{1}{x}$ | $\dfrac{1}{1/x} = x$ | $x \leftrightarrow \dfrac{1}{x}$ |
| $1 - x$ | $1 - (1 - x) = x$ | $x \leftrightarrow 1 - x$ |

Whenever I see $f(x)$ sitting next to $f$ of one of these, I know I can generate the second equation and turn the whole thing into a 2×2 system.

## How I'd summarise it to myself

1. **The target is the machine, not $x$.** The equation is true for every input.
2. **Find the partner input.** Look inside the brackets: $-x$, $1/x$, $1-x$.
3. **Feed in the partner.** Replace every $x$ with it. That's a second true equation for free.
4. **Rename.** $A = f(x)$, $B = f(\text{partner})$. Now they're just two unknown numbers.
5. **Line up and cut.** Scale one equation so a piece matches, subtract, read off what's left.

The part I like most is that step 5 is exactly the same move as the beams and blocks. Functional equations felt like a completely different topic, but underneath it's the same instinct I have in geometry: arrange things so a piece matches, then remove it.
