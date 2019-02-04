# Bubble-Sort
## Complexity = n^2 <-- not good for very large sets of data!
## Uses:
1. [Stack Overflow](https://stackoverflow.com/questions/276113/what-is-a-bubble-sort-good-for)
- Not used widely in "real world" situations
- Very fast sorting of extremely small/nearly sorted set of data 
- insertion sort will usually be better for same processes
- more of an introdution to sorting algorithms for students
## Code:
1. [Stack Overflow](https://stackoverflow.com/questions/276113/what-is-a-bubble-sort-good-for)
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE }

For i: = 1 to n - 1
    For j: = i + 1 to n
        If a[i] < a[j]
            b: = a[i]
            a[i]: = a[j]
            a[j]: = b
        End-if
    End-for
End-for
Return (a[1]....a[n])

```
