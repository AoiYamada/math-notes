---
type: proof
keywords: derivative, taylor series
tags:
  - taylor series
---

\[
q(t) = \sum_{i=0}^{n} \frac{f^{(i)}(t) (x-t)^i}{i!}
\]

To calculate \( q'(t) \), we can separate out the \( i=0 \) term:

\[
\begin{align*}
q(t) &= \frac{f(t)(x-t)^0}{0!} + \sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^i}{i!} \\
     &= f(t) + \sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^i}{i!}
\end{align*}
\]

### Differentiate the First Term

The derivative of the first term is straightforward:

\[
\frac{d}{dt} f(t) = f'(t)
\]

### Differentiate the Second Term

For the second term, we apply the product rule to \( f^{(i)}(t) (x-t)^i \):

\[
\frac{d}{dt} \left( f^{(i)}(t) (x-t)^i \right) = f^{(i+1)}(t) (x-t)^i - f^{(i)}(t) \cdot i (x-t)^{i-1}
\]

Thus, we have:

\[
\frac{d}{dt} \sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^i}{i!} = \sum_{i=1}^{n} \frac{1}{i!} \left( f^{(i+1)}(t) (x-t)^i - f^{(i)}(t) \cdot i (x-t)^{i-1} \right)
\]

This can be rewritten as:

\[
\sum_{i=1}^{n} \frac{f^{(i+1)}(t) (x-t)^i}{i!} - \sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^{i-1}}{(i-1)!}
\]

### Change the Index in the Second Sum

Changing the index in the second sum from \( i \) to \( j = i - 1 \):

\[
\sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^{i-1}}{(i-1)!} = \sum_{j=0}^{n-1} \frac{f^{(j+1)}(t) (x-t)^{j}}{j!}
\]

Thus, we have:

\[
\frac{d}{dt} \sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^i}{i!} = \sum_{i=1}^{n} \frac{f^{(i+1)}(t) (x-t)^i}{i!} - \sum_{j=0}^{n-1} \frac{f^{(j+1)}(t) (x-t)^{j}}{j!}
\]

### Perform the Telescoping Effect

Notice that terms from \( j=1 \) to \( j=n-1 \) will cancel with those from \( i=1 \) to \( i=n-1 \):

\[
\frac{d}{dt} \sum_{i=1}^{n} \frac{f^{(i)}(t) (x-t)^i}{i!} = \frac{f^{(n+1)}(t) (x-t)^n}{n!} - f'(t)
\]

### Combine Results

Now we can combine the derivatives:

\[
q'(t) = f'(t) + \frac{f^{(n+1)}(t) (x-t)^n}{n!} - f'(t) = \frac{f^{(n+1)}(t) (x-t)^n}{n!}
\]

Thus, we conclude:

\[
\boxed{q'(t) = \frac{f^{(n+1)}(t) (x-t)^n}{n!}}
\]
