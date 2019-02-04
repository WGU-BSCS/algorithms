# Description of an algorithm
- A name for the alorithm
- A brief description of the task performed by the algorithm
- A description of the task performed by the algorithm
- A sequence of steps to follow


# if-statements
## Complexity = 1
## Uses:
## Code: 
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE }
//if-statement
If (condition)
   Step 1
   Step 2 
   ...
   Step n
End-if

```

```{r, tidy=FALSE, eval=FALSE, highlight=FALSE }
//if-else-statement
If (condition)
	Steps
Else
	Steps
End-if

```

# for-loop
## Complexity = n
## Uses:
## Code: 
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE }

For i = s to t
    Step 1
    Step 2
    . . .
    Step n
End-for

```

# while-loop
### Complexity = n
## Uses:
## Code: 
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE }

While ( condition )
    Step 1
    Step 2
    . . .
    Step n
End-while

```

# Nested Loops
## Complexity = n^num-of-nested loops
## Uses:
## Code: 
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE }

//set your counter/iterator
count := 0

//loop 1
For i = 1 to 3

	  //loop 2
      For j = 1 to 4
            count := count + i ⋅ j
      End-for

End-for

```