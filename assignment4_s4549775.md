% Assignment 4\
	Group 4
---
title: Assignment 4
author: Hendrik Werner s4549775
date: \today
fontsize: 12pt
geometry: margin=5em
---

# 9
## a
Nickels are worth 5 cents, and Dimes 10 cents. $a_n$ is the number of possibilities to pay a toll of $n$ cents with only nickels and dimes.

When putting the last coin in, it is either a dime, or a nickel. If it was a dime we put in $n - 10$ cents before, so there are $a_{n - 10}$ ways to do this. If the last coin was a nickel, we put in $n - 5$ cents before, so there are $a_{n - 5}$ ways to do this.

We can derive the following recurrence relation:

* $a_0 = 1$
* $a_5 = 1$
* $a_n = a_{n - 5} + a_{n - 10}$ for $n \geq 10$

## b
Since the recurrence relation is recursive, we need to calculate all values up to 45 cents.

$n$|possibilities
---|-------------
0|1
5|1
10|2
15|3
20|5
25|8
30|13
35|21
40|34
45|55

A toll of 45 cents can be paid in $a_{45} = 55$ ways with nickels and dimes.

# 10
There are red, green, and gray walkways slates. $a_n$ is the number of possibilities to lay out $n$ walkways slate tiles, without two red tiles touching.

## a
When placing the $n$th tile, it could be a red, green, or gray one. If it is a green or gray slate, then the color of the previous tile does not matter. We can place the previous tiles in $a_{n - 1}$ ways.

If the $n$th slate is red, the previous slate must be green or gray. This means that there are $2 * a_{n - 2}$ possibilities.

We can derive the following recurrence relation:
$a_n = 2 a_{n - 1} + 2 a_{n - 2}$ for $n \geq 2$

## b
Our recurrence relation from (a) is defined for $n \geq 2$, so we need to know $a_0$, and $a_1$:

$n$|possibilities|$a_n$
---|:-----------:|-----
0|""|1
1|"green", "gray", "red"|3

## c
We need to start from the beginning again, and work our way up.

$n$|$a_n$
---|-----
0|1
1|3
2|8
3|22
4|60
5|164
6|448
7|1224

We can lay out a walkway with 7 tiles in $a_7 = 1224$ ways.

# 11
## a
m is the medium disk, and s the small disk.

$n = 1$

move|peg 1|peg 2|peg 3
----|-----|-----|-----
0|s
1||s
2|||s

$a_1 = 2$

$n = 2$

move|peg 1|peg 2|peg 3
----|-----|-----|-----
0|ms
1|m|s
2|m||s
3||m|s
4||ms
5|s|m
6|s||m
7||s|m
8|||ms

$\begin{aligned}
	a_2 &= 8\\
	&= 3 a_1 + 2
\end{aligned}$

$a_n = 3 a_{n - 1} + 2$

## b
## c
## d

# 12
If I understand the problem correctly, then everyone beginning from person 1 kills his left neighbor until only one person is left. So person one begins by killing person 2, person 3 kills person 4, and so on.

## a
$n$|$J(n)$|order of death
---|------|---------------
1|1
2|1|2
3|3|2, 1
4|1|2, 4, 3
5|3|2, 4, 1, 5
6|5|2, 4, 6, 3, 1
7|7|2, 4, 6, 1, 5, 3
8|1|2, 4, 6, 8, 3, 7, 5
9|3|2, 4, 6, 8, 1, 5, 9, 7
10|5|2, 4, 6, 8, 10, 3, 7, 1, 9
11|7|2, 4, 6, 8, 10, 1, 5, 9, 3, 11
12|9|2, 4, 6, 8, 10, 12, 3, 7, 11, 5, 1
13|11|2, 4, 6, 8, 10, 12, 1, 5, 9, 13, 7, 3
14|13|2, 4, 6, 8, 10, 12, 14, 3, 7, 11, 1, 9, 5
15|15|2, 4, 6, 8, 10, 12, 14, 1, 5, 9, 13, 3, 11, 7
16|1|2, 4, 8, 10, 12, 14, 16, 3, 7, 11, 15, 5, 13, 9

## b
If we write $n$ as $2^m + k$ like this

$n = 2^m + k$|$m$|$k$|$J(n)$
-------------|---|---|------
1|0|0|1
2|1|0|1
3|1|1|3
4|2|0|1
5|2|1|3
6|2|2|5
7|2|3|7
8|3|0|1

we see that $J(n) = 2k + 1$.

This makes sense because after $k$ people have been killed it is the turn of person $2k + 1$, and there are $2^m$ people left, so after every round, half of the people have been eliminated ($2^{m - 1}, \dots, 2^0$), and it is the turn of person $2k + 1$ again. This pattern repeats until everybody else is dead.

# 13
## a
$a_n = a_{n - 1}$ for $n \geq 1, a_0 = 2$

1. This recurrence relation is already in the normal form.

	$c_1 = 1$
2. The characteristic equation is

	$r^1 - c_1 = r - 1 = 0$
3. We need to find the root $r$ by solving $r - 1 = 0$.

	$r = 1$
4. The general solution is

	$a_n = \alpha_1 c_1^n$

5. Now we fill in the initial conditions, to calculate $\alpha_1$.

	$\alpha_1 = 2$

## b
$a_n + 4 a_{n - 2} = -4 a_{n - 1}, a_0 = 0, a_1 = 1$

1. The normal form is

	$a_n = -4 a_{n - 1} -4 a_{n - 2}$

2. The characteristic equation is

	$r^2 - c_1 r^1 - c_2 = r^2 + 4r + 4 = 0$

3. We need to find the roots $r_1, r_2$ by solving the characteristic equation.

	$r^2 + 4r + 4 = (r + 2)(r + 2) = 0$, so $r_1 = r_2 = -2$

4. The general solution is

	$\begin{aligned}
		a_n &= \alpha_1 r_1^n + n \alpha_2 r_2^n\\
		&= \alpha_1 (-2)^n + n \alpha_2 (-2)^n
	\end{aligned}$

5. Now we fill in the initial conditions to determine $\alpha_1, \alpha_2$

	$\begin{aligned}
		0 &= \alpha_1 (-2)^0 + 0 \alpha_2 (-2)^0\\
		&= \alpha_1
	\end{aligned}$

	$\begin{aligned}
		1 &= \alpha_1 (-2)^1 + 1 * \alpha_2 (-2)^1\\
		&= -2 \alpha_1 -2 \alpha_2\\
		&= -2 \alpha_2
	\end{aligned}$

	$\alpha_1 = 0, \alpha_2 = -\frac{1}{2}$

## c

$a_n = \dfrac{a_{n - 2}}{4}$ for $n \geq 2, a_0 = 1, a_1 = 0$

1. The normal form is

	$a_n = 0 a_{n - 1} + \frac{1}{4} a_{n - 2}$

2. The characteristic equation is

	$r^2 - c_1 r^1 - c_2 = r^2 - 0 r - \frac{1}{4} = r^2 - \frac{1}{4} = 0$

3. We need to find the roots by solving the characteristic equation

	$\begin{aligned}
		r^2 - \frac{1}{4} &= 0\\
		r^2 &= \frac{1}{4}
	\end{aligned}$

	$r_1 = \frac{1}{2}, r_2 = -\frac{1}{2}$

4. The general solution is

	$\begin{aligned}
		a_n &= \alpha_1 r_1^n + \alpha_2 r_2^n\\
		&= \alpha_1 (\frac{1}{2})^n + \alpha_2 (-\frac{1}{2})^n\\
	\end{aligned}$

5. By filling in the initial conditions we can solve for $\alpha_1, \alpha_2$.

	$\begin{aligned}
		1 &= \alpha_1 (\frac{1}{2})^0 + \alpha_2 (-\frac{1}{2})^0\\
		&= \alpha_2 + \alpha_2
	\end{aligned}$

	$\begin{aligned}
		0 &= \alpha_1 (\frac{1}{2})^1 + \alpha_2 (-\frac{1}{2})^1\\
		&= \alpha_1 - \alpha_2
	\end{aligned}$

	$\alpha_1 = \frac{1}{2}, \alpha_2 = -\frac{1}{2}$

# 14
