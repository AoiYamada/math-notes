---
type: proof
keywords: derivative, taylor series
tags:
  - taylor series
---

# Proof of the Taylor Remainder Theorem

## Step 1: Define the Functions

We start by defining the Taylor polynomial and the remainder function.

1. **Taylor Polynomial \( p(x) \)**:
   \[
   p(x) = \sum_{i=0}^{n} \frac{f^{(i)}(a)}{i!} (x-a)^i
   \]
   Here, \( p(x) \) is the Taylor polynomial of \( f \) centered at \( a \) up to degree \( n \), with \( x \) varying and \( a \) held constant.

2. **Remainder Function \( R(x) \)**:
   The remainder \( R(x) \) captures the discrepancy between the actual function \( f(x) \) and its Taylor approximation \( p(x) \):
   \[
   f(x) = p(x) + R(x)
   \]

3. **Taylor Polynomial \( q(t) \)**:
   \[
   q(t) = \sum_{i=0}^{n} \frac{f^{(i)}(t)}{i!} (x-t)^i
   \]
   Here, \( q(t) \) is the Taylor polynomial of \( f \) centered at \( t \) up to degree \( n \), with \( t \) varying while \( x \) remains fixed.

4. **Helper Function \( g(t) \)**:
   We define:
   \[
   g(t) = f(t) - q(t) - R(x) \frac{(x-t)^{n+1}}{(x-a)^{n+1}}
   \]
   This function helps us analyze the remainder \( R(x) \).

## Step 2: Evaluate \( g(x) \) and \( g(a) \)

Next, we substitute \( t = x \) and \( t = a \) into \( g(t) \):

- **At \( t = x \)**:
  \[
  g(x) = f(x) - q(x) - R(x) \frac{(x-x)^{n+1}}{(x-a)^{n+1}} = f(x) - q(x) = 0
  \]
  This holds because \( q(x) \) is the Taylor polynomial evaluated at \( x \), which equals \( f(x) \).

- **At \( t = a \)**:
  \[
  g(a) = f(x) - q(a) - R(x) \frac{(x-a)^{n+1}}{(x-a)^{n+1}} = f(x) - q(a) - R(x)
  \]
  If we set \( R(x) \) to be the exact remainder term, we conclude \( g(a) = 0 \).

## Step 3: Apply Rolle's Theorem

Since \( g(t) \) is continuous on the interval \([a, x]\) and differentiable on \((a, x)\), and because \( g(a) = g(x) = 0 \), we can apply Rolle’s Theorem. This guarantees that there exists at least one point \( c \in (a, x) \) such that:
\[
g'(c) = 0
\]

## Step 4: Compute the Derivative \( g'(t) \)

Now we differentiate \( g(t) \) to find \( g'(t) \).

1. **Differentiate \( q(t) \)**:
   \[
   q(t) = \sum_{i=0}^{n} \frac{f^{(i)}(t) (x-t)^i}{i!}
   \]
   Differentiating term-by-term gives:
   \[
   q'(t) = f'(t) + \sum_{i=1}^{n} \frac{d}{dt} \left( \frac{f^{(i)}(t) (x-t)^i}{i!} \right)
   \]

   Applying the product rule:
   \[
   \frac{d}{dt} \left( f^{(i)}(t) (x-t)^i \right) = f^{(i+1)}(t) (x-t)^i - f^{(i)}(t) \cdot i (x-t)^{i-1}
   \]
   Thus, we express \( q'(t) \) as:
   \[
   q'(t) = f'(t) + \sum_{i=1}^{n} \left( \frac{f^{(i+1)}(t) (x-t)^i}{i!} - \frac{f^{(i)}(t) \cdot i (x-t)^{i-1}}{i!} \right)
   \]

   The second sum can be rewritten by changing the index:
   - Let \( j = i - 1 \). When \( i = 1 \), \( j = 0\), and when \( i = n \), \( j = n - 1 \). Thus:
   \[
   \sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^{i-1}}{i!} = \sum_{j=0}^{n-1} \frac{f^{(j+1)}(t) (x-t)^{j}}{(j+1)!}
   \]

   Substituting this back gives:
   \[
   q'(t) = f'(t) + \sum_{i=1}^{n} \frac{f^{(i+1)}(t) (x-t)^i}{i!} - \sum_{j=0}^{n-1} \frac{f^{(j+1)}(t) (x-t)^{j}}{(j+1)!}
   \]

   After simplification, terms from \( j=1 \) to \( j=n-1 \) will cancel by telescoping effect, yielding:
   \[
   \begin{align*}
   q'(t) &= f'(t) + \frac{f^{(n+1)}(t) (x-t)^{n}}{n!} - \frac{f^{(1)}(t) (x-t)^{0}}{1!}
         &= \frac{f^{(n+1)}(t) (x-t)^{n}}{n!}
   \end{align*}
   \]

2. **Differentiate \( g(t) \)**:
   \[
   g'(t) = -q'(t) + R(x) \frac{(n+1)(x-t)^{n}}{(x-a)^{n+1}}
   \]

## Step 5: Establish the Relationship

Setting \( g'(c) = 0 \):
\[
0 = -q'(c) + R(x) \frac{(n+1)(x-c)^{n}}{(x-a)^{n+1}}
\]

Rearranging gives:
\[
q'(c) = R(x) \frac{(n+1)(x-c)^{n}}{(x-a)^{n+1}}
\]

Substituting our expression for \( q'(c) \):
\[
R(x) = \frac{f^{(n+1)}(c)(x-c)^{n}}{n!} \cdot \frac{(x-a)^{n+1}}{(n+1)(x-c)^{n}}
\]
This simplifies to:
\[
R(x) = \frac{f^{(n+1)}(c)}{(n+1)!} (x-a)^{n+1}
\]

## Step 6: Establish Upper and Lower Bounds

Assuming \( f^{(n+1)}(t) \) is bounded on \([a, x]\) by constants \( m \) and \( M \):
\[
m \leq f^{(n+1)}(t) \leq M \quad \text{for } t \in [a, x]
\]

Thus, we derive bounds for \( R(x) \):
\[
\frac{m}{(n+1)!} (x-a)^{n+1} \leq R(x) \leq \frac{M}{(n+1)!} (x-a)^{n+1}
\]

## Conclusion

We have shown that the remainder \( R(x) \) in the Taylor series expansion of \( f(x) \) around the point \( a \) can be expressed as:
\[
R(x) = \frac{f^{(n+1)}(c)}{(n+1)!} (x-a)^{n+1}
\]
We also established upper and lower bounds for \( R(x) \), demonstrating its behavior over the interval. This completes the proof of the Taylor Remainder Theorem.
