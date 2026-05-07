1. Big O Notation - Big O notation is used to describe how an algorithm's time or space usage grows as the input size increases. It focuses on the overall growth pattern instead of exact execution time, making it easier to compare different solutions. The content explains common complexities such as O(1), O(log n), O(n), and O(n^2), how to simplify Big O expressions by ignoring constants and smaller terms, and how loops, nested loops, and extra memory usage affect time and space complexity.

2. Big O of Arrays and Objects - This topic explains how JavaScript arrays and objects behave with Big O. Objects are useful for unordered key-value data and give fast access, insertion, and removal, while searching and methods like Object.keys, Object.values, and Object.entries take O(n). Arrays are useful when order matters, but adding or removing items at the beginning is slower because indexes must shift. It also compares common array methods like push, pop, shift, unshift, concat, slice, splice, sort, map, filter, and reduce.

3. Problem Solving Approach and Patterns - This topic explains how to approach algorithm problems by understanding the problem, exploring examples, breaking the solution into steps, solving or simplifying, and then refactoring. It also introduces common patterns such as frequency counters, multiple pointers, sliding window, and divide and conquer, showing how they can reduce time complexity compared with naive nested-loop solutions.

## Problems

### Frequency Counter - Same

Files:
- `Problems/Frequency Counter/same_naive_solution.js`
- `Problems/Frequency Counter/same_refactored_solution.js`

This problem checks whether every value in the first array has its squared value in the second array with the same frequency. For example, `[1, 2, 3, 2]` and `[9, 1, 4, 4]` should return `true` because `1^2 = 1`, `2^2 = 4` appears twice, and `3^2 = 9`.

The naive solution uses `indexOf` inside a loop and removes matched values with `splice`. It is useful for understanding the problem step by step, but it is slower because searching inside the second array happens repeatedly. This approach has roughly `O(n^2)` time complexity.

The refactored solution uses the frequency counter pattern. It builds objects that count how many times each value appears in both arrays, then compares the counts. This is the better approach when you need to compare two collections by value frequency, such as checking squared values, anagrams, duplicates, or matching grouped data. This approach has `O(n)` time complexity because each array is looped through only a small fixed number of times.

Use the frequency counter pattern when:
- You need to compare two arrays, strings, or collections.
- The order of values does not matter.
- The number of times each value appears does matter.
- A nested loop solution is becoming too slow.

To run the examples, install Node.js and execute:

```bash
node "Problems/Frequency Counter/same_naive_solution.js"
node "Problems/Frequency Counter/same_refactored_solution.js"
```
