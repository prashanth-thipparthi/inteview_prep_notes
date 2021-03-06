# Searching

## Basic Approaches
Two basic algorithms exists.
 - **Sequential Search**
	 - time complexity - O (n)
	 - generally faster up to 20 elements
 - **Binary Search**
	 - time complexity - O (log n)
	 - input array must be sorted
	 - efficient when n > 100 elements

## Identifying variant of searching algorithm

 - ### Are certain items accessed more often than other ones?
	 - Reduce comparisons in **sequential search** by placing most popular items in front and least popular towards end.
	 - For **binary search** trees, keeping most popular ones to root is quite complicated, that too ensuring BST won't end up like sequential search.
		 - Optimal BST implementation is needed (keeping it balanced)

 - ### Might access frequencies change over time?
	- **self-organizing lists**: order of keys change in response to the queries.
		- eg: **move-to-front**: most recently searched item will be moved to front of list, from its current position
		- **splay trees**: self-organizing BST's that rotate each searched node to the root. [implementation reference - search for slay](http://www.cs.princeton.edu/~rs/Algs3.java1-4/code.txt)
			- offer excellent amortized performance guarantees.

 - ### Is the search key close by?
	- We know target key is to the right of position **p**, and we know its nearby
	- Try out **one-sided binary search** technique:
		- try larger intervals (p+1, p+2, P+4, p+8, p+16, ...) to the right until we find a key to the right of our target
		- we will now have a window containing target and peform the regular binary search.
		- **this technique** is particularly useful in unbounded search problems.

 - ### Is my data structure sitting on external memory?
	 - Binary search is not as very effective for too larger number of keys 
	 - **B-trees** which cluster keys into pages to minimize the number of disk accesses per search.

 - ### Can I guess where the key should be?
	 - **interpolation search** where we explore our understanding of distribution of the keys to guess where to look next.
		 - eg: telephone book
		 - need to work very hard to optimize this search algorithm so it performs more efficient than binary search.


	
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwOTQxMDc4MiwtMzI5NzQ5NjI5LDEyNz
g0MDY4OTQsMTA0MDQ5NDE5M119
-->