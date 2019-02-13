# Loop Invariant Theorem
## Complexity = 
## Uses: 
1. [Susan S. Epps - Discrete Mathematics with Applications, 4th Edition (2010, Brooks Cole)](https://www.amazon.com/Discrete-Mathematics-Applications-Susanna-Epp/dp/0495391328)
- "Let a **while** loop with guard *G* be given, together with pre- and post-conditions that are 
predicates in the algorithm variables. Also let a predicate *I(n)*, called the **loop invariant**, 
be given. If the following four properties are true then the loop is correct with respect to its pre- and 
post-conditions

I. **Basis Property**: The pre-condition for the loop implies that I(0) is true before
the first iteration of the loop
II. **Inductive Property**: For all integers k >= 0, if the guard *G* and the loop invari-
ant *I(k)* are both true before an iteration of the loop, the *I(k+1)* is true after iteration
of the loop.
III. **Eventually Falsity of Guard**: After a finite number of iterations of the loop,
the guard *G* becomes false.
IV. **Correctiveness of the Post-condition**: if *N* is the least number of iterations after
which *G* is false and *I(N)* is true, then the values of the algorithm variables will be as
specified in the post-condition loop

**Proof**:
For all integers *n>=0*, if the while loop
iterates *n* times, then *I(n)* is true

"
## Code: p.283-284 (PDF)
### in general
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

SET VAR pre-condition for loop
while (G)
	loop body
	none contain branching statements that lead outside the loop
end while
SET VAR post-condition for loop

```
### for a product
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

pre-condition: m is a nonnegative integer, 
x is a real number, i=0, and product=0

while (i != m)
	1. product = product + x
	2. i = i + 1
end while

post-condition: product=m*x

```