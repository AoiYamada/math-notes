# Extended euclidean algorithm for polynomials

a(x) = (x + 1)^3
b(x) = (x - 1)^3
求 -2 = a(x)g(x) + b(x)h(x)

WolframAlpha:
PolynomialExtendedGCD[ (x + 1)^3, (x-1)^3 ]

先 expand
a(x) = (x + 1)^3 = x^3 + 3x^2 + 3x + 1
b(x) = (x - 1)^3 = x^3 - 3x^2 + 3x - 1

iterate:
x^3 + 3x^2 + 3x + 1 = (x^3 - 3x^2 + 3x - 1)(1) + 6x^2 + 2
x^3 - 3x^2 + 3x - 1 = (6x^2 + 2)(x/6 - 1/2) + 8x/3
6x^2 + 2 = (8x/3)(9x/4) + 2
8x/3 = (2)(4x/3)

reverse from the 2nd last equation
2 = (6x^2 + 2) - (8x/3)(9x/4)

substitute 8x/3 by (x^3 - 3x^2 + 3x - 1) - (6x^2 + 2)(x/6 - 1/2)
2 = (6x^2 + 2) - ((x^3 - 3x^2 + 3x - 1) - (6x^2 + 2)(x/6 - 1/2))(9x/4)

keep (6x^2 + 2) and reorganize the rest
2 = (6x^2 + 2)(1 + (x/6 - 1/2)(9x/4)) - (x^3 - 3x^2 + 3x - 1 )(9x/4)
2 = (6x^2 + 2)(3x^2/8 - 9x/8 + 1) - (x^3 - 3x^2 + 3x - 1 )(9x/4)

substitute (6x^2 + 2) by (x^3 + 3x^2 + 3x + 1) - (x^3 - 3x^2 + 3x - 1)
2 = ((x^3 + 3x^2 + 3x + 1) - (x^3 - 3x^2 + 3x - 1))(3x^2/8 - 9x/8 + 1) - (x^3 - 3x^2 + 3x - 1)(9x/4)

keep (x^3 + 3x^2 + 3x + 1) = a(x) and (x^3 - 3x^2 + 3x - 1) = b(x), reorganize the rest
2 = (a(x) - b(x))(3x^2/8 - 9x/8 + 1) - b(x)(9x/4)
2 = a(x)(3x^2/8 - 9x/8 + 1) - b(x)(3x^2/8 - 9x/8 + 1 + 9x/4)
2 = a(x)(3x^2/8 - 9x/8 + 1) - b(x)(3x^2/8 + 9x/8 + 1)
-2 = a(x)(-3x^2/8 + 9x/8 - 1) + b(x)(3x^2/8 + 9x/8 + 1)

得
g(x) = -3x^2/8 + 9x/8 - 1
h(x) = 3x^2/8 + 9x/8 + 1

[參考](https://www.billcookmath.com/sage/algebra/Euclidean_algorithm-poly.html)
