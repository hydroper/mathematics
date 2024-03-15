# Mathematics Basics

- ([LaTeX syntax](https://en.wikibooks.org/wiki/LaTeX/Mathematics))
  - [Big Union](https://www.physicsread.com/make-big-union-symbol-in-latex/)

## Fundamental

#### Manual Calculus

<details>

<summary>Exams may require handwritten calculus.</summary>

- When writing multiplication (given non-negative decimals):
  - Let $n$ be the sum of decimal places in both operands.
  - Strip decimal point in both operands.
  - Add a decimal point to the product before _n_ digits.
- When writing division (given non-negative decimals):
  - $x \div y$
    - Align operands: $A(x, y)$
      - Let the initial quotient $q$ be _empty_
      - If $`\text{integer of $x$} = 0`$ and $`\text{integer of $y$} \neq 0`$:
        - Let $n$ be the number of decimal places in $x$ **_without_** counting leading zeroes.
        - Let the initial quotient $q$ be all leading zeroes of $x$ with a decimal point after the first zero.
        - Let $x = x \times 10^n$ without leading zeroes
        - Let $(x, y, q) = A(x, y)$
      - If $`\text{integer of $x$} \neq 0`$ and $`\text{integer of $y$} = 0`$:
        - Let $n$ be the number of decimal places in $y$ **_counting_** all zeroes.
        - Let $y$ be $y$ without leading zeroes. <!--and with decimal point after the first digit.-->
        - Let $x = x \times 10^n$
        - Let $(x, y, q) = A(x, y)$
      - If $`\text{integer of $x$} = 0`$ and $`\text{integer of $y$} = 0`$:
        - Let $(n_1, n_2)$ be the number of leading zeroes in $(x, y)$.
        - Let $(x, y)$ without leading zeroes
        - If original $y$ had less leading zeroes than original $x$, let $`y = y \times 10^{n_1 - n_2}`$ (this adds trailing delta zeroes to $y$)
        - If original $x$ had less leading zeroes than original $y$, let $`x = x \times 10^{n_2 - n_1}`$ (this adds trailing delta zeroes to $x$)
      - If $`\text{integer of $x$} \neq 0`$ and $`\text{integer of $y$} \neq 0`$:
        - Let $`m = \text{the maximum number of decimal places between $x$ and $y$}`$
        - Let both $x$ and $y$ be integers with $`[n, m)`$ trailing zeroes and no decimal point, where $n$ is the number of decimal places in the decimal.
    - Let $(x, y, q) = A(x, y)$
    - Repeat these steps until $x$ is zero or the quotient is a periodic decimal:
      - If $x < y$:
        - If the quotient is empty, let it be a zero.
        - If the quotient is not empty:
          - If quotient has no decimal point, add a decimal point it.
          - If quotient has a decimal point, add a trailing zero to the quotient.
        - Add a trailing zero to $x$.
      - If $x \ge y$:
        - Let $f$ be how many times $y$ fits into $x$
        - Let $x = x - f$
        - Add $f$ as trailing digits to the quotient.
- Division examples
```
1.12 / 1.5 =
  x = 112  y = 150

0.25 / 125 =
  q = 0.     x = 25
  q = 0.0    x = 250
  q = 0.02   x = 250 - 250 = 0

0.25 / 125 = 0.02

1001 / 100 =
  1001
- 1000      q = 10
  ---
     1
     10     q = 10.
     100    q = 10.0
   - 100    q = 10.01
     ---

1001 / 100 = 10.01

0.5 / 0.5 =
  q = ?   x = 5   y = 5

0.005 / 0.05 =
  q = ?   x = 5   y = 50

0.5 / 0.05 =
  q = ?   x = 50  y = 5

10.55 / 10.001 =
  q = ?   x = 10550   y = 10001

1 / 0.05  =
  x = 100  y = 5
  q = 20

11 / 0.11 =
  x = 1100  y = 11
  q = 100

15 / 0.0011 =
  x = 150000   y = 11
  q = 13       x = (150000 - 143) 10^3 = 7000
  x = 7000

  # how much 11 fits into the leading 700?

  q = 1363   x = (700 - 693) * 10 = 70
  x = 70

  # continue division here...
```
- Fraction
  - Given $`x \div y`$ of $n$, you can either:
    - Resolve the division and multiply it by $n$.
    - Do $x \times n \div y$
  - Given $`x_1 \div y_1`$ of $x_2 \div y_2$, you can either:
    - Resolve both divisions and multiply one by the another.
    - Do $(x_1 \times x_2) \div (y_1 \times y_2)$

</details>

#### Sets

- **Complement:** Complement of $B$ is $\set{x \in SuperSet|x \notin B}$
- **Disjoint:** A collection of sets is said to be disjoint if any two of them are disjoint. Two sets are disjoint if they've no common element.
- **Partition:** A set of subsets $P$ is a partition of $S$ if the subsets of $P$ are disjoint and their union is $S$. In other words, a partition of $S$ is a set of non-empty subsets of $S$ such that every element $x$ in $S$ is in exactly one of these subsets, that is, the subsets are mutually non-empty disjoint sets.
- **Intersection:** Think of $\cap$ as "and" (n).
- **Union of _n_ sets:**

$$
\bigcup_{n=1}^{\infty} S_n = S_1 \cup S_2 \cup \dots
$$
- **Intersection of _n_ sets:**

$$
\bigcap_{n=1}^{\infty} S_n = S_1 \cap S_2 \cap \dots
$$

- **Relationship:** $B \subset A\$ (B is subset of A)
- **Universal set:** $\Omega$ (in probabilistic model, the sample space)
- **Empty set:** $\varnothing$

#### De Morgan's Laws

The following is useful for the $S^c_n$ complement:

$$
\left(\bigcup_{n} S_n\right)^c = \bigcap_{n} S^c_n
$$

Don't know yet about:

$$
\left(\bigcap_{n} S_n\right)^c = \bigcup_{n} S^c_n
$$

#### Terminology

- **Collectively exhaustive:** Complete as a group
- **Mutually exclusive:** Independent from each other or only one element of a set ends up as outcome
