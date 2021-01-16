# Competitive Programming Data Structures and Algorithms

## About
Contains a library of premade templates for common data structures and algorithms found in competitive programming

## Data Structures

### Segment Tree
* About Segment Trees
	* Use for queries over ranges of data
		* Operations on said ranges must be associative

* Functionality
	* Builds from arr O(N)
	* Updates individual values O(logN)
	* Queries on associative range O(logN)
	* Prints debug elements O(N)
	* Does not currently support lazy propagation
* segment_tree.cpp
	* Declare with c++ template
		* e.g. `SegTree<long long> seg_tree(size, default, associativeFunction);`
	* Debug print requires declared template type supports `<<` insertion operator
		* Stream io with `<<` is slower than `stdio.h` in C++ so be careful with using this everywhere
	
* segment_tree.py
	* Note that this class has not been optimized for maximized efficiency
		* All that can be promised is operations in accordance with the previously defined runtime complexities

---

### Suffix Array
* About Suffix Arrays
	* By sorting the suffixes of a string a lot of powerful computation can be done
		* These often involve using some sort of binary search query on the data
	* A suffix array is efficiently stored as an array of integers representing the order of the suffixes by their indices
	* Alongside the suffix array is the longest common prefix (LCP) array
		* This array contains between suffixes *adjacent to each other in the suffix array* the length of their common prefix
		* What is important about such is the following:
			* For any list of sorted strings, the LCP between any two strings is the minimum value in between their indices in the LCP array
			* Thus any range minimum query (RMQ) structure can be used to calculate the longest common prefix between any two suffixes in log(N) time
* Functionality
	* Constructs the suffix array (O(NlogN)) and LCP array (O(N))
	* The corresponding suffix array and LCP array are easily accessible for computation
	* TODO: will add a basic segment tree for LCP queries (may want to change to Sparse Query Data Table)
* suffix_array.cpp
	* Be sure to read the commonts at the top of the namespace
	* order of construction must be followed precisely
	* an example declaration follows:
```cpp
std::cin >> SuffixArray::str;
SuffixArray::str += '$';		// Having a trailing character is necessary for the sort to perform properly
SuffixArray::size = SuffixArray::str.length();
SuffixArray::buildSA();
SuffixArray::buildLCP();
SuffixArray::printSA();
SuffixArray::printLCP();
```

---

### reTrieval Tree

---

### Union Find

---

### Matrix
* Work in conjunction with Floyd Warshalls

---
