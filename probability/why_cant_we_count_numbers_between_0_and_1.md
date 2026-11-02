# Why Can’t We Count the Numbers Between 0 and 1?

When you first learn about infinity, it can feel straightforward: start at 1, then 2, then 3, and keep going forever. This is the infinity of the natural numbers, $\mathbb{N}$.

It is tempting to think that all infinite sets have the same size. In the late 19th century, Georg Cantor proved otherwise: **some infinities are strictly larger than others.** In particular, the real numbers in the interval $[0,1]$ cannot be listed one by one, even though the natural numbers can.

Cantor’s **diagonalization argument** shows why.

## 1. What Does “Countable” Mean?

A set is **countable** if its elements can be put into a list indexed by the natural numbers:

$$
x_1, x_2, x_3, \ldots
$$

The list may contain every element exactly once, or may repeat elements; what matters is that every element appears somewhere. A set that cannot be completely listed this way is **uncountable**.

## 2. Suppose We Have a Complete List

We will prove that $[0,1]$ is uncountable by contradiction. Suppose, for the sake of argument, that someone has made a complete list of every real number in $[0,1]$.

Write each number as a decimal expansion:

| Position | Number |
|---:|:---|
| $1$ | $x_1 = 0.314159\ldots$ |
| $2$ | $x_2 = 0.592653\ldots$ |
| $3$ | $x_3 = 0.271828\ldots$ |
| $4$ | $x_4 = 0.867530\ldots$ |
| $\vdots$ | $\vdots$ |

The claim is that every real number between 0 and 1 appears somewhere in this list.

## 3. Build a Number That Escapes the List

Look at the diagonal digits: the first digit of $x_1$, the second digit of $x_2$, the third digit of $x_3$, and so on. In this example, they are $3, 9, 1, 5, \ldots$.

Now construct a new number $y = 0.y_1y_2y_3\ldots$ by choosing each digit to differ from the corresponding diagonal digit. To avoid the ambiguity that $0.5000\ldots = 0.4999\ldots$, choose only 1 and 2:

- If the diagonal digit is 1, choose 2.
- Otherwise, choose 1.

For the example above:

1. The first digit of $x_1$ is 3, so choose $y_1 = 1$.
2. The second digit of $x_2$ is 9, so choose $y_2 = 1$.
3. The third digit of $x_3$ is 1, so choose $y_3 = 2$.
4. The fourth digit of $x_4$ is 5, so choose $y_4 = 1$.

So the beginning of the new number is $y = 0.1121\ldots$.

## 4. Why the List Cannot Be Complete

The number $y$ differs from $x_1$ in its first decimal digit, from $x_2$ in its second decimal digit, from $x_3$ in its third decimal digit, and, in general, from $x_n$ in its $n$th decimal digit.

Therefore, $y$ is not equal to any number in the list: for every position $n$, it differs from the number at that position. But $y$ is still a real number in $[0,1]$, since its decimal digits are all 1s and 2s.

This contradicts the claim that the list contained every real number in $[0,1]$. No matter how someone tries to list them, the diagonal construction produces a real number that is missing. Thus, $[0,1]$ is **uncountable**.

## Key Intuition

A list gives each position $n$ one number, $x_n$. The diagonal construction uses position $n$ to change the $n$th digit of that number. This guarantees that the new number escapes every position in the list.

The natural numbers and the real numbers are both infinite, but the real numbers in $[0,1]$ form a strictly larger infinity. This idea—constructing an object that differs from the $n$th listed object at its $n$th feature—also appears in logic and theoretical computer science, including proofs related to the Halting Problem.
