# Solving Systems of Equations by Lining Things Up

Something I noticed in geometry: before we prove anything or calculate anything, we usually rearrange the picture first. We rotate a triangle so a side sits flat on the ground. We drop a perpendicular so two pieces line up. We slide one shape on top of another to see what matches. The arithmetic only gets easy *after* things are aligned.

At some point I realised I was doing the exact same thing when solving a system of linear equations by elimination. I just hadn't seen it that way. This post is me working through that idea.

## The setup: two objects, same parts

Forget $x$ and $y$ for a second. Say I have two sculptures built from the same two kinds of parts:

- wooden beams (I don't know what one weighs, call it $x$)
- iron blocks (also unknown, call it $y$)

I can't weigh a single beam or a single block. I can only weigh the whole sculpture.

```
Sculpture A:   [Beam]            [Block][Block][Block]      = 11 kg
Sculpture B:   [Beam][Beam]      [Block]                    = 12 kg
```

Written as equations:

$$
\begin{aligned}
x + 3y &= 11 \quad \text{(A)}\\
2x + y &= 12 \quad \text{(B)}
\end{aligned}
$$

Each sculpture on its own tells me nothing definite. One equation, two unknowns. There are endless combinations of beam weight and block weight that make 11 kg.

But I have *two* sculptures made of the *same* parts. That is the whole point. If I can make some part of them match, I can compare them directly.

## Step 1: Make a piece match (scaling)

Right now nothing lines up. A has one beam, B has two. A has three blocks, B has one. If I lay them side by side, there is no clean piece I can cut away.

So I build a second copy of Sculpture A and glue it to the first. Now I have "double A":

```
2 × A:   [Beam][Beam]      [Block][Block][Block][Block][Block][Block]   = 22 kg
```

$$
2x + 6y = 22
$$

This is the bit I want to be careful about. Doubling didn't change what A *is*. The ratio of beams to blocks is the same, and the weight doubled along with the parts. It's like scaling a triangle: bigger, but the same shape, same angles. Every true statement about A is still true about 2A.

That's why we multiply the *whole* equation, every term, both sides. If I doubled the beams but forgot to double the weight, I'd have distorted the object. It wouldn't be A anymore, it'd be a lie.

The reason I chose 2 is simple: it's the number that makes the beams match B.

## Step 2: Lay them on top of each other and cut away the shared part

Now put 2A next to B:

```
2 × A:   [Beam][Beam] | [Block][Block][Block][Block][Block][Block]   = 22 kg
B:       [Beam][Beam] | [Block]                                      = 12 kg
         ------------   -----------------------------------------
          identical          this is where they differ
```

The left side is identical. Two beams in both. Whatever two beams weigh, they weigh the same in both sculptures. So the entire 10 kg difference between them has to come from the blocks.

I can just cut the beam section off both:

$$
(2x + 6y) - (2x + y) = 22 - 12
$$

$$
5y = 10
$$

The beams are gone. Not solved, *gone*. That's the trick: subtraction removes exactly the piece I made identical.

```
leftover:   [Block][Block][Block][Block][Block]   = 10 kg
```

## Step 3: Read off what's left

$$
5y = 10 \implies y = 2
$$

One block is 2 kg. Now go back to either original sculpture, A is easiest:

$$
x + 3(2) = 11 \implies x = 5
$$

One beam is 5 kg. Check with B: $2(5) + 2 = 12$. Good.

## Why this works, in plain terms

When I strip it down, elimination is three moves, and each one has a geometric twin:

| What I do with the equation | What it feels like geometrically |
|---|---|
| Multiply the whole equation by a number | Scale an object up without changing its shape |
| Choose the number so one coefficient matches | Rotate/slide things so an edge lines up |
| Subtract one equation from the other | Overlay the two shapes and cut away the overlap |

The thing that makes it legal is that both equations are describing the **same unknowns**. A beam in sculpture A weighs exactly what a beam in sculpture B weighs. If they were different kinds of beams, the matching piece wouldn't really match, and cutting it away would be meaningless.

So the real ingredients are:

1. **Shared parts.** Both equations use the same $x$ and $y$.
2. **Scaling preserves truth.** $2 \times (\text{true equation})$ is still true.
3. **Equal things cancel.** Once a piece is identical in both, the difference between the totals belongs entirely to the parts that differ.

## A second example, eliminating the other variable

Just to make sure the idea isn't tied to that one problem, let me go the other way and kill $y$ first on the same system.

$$
\begin{aligned}
x + 3y &= 11\\
2x + y &= 12
\end{aligned}
$$

To make the blocks match, I need three blocks in B. So I triple B:

$$
6x + 3y = 36
$$

```
3 × B:   [Beam]x6   | [Block][Block][Block]   = 36 kg
A:       [Beam]x1   | [Block][Block][Block]   = 11 kg
                      ---------------------
                      identical, cut it off
```

$$
(6x + 3y) - (x + 3y) = 36 - 11 \implies 5x = 25 \implies x = 5
$$

Same answer, different cut. Which piece I choose to align is my choice. I usually pick whichever needs the smaller multiplier.

## What I take away from this

Before I saw it like this, elimination felt like a recipe: "multiply, subtract, hope." Now it feels like what I already do with shapes. I don't try to compare two messy objects directly. I first reshape one so a piece matches the other exactly, then that piece stops mattering and what's left is simple enough to read.

In the next post I use this same idea somewhere I didn't expect it to show up: functional equations, where you're solving for a whole function instead of a number.
