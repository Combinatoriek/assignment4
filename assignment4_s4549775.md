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
## b
## c
## d

# 12
## a
## b

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

	$r^2 - c_1 r^1 - c_2 = 0$

## c

# 14
