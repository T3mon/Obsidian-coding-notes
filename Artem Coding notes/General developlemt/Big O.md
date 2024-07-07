![[Pasted image 20240629185440.png]][Big O](https://www.youtube.com/watch?v=XMUe3zFhM5c&ab_channel=BroCode) notation helps to:
- **Compare Algorithms**: It provides a way to compare the efficiency of different algorithms.
- **Predict Performance**: It helps in predicting how an algorithm will perform as the input size increases.
### Common Big O Notations
1. **O(1) - [Constant Time](<https://levelup.gitconnected.com/unlocking-coding-interview-success-mastering-big-o-notation-net-c-73b4ef1554c5#:~:text=O(1)%20%E2%80%94%20Constant%20Complexity>)**:
    - The runtime of the algorithm is constant and does not change with the input size.
    - Example: Accessing an element in an [[array]] by index.
2. **O(log n) - Logarithmic Time**:
    - The runtime grows logarithmically as the input size increases. This usually happens in algorithms that divide the problem in half each time.
    - Example: Binary search.
3. **O(n) - Linear Time**:
    - The runtime grows linearly with the input size.
    - Example: Iterating through all elements in a [[list]].
4. **O(n log n) - Linearithmic Time**:
    - The runtime grows in proportion to nnn and log⁡n\log nlogn. This is common in efficient sorting algorithms.
    - Example: Merge sort, quicksort.
5. **O(n^2) - Quadratic Time**:
    - The runtime grows quadratically with the input size. This is often seen in algorithms with nested loops.
    - Example: Bubble sort, insertion sort.
6. **O(n^3) - Cubic Time**:
    - The runtime grows cubically with the input size. This is typical of algorithms with three nested loops.
    - Example: Naive matrix multiplication.
7. **O(2^n) - Exponential Time**:
    - The runtime grows exponentially with the input size. Algorithms with this complexity are usually impractical for large inputs.
    - Example: Recursive calculation of Fibonacci numbers.
8. **O(n!) - Factorial Time**:
    - The runtime grows factorially with the input size. This is seen in algorithms that generate all permutations of a set.
    - Example: Solving the traveling salesman problem using brute-force search.
### How to Determine Big O Complexity
1. **Identify the Basic Operations**: Find the most significant operation that determines the runtime, such as comparisons in sorting.
2. **Count the Operations**: Determine how many times this basic operation is performed relative to the input size.
3. **Express the Count Using Big O Notation**: Simplify the expression to the most significant term, ignoring constants and lower-order terms.

**Example 1: Linear Search** 
```Csharp
	bool LinearSearch(int[] array, int target) {
	    for (int i = 0; i < array.Length; i++) {
	        if (array[i] == target) {
	            return true;
	        }
	    }
	    return false;
	}
```
- **Complexity**: O(n)
- **Explanation**: In the worst case, the algorithm iterates through all elements.
### Example 2: Bubble Sort
```Csharp
	void BubbleSort(int[] array) {
	    int n = array.Length;
	    for (int i = 0; i < n - 1; i++) {
	        for (int j = 0; j < n - i - 1; j++) {
	            if (array[j] > array[j + 1]) {
	                int temp = array[j];
	                array[j] = array[j + 1];
	                array[j + 1] = temp;
	            }
	        }
	    }
	}
```
- **Complexity**: O(n^2)
- **Explanation**: There are two nested loops, each running n times in the worst case.