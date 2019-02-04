# Description of an algorithm
- A name for the alorithm
- A brief description of the task performed by the algorithm
- A description of the task performed by the algorithm
- A sequence of steps to follow

# if-statements
## Complexity =
If (condition)
	Step 1
	Step 2 
	...
	Step n
End-if

If (condition)
	Steps
Else
	Steps
End-if

# for-loop
## Complexity =
For i = s to t
    Step 1
    Step 2
    . . .
    Step n
End-for

# while-loop
### Complexity =
While ( condition )
    Step 1
    Step 2
    . . .
    Step n
End-while

# nested loops
## Complexity = n^num-of-nested loops

//set your counter/iterator
count := 0

//loop 1
For i = 1 to 3

	  //loop 2
      For j = 1 to 4
            count := count + i ⋅ j
      End-for

End-for

# Fibonacci-1
## Complexity =
F[1] :=1
F[2]:=1
For i:=3 to n
    F[i] := F[i-1]+F[i- 2]
End-for
Return (F[n])

# Bubble-Sort
## Complexity = n^2 <-- not good for very large sets of data!
### Uses:
[Stack Overflow](https://stackoverflow.com/questions/276113/what-is-a-bubble-sort-good-for)
	- Not used widely in "real world" situations
	- Very fast sorting of extremely small/nearly sorted set of data 
	- insertion sort will usually be better for same processes
	- more of an instroductory sorting algorithm for students
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

# Linear-Search
## Compelxity = n

For i: = 1 to n
    If a[i]: = V, return (true)
End-for
Return(false)