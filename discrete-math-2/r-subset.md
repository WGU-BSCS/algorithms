# R-Subsets in Lexigraphical Order
## Complexity = 
## Uses: 
1. zybooks
- names, phone numbers
- databse management - create management programs which are accurate and efficient
## Code: 
1. [resource clickable title](web address of resource)
- 
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

// takes as input two natural numbers, r and n, such that r =< n
// outputs all the r-subsets of the set {1, 2,...,n-1, n}
// elements in a subset always listed in increasing order
// uses lex order to ensure that each subset is generated exactly once
	// first r-subset of {1, 2,..., n-1, n} == {1, 2,..., r-1, r}
	// last r-subset == {n-r+1,..., n-1, n}
// r = length of subset
// n = highest number

function NextSubset(n, {s_1, s_2, ..., s_r})
	let k be the largest index such that s_k < (n - r + k)
		if no such k exsists then {s_1, s_2, ..., s_r} is the last r-subset of (1, 2, ..., n})

	s_k = (s_k) + 1
	for j = k+1 to r
		s_j = s_(j-1) + 1
	end for

	return({s_1, s_2, ..., s_r})
end function

function GenLexSubsets(r, n)

	Initialize S = {1, 2, …, r-1, r}
	Output P
	While S ≠ {n-r+1, …, n-1, n},
		S = NextSubset(n, S)
		Output S
	end while
end function
```