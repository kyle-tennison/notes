# GRE Quant Notes


## Sum of Integers in an Interval

![[image-39.png]]

This pivots on the idea that every end-start comination will add up to the same thing. For an even set of numbers, this is very easy; for an odd set, you need to individually include the number in the middle.

The middle number will be $\text{ceil}(\text{end}/2)$. 

Example:
1-59 *inclusive*

The middle number is $ceil(29.5) = 30$. 

That means there are $58/2=29$ combinations that add up to $59+1=60$, which equates to $29 \times 60 + 30 = 1770$


### Factors & Divisors

Both the same thing. 

The *factor* of some integer will yield an integer upon division. For instance, in $10/2=5$, 2 in the factor.

For factorials, any combination of factors is also a factor:

![[image-40.png]]

You can use any number of these factors to "build" a factor.

You can also think of "decomposing" factors into more factors. For instance, you can decompose $4$ into $2^2$, or $8$ into $2^3$. Now, you effectively have five $2$ factors, so any value between $2^0$ and $2^5$ will be a factor if $15!$. 

---

If you want to find which values are *not factors* of a factorial, you can look at prime numbers larger than the factorial base. These cannot (by definition) "decompose" into any other factors. 

So, prime numbers *larger* than the factorial base (e.g. $20$ in $20!$) *and their multiples* will NOT be factors of factorials. 

## Divisibility Rules


| Number | Rule                                    |
| ------ | --------------------------------------- |
| 1      | Always                                  |
| 2      | is even                                 |
| 3      | sum of digits divisible by 3            |
| 4      | last 2 digits divisible by 4            |
| 5      | ends in 0 or 5                          |
| 6      | even *and* sum of digits divisible by 3 |
| 7      | cooked                                  |
| 8      | last 3 digits divisible by 8            |
| 9      | last 3 digits are divisible by 9        |
| 10     | duh                                     |
| 11     | below                                   |

![[image-41.png|358x154]]

If sum of digits in alternating sign is zero OR divisible by 11, then the number is divisible by 11.

## Is it Prime?

Given a random number $x$ and asked to determine if it's prime:

1. List all other primes whose squares are less than $x$
2. Divide $x$ by each of these primes. If it is divisible by any of these, it's not prime; otherwise it is.

## GCF  & LCM

For **Greatest Common Factor**, 
	Literally just list the factors of both numbers and pick the biggest.

For **Least Common Multiple**
	List multiples of each number, one at a time increasing until they match.

---

If you add 1 to an integer, there will be a whole new set of factors that are not shared with the original number (besides the factor 1 itself). More generally, adding an integer $n$ to some number $x$, i.e. $x+n=y$ , will necessarily make the factors of $x$ *that are greater than* $n$ **not** be factors of $y$.

---

## Number of multiples in a Series
The **number of multiples in a series** is given by:

$$\frac{\text{last}-\text{first}}{n}+1$$

where $n$ the "how many multiples of $n$ between ..."

Note, $\text{last}$ and $\text{first}$ refer to the last and first *multiples*, not simply the bounds of the series. So, unless the series has ends that are multiples of $n$ AND the question states inclusivity, the $\text{last}$ and $\text{first}$ will *not* refer to the series bounds. 

## Sum of Multiples in a Series

Just like the [Sum of Integers in an Interval](#Sum%20of%20Integers%20in%20an%20Interval), the pattern exists that:

![[image-42.png|438x206]]

the sum of each end of the series will have the same quantity. Multiplying this by the number of pairs will work easily.

If the interval is large and you don't want to write out all of them:

1. Look at the end values, sum these, let that value be $x$
2. Compute the [Number of multiples in a Series](#Number%20of%20multiples%20in%20a%20Series); let this be $y$
	1. If the value $y$ is even, multiply it's half with $x$. The answer is $x(y/2)$
		1. If they're not even, you need the middle number, which will always be $x/2$. The answer is now $x(\frac{y-1}{2})+x/2$ 