---
type: proof
keywords: derivative, taylor series
tags:
  - taylor series
---

# **Proof of the Taylor Remainder Theorem**

Let \( f \) be a function with continuous \( (n+1) \)-st derivative on an open interval containing the points \( a \) and \( x \).

---

## **Step 1: Taylor Polynomial, Remainder, and Key Functions**

### 1. **Taylor Polynomial at \( a \):**

\[
p(x) = \sum_{i=0}^n \frac{f^{(i)}(a)}{i!} (x-a)^i
\]

This is the degree-\( n \) Taylor polynomial for \( f \) at \( a \).

### 2. **Remainder Definition:**

\[
f(x) = p(x) + R(x)
\]
where \( R(x) \) is the error (remainder) at \( x \).

### 3. **Auxiliary Taylor Polynomial at \( t \):**

For \( t \) between \( a \) and \( x \), define:
\[
q(t) = \sum_{i=0}^n \frac{f^{(i)}(t)}{i!} (x-t)^i
\]
This is the Taylor polynomial of \( f \) centered at \( t \), evaluated at \( x \).

### 4. **Auxiliary Function:**

Define
\[
g(t) = f(x) - q(t) - R(x) \cdot \frac{(x-t)^{n+1}}{(x-a)^{n+1}}
\]
for \( t \) in the closed interval between \( a \) and \( x \) (assuming \( x \neq a \)).

---

## **Step 2: Evaluate \( g(t) \) at the Endpoints**

### **At \( t = a \):**

\[
\begin{align*}
g(a) &= f(x) - q(a) - R(x)\frac{(x-a)^{n+1}}{(x-a)^{n+1}} \\
     &= f(x) - p(x) - R(x)\cdot 1 \\
     &= f(x) - p(x) - R(x) \\
     &= 0
\end{align*}
\]
(since \( f(x) = p(x) + R(x) \) by definition).

### **At \( t = x \):**

\[
\begin{align*}
g(x) &= f(x) - q(x) - R(x)\frac{(x-x)^{n+1}}{(x-a)^{n+1}} \\
     &= f(x) - q(x) - R(x)\cdot 0 \\
     &= f(x) - q(x)
\end{align*}
\]
But
\[
q(x) = \sum_{i=0}^n \frac{f^{(i)}(x)}{i!}(x-x)^i = f(x)
\]
(all terms with \( i > 0 \) vanish, the \( i=0 \) term is \( f(x) \)), so:
\[
g(x) = 0
\]

---

## **Step 3: Rolle’s Theorem Application**

Since \( f \) is \( (n+1) \)-times differentiable and \( f^{(n+1)} \) is continuous, the function \( g \) is differentiable on the open interval between \( a \) and \( x \) and continuous on its closure.

We have \( g(a) = g(x) = 0 \).  
**By Rolle’s Theorem, there exists \( c \) between \( a \) and \( x \) such that \( g'(c) = 0 \).**

---

## **Step 4: Compute \( g'(t) \)**

\[
g'(t) = -q'(t) - R(x) \cdot \frac{d}{dt}\left(\frac{(x-t)^{n+1}}{(x-a)^{n+1}}\right)
\]
Since \( (x-a)^{n+1} \) is constant with respect to \( t \):
\[
\frac{d}{dt}(x-t)^{n+1} = -(n+1)(x-t)^n
\]
So,
\[
g'(t) = -q'(t) + R(x)\frac{(n+1)(x-t)^n}{(x-a)^{n+1}}
\]

### **Compute \( q'(t) \):**

Recall:
\[
\begin{align*}
q(t) &= \sum_{i=0}^n \frac{f^{(i)}(t)}{i!}(x-t)^i \\
     &= \frac{f^{(0)}(t)}{0!}(x-t)^0 + \sum_{i=1}^n \frac{f^{(i)}(t)}{i!}(x-t)^i \\
     &= f(t) + \sum_{i=1}^n \frac{f^{(i)}(t)}{i!}(x-t)^i
\end{align*}
\]

Differentiate term-by-term:
\[
\frac{d}{dt}\left[ f^{(i)}(t)(x-t)^i \right] = f^{(i+1)}(t)(x-t)^i - i f^{(i)}(t)(x-t)^{i-1}
\]
So,
\[
\begin{align*}
q'(t) &= f'(t) + \sum_{i=0}^{n} \frac{1}{i!}\left( f^{(i+1)}(t)(x-t)^i - i f^{(i)}(t)(x-t)^{i-1} \right) \\
      &= f'(t) + \sum_{i=0}^{n} \frac{f^{(i+1)}(t)}{i!}(x-t)^i - \sum_{i=1}^{n} \frac{i f^{(i)}(t)}{i!}(x-t)^{i-1}
\end{align*}
\]
Note that \( \frac{i f^{(i)}(t)}{i!} = \frac{f^{(i)}(t)}{(i-1)!} \), so:

\[
\sum_{i=1}^n \frac{i f^{(i)}(t)}{i!} (x-t)^{i-1} = \sum_{j=0}^{n-1} \frac{f^{(j+1)}(t)}{j!}(x-t)^j
\]
(where \( j = i-1 \)).

Thus, the difference telescopes from \( i=1 \) to \( i=n-1 \):
\[
\begin{align*}
q'(t) &= f'(t) + \frac{f^{(n+1)}(t)}{n!}(x-t)^n - f'(t) \\
      &= \frac{f^{(n+1)}(t)}{n!}(x-t)^n
\end{align*}
\]

---

## **Step 5: Setting \( g'(c) = 0 \) and Solving for \( R(x) \)**

At \( t = c \):
\[
0 = -q'(c) + R(x)\frac{(n+1)(x-c)^n}{(x-a)^{n+1}}
\]
So,
\[
q'(c) = R(x)\frac{(n+1)(x-c)^n}{(x-a)^{n+1}}
\]
Since \( q'(c) = \frac{f^{(n+1)}(c)}{n!}(x-c)^n \), so:
\[
\frac{f^{(n+1)}(c)}{n!}(x-c)^n = R(x)\frac{(n+1)(x-c)^n}{(x-a)^{n+1}}
\]
If \( x \neq c \), divide both sides by \( (x-c)^n \) (which is nonzero except possibly at endpoints):
\[
\frac{f^{(n+1)}(c)}{n!} = R(x)\frac{(n+1)}{(x-a)^{n+1}}
\]
So,
\[
R(x) = \frac{f^{(n+1)}(c)}{(n+1)!}(x-a)^{n+1}
\]

This formula is valid for \( x \neq a \). For \( x = a \), both sides are zero.

---

## **Step 6: Bounds on the Remainder**

If \( f^{(n+1)} \) is bounded on the interval between \( a \) and \( x \),
\[
m \leq f^{(n+1)}(t) \leq M
\]
for all \( t \) between \( a \) and \( x \), then
\[
\frac{m}{(n+1)!} (x-a)^{n+1} \leq R(x) \leq \frac{M}{(n+1)!} (x-a)^{n+1}
\]

---

## **Conclusion**

For any \( f \) with continuous \( (n+1) \)-st derivative on an interval containing \( a \) and \( x \), and for any \( x \neq a \), there exists \( c \) between \( a \) and \( x \) such that:
\[
f(x) = \sum_{i=0}^n \frac{f^{(i)}(a)}{i!}(x-a)^i + \frac{f^{(n+1)}(c)}{(n+1)!}(x-a)^{n+1}
\]

Moreover, the remainder satisfies the bounds above.

---

**Q.E.D.**
