# Introduction #

Write a program to implement an arbitrary-precision integer and to compute the 20th Mersenne prime.


# Digit Storage #
Integer is implemented in such a way that the digits are stored backwards, from lowest decimal place to highest. This allows trailing zeros to be ignored easily and the calculation of addition, subtraction, multiplication, and division to be performed in a straightforward manner. It also allows Integer to grow in value without needing to move digits around inside the container.

# Multiplication and Division #
Multiplication and division are implemented in the same manner that long division and long division are carried out. There is a small optimization in multiplication that allows it to skip a loop iteration when a 0 is one of the digits being multiplied.

This results in O(m\*n) for both multiplication and division.

# Pow #
Pow was implemented by using the following insights:

b2e == b\*be

b2e + 1 == b\*be times b

Thus, pow is O(ln(n)) ignoring the multiplication's order.