

# Division Algorithm
## Complexity = n

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}
 //Input: Integers n and d > 0
 //Output: q = n div d, and r=n mod d
 
 //case 1: n >= 0
q := 0
r := n
While ( r ≥ d )
      q := q + 1
      r := r - d
End-While

```
# Exponentiation modulo
## Complexity = 
## Uses: 
1. [Wikipedia](https://en.wikipedia.org/wiki/Modular_exponentiation)
- type of exponentiation performed over a modulus
- public-key cryptography
- c = b^e mod m 
	- b = base
	- e = exponent
	- m = modulus
	- RULE: 0 <= c < m

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

//memory efficient method
function modular_pow(base, exponent, modulus)
    if modulus = 1 then return 0 
    c := 1
    for e_prime = 0 to exponent-1
        c := (c * base) mod modulus
    return c

```
2. Zybooks
- For larger exponents
- Taking partial results modulo n does not change the final result

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}
b = base number
n = exponent
m = modulus number
p = base number //this is used for holding the new value

function expo_mod

	For i = 1 to (n - 1)
		p = (b*p) mod m
	end-for

	return(p)

end function
```

# Prime Factorization
## Complexity = 
## Uses:
1. [Geek](https://www.geek.com/news/geek-answers-why-should-we-care-about-prime-numbers-1574269/)
- prime factorization trees
- cryptography - encryption - cc processing, etc.
- number theory - building blocks of whole numbers
2. Zybooks
- encryption/decryption
- any website where you log
	- rely on keys == hard to find prime numbers
		- extremely difficult to "undo"
## Code: 
1. [GeeksforGeeks](https://www.geeksforgeeks.org/print-all-prime-factors-of-a-given-number/)

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

n = integer to find primes of
// A function to print all prime factors of a given number
primeFactors(n)
	//Print the number of 2s that divide n
	while (n%2 == 0)
		output: "%d ", 2 
		n = n/2
	end while

	//n must not be odd at this point. so we can skip
	//one element (Note: i = i + 2)
	for i = 3; i <= sqrt(int); i = i +2
		//while i divides n, print i and divide n
		while n%i == 0
			output: "%d ", i
			n = n/i
		end while
	end for
	
	//This condition is to handle the case when n 
	//is a prime number greater than 2
	if n > 2 
		output: "%d ", n
	end if
end function

```

# GCD
## Complexity = nlogn
## Uses: 
1.  number theory
	- modular arithmetic - encryption/decryption --> ex: RSA
2.  to simplify fractions
3. [CodeChef](https://discuss.codechef.com/questions/107499/applications-of-gcd-in-competitive-programming)
- Eular Totient Function
	-counts the positive integers up to a given integer n that are relatively prime to n.
- Modular Multiplicative Inverse
	-  ax = 1(mod m) or (1/a)mod 
- Extended Euclid Algorithm
- LCM(a,b) = a*b/(gcd(a,b))
## Code: 
1. [COMP 170 Examples](https://books.cs.luc.edu/introcs-csharp/while/gcdexamples.html)
- //gcd(a,b)=gcd(b, a mod b )
  //gcd(a,0)=a

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

//BRUTE FORCE 

GCD(int a, int b)
	n = math.min(a, b) //math.min returns lowest number passed into it
	gcd = 1
	i = 1

	while i <= n 
		if (a % i == 0) && (b % i == 0)
			gcd = i
		end if

		i++
	end while

	return gcd
end function
```

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}
//RECURSIVE GCD

// Return the gcd of nonegative nums
//not both 0

GCD(int a, int b)
	if b == 0 //base case
		return a
	else
		return GCD(b, a%b) // recursion
	end if
end function
```
2. [Stack Overflow- efficiency](https://cs.stackexchange.com/questions/1447/what-is-most-efficient-for-gcd)

# LCM
## Complexity = 
## Uses: 
1. Zybooks
- 
2. [Quora](https://www.quora.com/What-are-some-common-applications-of-GCD-and-LCM-in-programming)
- finding common denominators when adding or sutracting fractions
- to find out about an event and its repetition
- to get multiple items to have enough
- an example would be: if a contest *A* happens every 2nd month, and a contest *B* happens every 3rd month, when will they collide?
## Code: 
1. [GeeksforGeeks](https://www.geeksforgeeks.org/program-to-find-lcm-of-two-numbers/)
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

//LCM(a, b) = [(a * b) / GCD( a, b)]
//see recursive version of GCD above

function LCM(int a, int b)
	return (a*b)/GCD(a, b)
end function

```


