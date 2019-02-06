# Lexigraphical Order
## Complexity = 
## Uses: 
1. Zybooks:
- "A package delivery service must deliver 20 packages to 20 different locations. What is the best order to deliver the packages
that minimizes the total distance traveled by the driver?"
	- One approach to finding the shortest route is to enumerate all permutations of the 20 locations and calculate the total
	disance traveled by if the driver delivers the packages in the given order.
- "A company has 100 employees. For every pair of people, the managers know whether those two people are compatible. The
managers would like to find a group of 25 people to work together on a project such that every pair of people in the group is
compatible."
	- One approach to finding such a group is to enumerate all 25-subsets of the 100 employees and check whehter everyone
	in the group is mutually compatible.
- **NOTE:** A well-defined order imposed on the n-tuples i useful to systematically generate all the elements in a set of n-tuples.
	- Generate from smallest to largest to ensure each n-tuple is generated exactly once
	
## Code: 
1. Zybooks
- 
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

// takes as input a permutation P and returns the smallest permutation that is larger than P
// in other words, the "next" permutation in the lex order
function NextPerm(p_1, p_2, ..., p_n)
	let k be the largest index such that p_k < p_(k+1)
		if no such k exists then (p_1, p_2, ..., p_n) is the last permutation
	
	let j be the largest index such that p_j > p_k
	swap p_j and p_k
	revers the order of p_(k+1),...,p_n

	return(p_1, p_2,...,p_n)
end function

//generates all the permutations of a set size *n*
//starts with the first permutation in lex order
//keeps generating next permutation until last permutation is reached
function GenLexPermutations(n)

	Initialize P = (1,2, ..., n-1, n)
	Output P
	While P does not equal (n, n-1, ..., 2, 1),
		P = NextPerm(P)
		Output P
	End while
end function

```

2. [Wikipedia](https://en.wikipedia.org/wiki/Permutation)
- 
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}
//Algorithm steps to generate the next permutation lexicographically after a given permutation. It changes 
//the given permutation in-place
1. Find the largest index k such that a[k] < a[k+1]. If no such exists, the permutation is the last permutation
2. Find the largest index j greater than k such that a[k] < a[j]
3. Swap the value of a[k] with a[j]
4. Reverse the sequence from a[k+1] up to and including the final element a[n]

```
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

EXAMPLE:
//Given the sequence [1, 2, 3, 4] (which is in increasing order), and given that the incex is zero-based, the steps are as follows:

1. index k = 2 because 3 is placed at an index that satisfies condition of being the largest index that is stil less than a[k+1] which is 4.
2. index j = 3, because 4 is the only value in the sequence that is greater than 3 in order to satisfy the condition a[k] < a[j].
3. The values of a[2] and a[3] are swapped to form the new sequence [1, 2, 3, 4]
4. The sequence after k-index a[2] to the final element is reversed. Because only one value lies after this index (the 3)
the sequence remains unchanged in this instance. Thus the lexicographic successor of the intial state is permuted: [1, 2, 4, 3]
5. next lex => [1, 3, 2, 4] => 24th perm [4, 3, 2, 1] at which point a<[k] < a[k+1] does not exist == last permutation


```

## Other Algorithms to Try:
1. [Steinhaus-Johnson-Trotter algorithm](https://en.wikipedia.org/wiki/Steinhaus%E2%80%93Johnson%E2%80%93Trotter_algorithm)
2. [Heap's Algorithm](https://en.wikipedia.org/wiki/Heap%27s_algorithm) - supposed to be fastest

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE}

//recursive format

procedure generate(n : integer, A : array of any):
    if n = 1 then
          output(A)
    else
        for i := 0; i < n - 1; i += 1 do
            generate(n - 1, A)
            if n is even then
                swap(A[i], A[n-1])
            else
                swap(A[0], A[n-1])
            end if
        end for
        generate(n - 1, A)
    end if


// non-recursive 

procedure generate(n : integer, A : array of any):
    c : array of int

    for i := 0; i < n; i += 1 do
        c[i] := 0
    end for

    output(A)
    
    i := 0;
    while i < n do
        if  c[i] < i then
            if i is even then
                swap(A[0], A[i])
            else
                swap(A[c[i]], A[i])
            end if
            output(A)
            c[i] += 1
            i := 0
        else
            c[i] := 0
            i += 1
        end if
    end while

```