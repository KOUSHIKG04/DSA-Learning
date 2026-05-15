1. Big O Notation - Big O notation is used to describe how an algorithm's time or space usage grows as the input size increases. It focuses on the overall growth pattern instead of exact execution time, making it easier to compare different solutions. The content explains common complexities such as O(1), O(log n), O(n), and O(n^2), how to simplify Big O expressions by ignoring constants and smaller terms, and how loops, nested loops, and extra memory usage affect time and space complexity.

2. Big O of Arrays and Objects - This topic explains how JavaScript arrays and objects behave with Big O. Objects are useful for unordered key-value data and give fast access, insertion, and removal, while searching and methods like Object.keys, Object.values, and Object.entries take O(n). Arrays are useful when order matters, but adding or removing items at the beginning is slower because indexes must shift. It also compares common array methods like push, pop, shift, unshift, concat, slice, splice, sort, map, filter, and reduce.

3. Problem Solving Approach and Patterns - This topic explains how to approach algorithm problems by understanding the problem, exploring examples, breaking the solution into steps, solving or simplifying, and then refactoring. It also introduces common patterns such as frequency counters, multiple pointers, sliding window, and divide and conquer, showing how they can reduce time complexity compared with naive nested-loop solutions.

4. Recursion - The `07-pdf-slides-recursion.pdf` slides introduce recursion as a function or process that calls itself. The content explains the two essential parts of recursive functions: a base case that stops the recursion and a changed input that moves each call toward that base case. It also covers how recursive calls use the call stack, why returning values matters, common mistakes such as missing base cases or causing stack overflow, helper method recursion, pure recursion, and how to think about time and space complexity for recursive solutions. The practice section includes recursive challenges such as `power` and `productOfArray`.

## Problems

### Recursion Examples

Files:
- `Problems/recursion/callstack_example.js`
- `Problems/recursion/collect_odds_pure_recursion.js`
- `Problems/recursion/factorial_iterative.js`
- `Problems/recursion/factorial_recursive.js`

The call stack example shows how JavaScript functions call other functions and how those calls are handled in order. The `wakeUp` function calls smaller steps like `takeShower`, `eatBreakfast`, and `cookFood`, which makes it useful for understanding how function calls are placed on and removed from the call stack.

The collect odds example uses pure recursion to return all odd values from an array. It checks the first value, adds it to a new array if it is odd, then recursively calls itself with the rest of the array until the base case is reached.

The factorial examples compare the iterative and recursive ways to multiply every number from the input down to `1`. The iterative version uses a loop and a running total, while the recursive version uses a base case and smaller repeated calls.

To run the examples, install Node.js and execute:

```bash
node "Problems/recursion/callstack_example.js"
node "Problems/recursion/collect_odds_pure_recursion.js"
node "Problems/recursion/factorial_iterative.js"
node "Problems/recursion/factorial_recursive.js"
```

### Frequency Counter - Same

Files:
- `Problems/Frequency Counter/same_naive_solution.js`
- `Problems/Frequency Counter/same_refactored_solution.js`
- `Problems/anagram.js`

This problem checks whether every value in the first array has its squared value in the second array with the same frequency. For example, `[1, 2, 3, 2]` and `[9, 1, 4, 4]` should return `true` because `1^2 = 1`, `2^2 = 4` appears twice, and `3^2 = 9`.

The naive solution uses `indexOf` inside a loop and removes matched values with `splice`. It is useful for understanding the problem step by step, but it is slower because searching inside the second array happens repeatedly. This approach has roughly `O(n^2)` time complexity.

The refactored solution uses the frequency counter pattern. It builds objects that count how many times each value appears in both arrays, then compares the counts. This is the better approach when you need to compare two collections by value frequency, such as checking squared values, anagrams, duplicates, or matching grouped data. This approach has `O(n)` time complexity because each array is looped through only a small fixed number of times.

The anagram example uses the same frequency counter idea with strings. It counts the characters in the first word, then subtracts those counts while reading the second word. If a needed character is missing or has already been used up, the strings are not valid anagrams.

Use the frequency counter pattern when:
- You need to compare two arrays, strings, or collections.
- The order of values does not matter.
- The number of times each value appears does matter.
- A nested loop solution is becoming too slow.

To run the examples, install Node.js and execute:

```bash
node "Problems/Frequency Counter/same_naive_solution.js"
node "Problems/Frequency Counter/same_refactored_solution.js"
node "Problems/anagram.js"
```

### Multiple Pointers - Sum Zero

Files:
- `Problems/Two Pointer/sum_zero_naive.js`
- `Problems/Two Pointer/sum_zero_refactored.js`

This problem takes a sorted array of integers and returns the first pair where the two numbers add up to zero. For example, in `[-4, -3, -2, -1, 0, 1, 2, 5]`, the pair `[-2, 2]` adds to zero.

The naive solution uses two nested loops to compare every possible pair. This is easy to understand, but it becomes slower as the array grows because each value may be compared with many other values. This approach has `O(n^2)` time complexity.

The refactored solution uses the multiple pointers pattern. It starts one pointer at the beginning of the sorted array and one at the end, then moves the pointers inward based on whether the current sum is too high or too low. This reduces the time complexity to `O(n)` because each pointer moves through the array at most once.

Use the multiple pointers pattern when:
- The input is sorted or can be sorted safely.
- You need to find a pair or group of values that meet a condition.
- A nested loop solution is comparing too many combinations.

To run the examples, install Node.js and execute:

```bash
node "Problems/Two Pointer/sum_zero_naive.js"
node "Problems/Two Pointer/sum_zero_refactored.js"
```

### Multiple Pointers - Unique Values

File:
- `Problems/unique_values.js`

This problem counts how many unique values exist in a sorted array. For example, `[1, 2, 2, 5, 7, 7, 99]` has five unique values: `1`, `2`, `5`, `7`, and `99`.

The solution uses the multiple pointers pattern. One pointer tracks the position of the last unique value, while the second pointer scans through the rest of the array. When a new value is found, it is moved next to the previous unique value. This solves the problem in `O(n)` time and uses `O(1)` extra space.

To run the example, install Node.js and execute:

```bash
node "Problems/unique_values.js"
```

### Optional Challenge Problems

File:
- `Problems/OptionalChallange.js`

This file contains extra practice problems using frequency counter and multiple pointers patterns. It includes solutions for problems such as `sameFrequency`, `areThereDuplicates`, `constructNote`, `findAllDuplicates`, `averagePair`, `isSubsequence`, and `findPair`.

These challenges are useful for practicing how to choose an efficient pattern based on the problem constraints. Some solutions compare value frequencies with objects or sets, while others use sorted input and pointer movement to avoid unnecessary nested loops.

To run or test these examples, install Node.js and execute:

```bash
node "Problems/OptionalChallange.js"
```
