# Algorithm Title
## Complexity = 
## Uses: 
<!-- 1. [resource clickable title](web address of resource)
- -->
1. Zybooks
- Primality testing, factoring
- exhaustively searching all possible solutions without using an understanding of the mathematical structure in the problem to eliminate steps
- No test factors pas sqrt(N)
	- if N is a composite number, then N has a factor greater than 1 and at most sqrt(N)
## Code: 
1. Zybooks
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

//FOR FACTORING
Input: Integer N greater than 1.
Output: "Composite" if composite, else "Prime".

function bruteForce(n)

	For x = 2 to floor(sqrt(n))
		  If x evenly divides n,
				Return( "Composite" )
	End-for

	Return( "Prime" )

end function

```