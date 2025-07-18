# Probability

## Core Principles

The fundamental probability formula is:

$$P(A) = \frac{\text{Favoriable Outcomes}}{\text{Total Outcomes}}$$

The **compliment rule** is simply:

$$P(\text{not} A) = 1 - P(A)$$



When **adding probabilities**, there are multiple ways to do so:

- *Mutually exclusive*: $P(A \cup B)=P(A)+P(B)$
	- A box contains 3 red balls, 4 blue balls, and 5 green balls. One ball is chosen at random. What is the probability that the ball is *either red or blue*?
- *Not mutually exclusive*: $P(A \cup B) = P(A)+P(B)-P(A \cap B)$  
	- In a class of 30 students:

		* 18 take math
		* 12 take science
		* 5 take both
	  
	 What is the probability that a randomly selected student takes math or science?

	 Math and science are not mutually exclusive (some students take both), so:
	 $$
P(\text{math or science}) = P(\text{math}) + P(\text{science}) - P(\text{both})
$$

$$
= \frac{18}{30} + \frac{12}{30} - \frac{5}{30} = \frac{25}{30} = \frac{5}{6}
$$


When **multiplying** probabilities:

- *Independent events:* $P(A \cap B) = P(A)\cdot P(B)$ 
	- A fair coin is flipped, and a fair die is rolled. What is the probability of getting heads on the coin and a 4 on the die?
- *Dependent Events*: $P(A\cap B) = P(A)\cdot P(B|A)$ 
	- $P(B|A)$ is the probability of $B$ occurring, given that $A$ already occurred. 
	- A bag contains 5 red and 3 blue marbles. Two marbles are drawn *without replacement.
		1. $P(\text{first red}) = \frac{5}{8}$
		2. $P(\text{second red} \mid \text{first red}) = \frac{4}{7}$
		
		$$
		P(\text{both red}) = \frac{5}{8} \cdot \frac{4}{7} = \frac{20}{56} = \frac{5}{14}
		$$

## Counting Principles

**Permutations:**

$$P(n,r) = \frac{n!}{(n-r)!}$$

where $n$ is the total number of items and $r$ are the number of items per selection.

*Example:* How many ways to award 1st, 2nd, and 3rd place from 10 contestants?

$$
n = 10,\quad r = 3 \Rightarrow P(10, 3) = \frac{10!}{(10 - 3)!} = \frac{10!}{7!} = 720
$$
