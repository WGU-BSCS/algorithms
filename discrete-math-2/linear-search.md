# Linear-Search
## Complexity = n
## Uses:
1.  [tutorials point](https://www.tutorialspoint.com/data_structures_algorithms/linear_search_algorithm.htm)
- simple search algorithm to find an element in a list
	- sequential search is made over all items one by one
	- if a match is found then that particular item is returned, else search continues til the end of data collection
2. [Wikipedia](https://en.wikipedia.org/wiki/Linear_search)
- rarely practical because other search algorithms and schemes
	- alternative algos: [binary search](https://en.wikipedia.org/wiki/Binary_search_algorithm, [hash tables](https://en.wikipedia.org/wiki/Hash_table)
## Code: 
1. [tutorials point](https://www.tutorialspoint.com/data_structures_algorithms/linear_search_algorithm.htm)
```{r, tidy=FALSE, eval=FALSE, highlight=FALSE }

function linear_search (list, value)
	for each item in the list
		if match item == value
			return the item's location
		end if
	end for 
end function
```