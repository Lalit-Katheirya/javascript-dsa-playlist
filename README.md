# 🚀 JavaScript DSA Playlist
## 📚 A complete Data Structures & Algorithms roadmap in JavaScript from Beginner to Advanced with theory, examples, complexity analysis, interview questions, and practice problems.
<p align="center">
  <img src="./asset/banner.png" width="100%" />
</p>


## 📚 What You'll Learn in This Repository

<div align="center">

| | Feature | Description |
|--|---------|-------------|
| 📖 | **Simple Definitions** | Easy-to-understand explanations for every concept |
| 🧠 | **Beginner to Advanced** | Fundamental concepts built step by step |
| 💻 | **JS Implementations** | Clean JavaScript ES6+ code for every topic |
| ⚡ | **Complexity Analysis** | Time & Space Big-O breakdown per operation |
| 🔍 | **Dry Run Explanations** | Step-by-step trace-through for key algorithms |
| 🎯 | **Interview Q&A** | Common questions with clear answers per topic |
| 📝 | **Practice Problems** | Topic-wise problems with hints and solutions |
| 🚀 | **Platform Patterns** | LeetCode, HackerRank & competitive coding patterns |
| 🔄 | **Multiple Approaches** | Brute Force → Optimized solutions side by side |
| 🌳 | **Visualizations** | ASCII visualizations & real-world use cases |
| 📊 | **Algorithm Design** | Greedy, Divide & Conquer, DP design techniques |
| 🎓 | **Interview Roadmap** | 12-week structured preparation guide |
| ✅ | **Progress Checklists** | Topic-wise completion tracking |
| 🔗 | **Topic Navigation** | Cross-linked topics for connected learning |
| 🏆 | **Real-World DSA** | How each structure is used in production systems |

</div>


# 🚀 JavaScript DSA — Complete Interview Mastery Guide

[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![DSA](https://img.shields.io/badge/DSA-Interview%20Ready-0A66C2?style=for-the-badge&logo=leetcode&logoColor=white)](https://leetcode.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Stars](https://img.shields.io/github/stars/lalitkatheirya/js-dsa?style=for-the-badge)](https://github.com)

> ⭐ A complete, production-quality reference for **Data Structures & Algorithms in JavaScript** — with definitions, real JS code, Big-O analysis, and interview Q&A, all in one file.

> Click ⭐ if this helps you and share with fellow developers!

---

### 👨‍💻 Author: **Lalit Katheirya**
*Full Stack Developer · Angular · React · Node.js · MongoDB*

</div>

---

## 📚 Table of Contents

| # | Topic | Difficulty |
|---|-------|-----------|
| 1 | [Arrays](#1-arrays) | 🟢 Beginner |
| 2 | [Strings](#2-strings) | 🟢 Beginner |
| 3 | [Hash Maps & Objects](#3-hash-maps--objects) | 🟢 Beginner |
| 4 | [Recursion](#4-recursion) | 🟡 Intermediate |
| 5 | [Searching Algorithms](#5-searching-algorithms) | 🟢 Beginner |
| 6 | [Sorting Algorithms](#6-sorting-algorithms) | 🟡 Intermediate |
| 7 | [Linked Lists](#7-linked-lists) | 🟡 Intermediate |
| 8 | [Stacks](#8-stacks) | 🟡 Intermediate |
| 9 | [Queues](#9-queues) | 🟡 Intermediate |
| 10 | [Trees & Binary Search Trees](#10-trees--binary-search-trees) | 🔴 Advanced |
| 11 | [Heaps](#11-heaps) | 🔴 Advanced |
| 12 | [Graphs](#12-graphs) | 🔴 Advanced |
| 13 | [Dynamic Programming](#13-dynamic-programming) | 🔴 Advanced |
| 14 | [Sliding Window Pattern](#14-sliding-window-pattern) | 🟡 Intermediate |
| 15 | [Two Pointers Pattern](#15-two-pointers-pattern) | 🟡 Intermediate |
| 16 | [Prefix Sum](#16-prefix-sum) | 🟡 Intermediate |
| 17 | [Backtracking](#17-backtracking) | 🔴 Advanced |
| 18 | [Bit Manipulation](#18-bit-manipulation) | 🔴 Advanced |
| 19 | [Big-O Cheat Sheet](#19-big-o-cheat-sheet) | — |
| 20 | [Top Interview Questions](#20-top-interview-questions) | — |

---

## 1. Arrays

### 📖 Definition
An **Array** is a linear data structure that stores elements in contiguous memory locations. Each element is accessible via a zero-based index in O(1) time. Arrays in JavaScript are dynamic and can hold mixed types.

### ⚙️ Complexity

| Operation | Time | Space |
|-----------|------|-------|
| Access | O(1) | O(1) |
| Search | O(n) | O(1) |
| Insert (end) | O(1) amortized | O(1) |
| Insert (middle) | O(n) | O(1) |
| Delete | O(n) | O(1) |

### 💻 Code Examples

**Basic Operations**
```javascript
// Declaration
const arr = [10, 20, 30, 40, 50];

// Access — O(1)
console.log(arr[2]); // 30

// Insert at end — O(1)
arr.push(60);

// Insert at beginning — O(n)
arr.unshift(0);

// Delete last — O(1)
arr.pop();

// Delete first — O(n)
arr.shift();

// Search — O(n)
const idx = arr.indexOf(30); // 2
```

**Array Rotation**
```javascript
// Rotate array left by k positions
function rotateLeft(arr, k) {
  k = k % arr.length;
  return [...arr.slice(k), ...arr.slice(0, k)];
}

// Rotate array right by k positions
function rotateRight(arr, k) {
  k = k % arr.length;
  return [...arr.slice(arr.length - k), ...arr.slice(0, arr.length - k)];
}

console.log(rotateLeft([1, 2, 3, 4, 5], 2));  // [3, 4, 5, 1, 2]
console.log(rotateRight([1, 2, 3, 4, 5], 2)); // [4, 5, 1, 2, 3]
```

**Kadane's Algorithm — Maximum Subarray Sum**
```javascript
// Find contiguous subarray with maximum sum — O(n)
function maxSubarraySum(arr) {
  let maxSoFar = arr[0];
  let maxEndingHere = arr[0];

  for (let i = 1; i < arr.length; i++) {
    maxEndingHere = Math.max(arr[i], maxEndingHere + arr[i]);
    maxSoFar = Math.max(maxSoFar, maxEndingHere);
  }

  return maxSoFar;
}

console.log(maxSubarraySum([-2, 1, -3, 4, -1, 2, 1, -5, 4])); // 6
```

### ❓ Interview Questions
1. Find the duplicate number in an array of 1 to n.
2. Move all zeros to the end without changing order of non-zero elements.
3. Find the intersection of two arrays.
4. Merge two sorted arrays without extra space.

---

## 2. Strings

### 📖 Definition
A **String** is a sequence of characters. In JavaScript, strings are **immutable** — every operation returns a new string. They are internally stored as UTF-16 encoded character sequences.

### ⚙️ Complexity

| Operation | Time | Space |
|-----------|------|-------|
| Access char | O(1) | O(1) |
| Search substring | O(n·m) | O(1) |
| Concatenation | O(n) | O(n) |
| Slice | O(k) | O(k) |

### 💻 Code Examples

**Reverse a String**
```javascript
function reverseString(str) {
  return str.split('').reverse().join('');
}

// Manual approach
function reverseStringManual(str) {
  let result = '';
  for (let i = str.length - 1; i >= 0; i--) {
    result += str[i];
  }
  return result;
}

console.log(reverseString('hello')); // "olleh"
```

**Check Palindrome**
```javascript
function isPalindrome(str) {
  // Normalize: lowercase, remove non-alphanumeric
  const clean = str.toLowerCase().replace(/[^a-z0-9]/g, '');
  let left = 0, right = clean.length - 1;

  while (left < right) {
    if (clean[left] !== clean[right]) return false;
    left++;
    right--;
  }
  return true;
}

console.log(isPalindrome("A man, a plan, a canal: Panama")); // true
console.log(isPalindrome("race a car")); // false
```

**Check Anagram**
```javascript
function isAnagram(s, t) {
  if (s.length !== t.length) return false;

  const freq = {};
  for (const char of s) freq[char] = (freq[char] || 0) + 1;
  for (const char of t) {
    if (!freq[char]) return false;
    freq[char]--;
  }
  return true;
}

console.log(isAnagram("anagram", "nagaram")); // true
console.log(isAnagram("rat", "car"));         // false
```

**Longest Substring Without Repeating Characters**
```javascript
function lengthOfLongestSubstring(s) {
  const map = new Map();
  let max = 0, left = 0;

  for (let right = 0; right < s.length; right++) {
    if (map.has(s[right])) {
      left = Math.max(left, map.get(s[right]) + 1);
    }
    map.set(s[right], right);
    max = Math.max(max, right - left + 1);
  }

  return max;
}

console.log(lengthOfLongestSubstring("abcabcbb")); // 3
```

### ❓ Interview Questions
1. Find the first non-repeating character in a string.
2. Count and say problem.
3. Longest common prefix among an array of strings.
4. Check if two strings are rotations of each other.

---

## 3. Hash Maps & Objects

### 📖 Definition
A **Hash Map** (or Hash Table) is a data structure that maps **keys to values** using a hash function. It provides average O(1) time for insertion, deletion, and lookup. JavaScript's `Map` and plain `Object` serve as hash maps.

### ⚙️ Complexity

| Operation | Average | Worst |
|-----------|---------|-------|
| Insert | O(1) | O(n) |
| Delete | O(1) | O(n) |
| Search | O(1) | O(n) |
| Space | O(n) | O(n) |

### 💻 Code Examples

**Frequency Counter Pattern**
```javascript
// Count character frequency
function charFrequency(str) {
  const freq = new Map();
  for (const char of str) {
    freq.set(char, (freq.get(char) || 0) + 1);
  }
  return freq;
}

console.log(charFrequency("mississippi"));
// Map { 'm' => 1, 'i' => 4, 's' => 4, 'p' => 2 }
```

**Two Sum — Classic Hash Map Problem**
```javascript
// Find two indices that add up to target — O(n)
function twoSum(nums, target) {
  const map = new Map(); // value -> index

  for (let i = 0; i < nums.length; i++) {
    const complement = target - nums[i];
    if (map.has(complement)) {
      return [map.get(complement), i];
    }
    map.set(nums[i], i);
  }

  return [];
}

console.log(twoSum([2, 7, 11, 15], 9)); // [0, 1]
console.log(twoSum([3, 2, 4], 6));      // [1, 2]
```

**Group Anagrams**
```javascript
function groupAnagrams(strs) {
  const map = new Map();

  for (const str of strs) {
    const key = str.split('').sort().join('');
    if (!map.has(key)) map.set(key, []);
    map.get(key).push(str);
  }

  return [...map.values()];
}

console.log(groupAnagrams(["eat","tea","tan","ate","nat","bat"]));
// [["eat","tea","ate"],["tan","nat"],["bat"]]
```

### ❓ Interview Questions
1. Find the first recurring character in an array.
2. Implement a LRU Cache using Map.
3. Find all pairs in an array with a given sum.
4. Longest consecutive sequence in an array.

---

## 4. Recursion

### 📖 Definition
**Recursion** is a technique where a function **calls itself** with a smaller input until it reaches a **base case**. Every recursive solution has: (1) a base case to stop recursion, and (2) a recursive case that reduces the problem.

### ⚙️ Complexity
Depends on the problem. Typically O(n) time and O(n) space (call stack).

### 💻 Code Examples

**Factorial**
```javascript
function factorial(n) {
  if (n <= 1) return 1;           // Base case
  return n * factorial(n - 1);   // Recursive case
}

console.log(factorial(5)); // 120
```

**Fibonacci**
```javascript
// Naive recursion — O(2^n)
function fib(n) {
  if (n <= 1) return n;
  return fib(n - 1) + fib(n - 2);
}

// Memoized — O(n)
function fibMemo(n, memo = {}) {
  if (n in memo) return memo[n];
  if (n <= 1) return n;
  memo[n] = fibMemo(n - 1, memo) + fibMemo(n - 2, memo);
  return memo[n];
}

console.log(fibMemo(40)); // 102334155
```

**Flatten Nested Array**
```javascript
function flattenArray(arr) {
  const result = [];
  for (const item of arr) {
    if (Array.isArray(item)) {
      result.push(...flattenArray(item));
    } else {
      result.push(item);
    }
  }
  return result;
}

console.log(flattenArray([1, [2, [3, [4]], 5]])); // [1, 2, 3, 4, 5]
```

**Power Function**
```javascript
// x^n using fast exponentiation — O(log n)
function myPow(x, n) {
  if (n === 0) return 1;
  if (n < 0) return 1 / myPow(x, -n);

  if (n % 2 === 0) {
    const half = myPow(x, n / 2);
    return half * half;
  }
  return x * myPow(x, n - 1);
}

console.log(myPow(2, 10)); // 1024
```

### ❓ Interview Questions
1. Write a recursive function to compute the sum of digits of a number.
2. Solve the Tower of Hanoi problem.
3. Generate all permutations of a string using recursion.
4. Recursive binary search implementation.

---

## 5. Searching Algorithms

### 📖 Definition
**Searching** is the process of finding an element within a data structure. The two fundamental algorithms are **Linear Search** (works on unsorted data) and **Binary Search** (requires sorted data and is significantly faster).

### ⚙️ Complexity

| Algorithm | Best | Average | Worst | Space |
|-----------|------|---------|-------|-------|
| Linear Search | O(1) | O(n) | O(n) | O(1) |
| Binary Search | O(1) | O(log n) | O(log n) | O(1) |

### 💻 Code Examples

**Linear Search**
```javascript
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) return i;
  }
  return -1;
}

console.log(linearSearch([5, 3, 8, 1, 9], 8)); // 2
```

**Binary Search (Iterative)**
```javascript
function binarySearch(arr, target) {
  let left = 0, right = arr.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);

    if (arr[mid] === target) return mid;
    else if (arr[mid] < target) left = mid + 1;
    else right = mid - 1;
  }

  return -1;
}

console.log(binarySearch([1, 3, 5, 7, 9, 11, 13], 7)); // 3
```

**Binary Search (Recursive)**
```javascript
function binarySearchRecursive(arr, target, left = 0, right = arr.length - 1) {
  if (left > right) return -1;

  const mid = Math.floor((left + right) / 2);

  if (arr[mid] === target) return mid;
  if (arr[mid] < target) return binarySearchRecursive(arr, target, mid + 1, right);
  return binarySearchRecursive(arr, target, left, mid - 1);
}

console.log(binarySearchRecursive([1, 3, 5, 7, 9, 11], 9)); // 4
```

**Search in Rotated Sorted Array**
```javascript
function searchRotated(nums, target) {
  let left = 0, right = nums.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (nums[mid] === target) return mid;

    // Left half is sorted
    if (nums[left] <= nums[mid]) {
      if (nums[left] <= target && target < nums[mid]) right = mid - 1;
      else left = mid + 1;
    } else {
      // Right half is sorted
      if (nums[mid] < target && target <= nums[right]) left = mid + 1;
      else right = mid - 1;
    }
  }
  return -1;
}

console.log(searchRotated([4, 5, 6, 7, 0, 1, 2], 0)); // 4
```

### ❓ Interview Questions
1. Find the first and last position of an element in a sorted array.
2. Search a 2D matrix using binary search.
3. Find the minimum in a rotated sorted array.
4. Find peak element in an array.

---

## 6. Sorting Algorithms

### 📖 Definition
**Sorting** is the process of arranging elements in a defined order (ascending/descending). Different algorithms trade off between time complexity, space complexity, and stability.

### ⚙️ Complexity

| Algorithm | Best | Average | Worst | Space | Stable |
|-----------|------|---------|-------|-------|--------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) | ✅ |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) | ❌ |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) | ✅ |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) | ✅ |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) | ❌ |

### 💻 Code Examples

**Bubble Sort**
```javascript
function bubbleSort(arr) {
  const n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    let swapped = false;
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]; // ES6 swap
        swapped = true;
      }
    }
    if (!swapped) break; // Optimization: already sorted
  }
  return arr;
}

console.log(bubbleSort([64, 34, 25, 12, 22, 11, 90]));
// [11, 12, 22, 25, 34, 64, 90]
```

**Insertion Sort**
```javascript
function insertionSort(arr) {
  for (let i = 1; i < arr.length; i++) {
    const key = arr[i];
    let j = i - 1;

    while (j >= 0 && arr[j] > key) {
      arr[j + 1] = arr[j];
      j--;
    }
    arr[j + 1] = key;
  }
  return arr;
}

console.log(insertionSort([12, 11, 13, 5, 6]));
// [5, 6, 11, 12, 13]
```

**Merge Sort**
```javascript
function mergeSort(arr) {
  if (arr.length <= 1) return arr;

  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));
  const right = mergeSort(arr.slice(mid));

  return merge(left, right);
}

function merge(left, right) {
  const result = [];
  let i = 0, j = 0;

  while (i < left.length && j < right.length) {
    if (left[i] <= right[j]) result.push(left[i++]);
    else result.push(right[j++]);
  }

  return [...result, ...left.slice(i), ...right.slice(j)];
}

console.log(mergeSort([38, 27, 43, 3, 9, 82, 10]));
// [3, 9, 10, 27, 38, 43, 82]
```

**Quick Sort**
```javascript
function quickSort(arr, low = 0, high = arr.length - 1) {
  if (low < high) {
    const pivotIdx = partition(arr, low, high);
    quickSort(arr, low, pivotIdx - 1);
    quickSort(arr, pivotIdx + 1, high);
  }
  return arr;
}

function partition(arr, low, high) {
  const pivot = arr[high];
  let i = low - 1;

  for (let j = low; j < high; j++) {
    if (arr[j] <= pivot) {
      i++;
      [arr[i], arr[j]] = [arr[j], arr[i]];
    }
  }
  [arr[i + 1], arr[high]] = [arr[high], arr[i + 1]];
  return i + 1;
}

console.log(quickSort([10, 80, 30, 90, 40, 50, 70]));
// [10, 30, 40, 50, 70, 80, 90]
```

### ❓ Interview Questions
1. Sort an array of 0s, 1s, and 2s (Dutch National Flag problem).
2. Find the kth largest element without full sort.
3. Sort a linked list using merge sort.
4. Count inversions in an array.

---

## 7. Linked Lists

### 📖 Definition
A **Linked List** is a linear data structure where elements (**nodes**) are stored in non-contiguous memory. Each node contains **data** and a **pointer** to the next node. Unlike arrays, linked lists allow O(1) insertion/deletion at known positions without shifting elements.

### ⚙️ Complexity

| Operation | Singly LL | Doubly LL |
|-----------|-----------|-----------|
| Access | O(n) | O(n) |
| Search | O(n) | O(n) |
| Insert (head) | O(1) | O(1) |
| Insert (tail) | O(n) / O(1)* | O(1) |
| Delete (head) | O(1) | O(1) |
| Delete (known node) | O(n) | O(1) |

*O(1) with tail pointer

### 💻 Code Examples

**Singly Linked List Implementation**
```javascript
class ListNode {
  constructor(val) {
    this.val = val;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
    this.size = 0;
  }

  // Insert at beginning — O(1)
  prepend(val) {
    const node = new ListNode(val);
    node.next = this.head;
    this.head = node;
    this.size++;
  }

  // Insert at end — O(n)
  append(val) {
    const node = new ListNode(val);
    if (!this.head) { this.head = node; this.size++; return; }

    let curr = this.head;
    while (curr.next) curr = curr.next;
    curr.next = node;
    this.size++;
  }

  // Delete by value — O(n)
  delete(val) {
    if (!this.head) return;
    if (this.head.val === val) { this.head = this.head.next; this.size--; return; }

    let curr = this.head;
    while (curr.next && curr.next.val !== val) curr = curr.next;
    if (curr.next) { curr.next = curr.next.next; this.size--; }
  }

  // Print list
  print() {
    const vals = [];
    let curr = this.head;
    while (curr) { vals.push(curr.val); curr = curr.next; }
    console.log(vals.join(' -> '));
  }
}

const ll = new LinkedList();
ll.append(1); ll.append(2); ll.append(3);
ll.prepend(0);
ll.print(); // 0 -> 1 -> 2 -> 3
ll.delete(2);
ll.print(); // 0 -> 1 -> 3
```

**Reverse a Linked List**
```javascript
function reverseList(head) {
  let prev = null, curr = head;

  while (curr) {
    const next = curr.next;
    curr.next = prev;
    prev = curr;
    curr = next;
  }

  return prev; // New head
}
```

**Detect Cycle (Floyd's Algorithm)**
```javascript
function hasCycle(head) {
  let slow = head, fast = head;

  while (fast && fast.next) {
    slow = slow.next;
    fast = fast.next.next;
    if (slow === fast) return true;
  }
  return false;
}
```

**Find Middle Node**
```javascript
function middleNode(head) {
  let slow = head, fast = head;

  while (fast && fast.next) {
    slow = slow.next;
    fast = fast.next.next;
  }
  return slow; // Slow is at middle
}
```

### ❓ Interview Questions
1. Merge two sorted linked lists.
2. Find the nth node from the end.
3. Check if a linked list is a palindrome.
4. Detect the start of the cycle in a linked list.

---

## 8. Stacks

### 📖 Definition
A **Stack** is a linear data structure that follows the **LIFO** (Last In, First Out) principle. Think of a stack of plates — you can only add/remove from the top. Used for: function call stacks, undo operations, expression evaluation, DFS traversal.

### ⚙️ Complexity

| Operation | Time | Space |
|-----------|------|-------|
| Push | O(1) | O(1) |
| Pop | O(1) | O(1) |
| Peek/Top | O(1) | O(1) |
| Search | O(n) | O(1) |

### 💻 Code Examples

**Stack Implementation**
```javascript
class Stack {
  constructor() {
    this.items = [];
  }

  push(element) { this.items.push(element); }
  pop() { return this.items.length ? this.items.pop() : "Underflow"; }
  peek() { return this.items[this.items.length - 1]; }
  isEmpty() { return this.items.length === 0; }
  size() { return this.items.length; }
  print() { console.log(this.items.toString()); }
}

const stack = new Stack();
stack.push(10); stack.push(20); stack.push(30);
console.log(stack.peek()); // 30
console.log(stack.pop());  // 30
stack.print();             // 10,20
```

**Valid Parentheses**
```javascript
function isValid(s) {
  const stack = [];
  const map = { ')': '(', '}': '{', ']': '[' };

  for (const char of s) {
    if ('({['.includes(char)) {
      stack.push(char);
    } else {
      if (stack.pop() !== map[char]) return false;
    }
  }

  return stack.length === 0;
}

console.log(isValid("()[]{}")); // true
console.log(isValid("(]"));     // false
console.log(isValid("{[]}"));   // true
```

**Monotonic Stack — Next Greater Element**
```javascript
function nextGreaterElement(nums) {
  const result = new Array(nums.length).fill(-1);
  const stack = []; // Store indices

  for (let i = 0; i < nums.length; i++) {
    while (stack.length && nums[stack[stack.length - 1]] < nums[i]) {
      result[stack.pop()] = nums[i];
    }
    stack.push(i);
  }

  return result;
}

console.log(nextGreaterElement([2, 1, 2, 4, 3]));
// [4, 2, 4, -1, -1]
```

### ❓ Interview Questions
1. Implement a stack that supports getMin() in O(1).
2. Evaluate a Reverse Polish Notation expression.
3. Daily temperatures — find the next warmer day for each day.
4. Largest rectangle in a histogram.

---

## 9. Queues

### 📖 Definition
A **Queue** is a linear data structure following **FIFO** (First In, First Out) principle. Elements are added at the **rear** (enqueue) and removed from the **front** (dequeue). Used in: BFS, task scheduling, print spooling, and CPU scheduling.

### ⚙️ Complexity

| Operation | Time | Space |
|-----------|------|-------|
| Enqueue | O(1) | O(1) |
| Dequeue | O(1) | O(1) |
| Peek | O(1) | O(1) |
| Search | O(n) | O(1) |

### 💻 Code Examples

**Queue Implementation**
```javascript
class Queue {
  constructor() {
    this.items = {};
    this.front = 0;
    this.rear = 0;
  }

  enqueue(element) { this.items[this.rear++] = element; }
  dequeue() {
    if (this.isEmpty()) return "Underflow";
    const item = this.items[this.front];
    delete this.items[this.front++];
    return item;
  }
  peek() { return this.items[this.front]; }
  isEmpty() { return this.front === this.rear; }
  size() { return this.rear - this.front; }
}

const q = new Queue();
q.enqueue(1); q.enqueue(2); q.enqueue(3);
console.log(q.dequeue()); // 1
console.log(q.peek());    // 2
```

**Circular Queue**
```javascript
class CircularQueue {
  constructor(k) {
    this.data = new Array(k);
    this.head = -1;
    this.tail = -1;
    this.size = k;
  }

  enQueue(val) {
    if (this.isFull()) return false;
    if (this.isEmpty()) this.head = 0;
    this.tail = (this.tail + 1) % this.size;
    this.data[this.tail] = val;
    return true;
  }

  deQueue() {
    if (this.isEmpty()) return false;
    if (this.head === this.tail) { this.head = -1; this.tail = -1; return true; }
    this.head = (this.head + 1) % this.size;
    return true;
  }

  Front() { return this.isEmpty() ? -1 : this.data[this.head]; }
  Rear() { return this.isEmpty() ? -1 : this.data[this.tail]; }
  isEmpty() { return this.head === -1; }
  isFull() { return (this.tail + 1) % this.size === this.head; }
}
```

**BFS using Queue**
```javascript
function bfs(graph, start) {
  const visited = new Set();
  const queue = [start];
  const result = [];

  visited.add(start);

  while (queue.length) {
    const node = queue.shift();
    result.push(node);

    for (const neighbor of graph[node] || []) {
      if (!visited.has(neighbor)) {
        visited.add(neighbor);
        queue.push(neighbor);
      }
    }
  }
  return result;
}
```

### ❓ Interview Questions
1. Implement a queue using two stacks.
2. Sliding window maximum using a deque.
3. Generate binary numbers from 1 to n using a queue.
4. First non-repeating character in a stream.

---

## 10. Trees & Binary Search Trees

### 📖 Definition
A **Tree** is a hierarchical data structure with a root node and subtrees of children. A **Binary Tree** has at most two children (left, right). A **Binary Search Tree (BST)** maintains the invariant: `left < node < right`, enabling efficient O(log n) search.

### ⚙️ Complexity

| Operation | BST (Avg) | BST (Worst) |
|-----------|-----------|-------------|
| Search | O(log n) | O(n) |
| Insert | O(log n) | O(n) |
| Delete | O(log n) | O(n) |
| Traversal | O(n) | O(n) |

### 💻 Code Examples

**BST Implementation**
```javascript
class TreeNode {
  constructor(val) {
    this.val = val;
    this.left = null;
    this.right = null;
  }
}

class BST {
  constructor() { this.root = null; }

  insert(val) { this.root = this._insert(this.root, val); }

  _insert(node, val) {
    if (!node) return new TreeNode(val);
    if (val < node.val) node.left = this._insert(node.left, val);
    else if (val > node.val) node.right = this._insert(node.right, val);
    return node;
  }

  search(val) { return this._search(this.root, val); }

  _search(node, val) {
    if (!node || node.val === val) return node;
    if (val < node.val) return this._search(node.left, val);
    return this._search(node.right, val);
  }
}
```

**Tree Traversals**
```javascript
// Inorder (Left → Root → Right) — gives sorted order for BST
function inorder(root, result = []) {
  if (!root) return result;
  inorder(root.left, result);
  result.push(root.val);
  inorder(root.right, result);
  return result;
}

// Preorder (Root → Left → Right)
function preorder(root, result = []) {
  if (!root) return result;
  result.push(root.val);
  preorder(root.left, result);
  preorder(root.right, result);
  return result;
}

// Postorder (Left → Right → Root)
function postorder(root, result = []) {
  if (!root) return result;
  postorder(root.left, result);
  postorder(root.right, result);
  result.push(root.val);
  return result;
}

// Level Order (BFS)
function levelOrder(root) {
  if (!root) return [];
  const result = [], queue = [root];

  while (queue.length) {
    const level = [];
    const len = queue.length;
    for (let i = 0; i < len; i++) {
      const node = queue.shift();
      level.push(node.val);
      if (node.left) queue.push(node.left);
      if (node.right) queue.push(node.right);
    }
    result.push(level);
  }
  return result;
}
```

**Maximum Depth of Binary Tree**
```javascript
function maxDepth(root) {
  if (!root) return 0;
  return 1 + Math.max(maxDepth(root.left), maxDepth(root.right));
}
```

**Validate BST**
```javascript
function isValidBST(root, min = -Infinity, max = Infinity) {
  if (!root) return true;
  if (root.val <= min || root.val >= max) return false;
  return isValidBST(root.left, min, root.val) &&
         isValidBST(root.right, root.val, max);
}
```

### ❓ Interview Questions
1. Find the lowest common ancestor of two nodes.
2. Check if two trees are identical.
3. Convert a sorted array to a balanced BST.
4. Serialize and deserialize a binary tree.

---

## 11. Heaps

### 📖 Definition
A **Heap** is a complete binary tree satisfying the **heap property**. In a **Max-Heap**, each parent ≥ its children. In a **Min-Heap**, each parent ≤ its children. Heaps are stored as arrays and are used in priority queues and heap sort.

### ⚙️ Complexity

| Operation | Time |
|-----------|------|
| Insert | O(log n) |
| Delete Max/Min | O(log n) |
| Peek Max/Min | O(1) |
| Heapify | O(n) |
| Heap Sort | O(n log n) |

### 💻 Code Examples

**Min-Heap Implementation**
```javascript
class MinHeap {
  constructor() { this.heap = []; }

  insert(val) {
    this.heap.push(val);
    this._bubbleUp(this.heap.length - 1);
  }

  extractMin() {
    if (this.heap.length === 1) return this.heap.pop();
    const min = this.heap[0];
    this.heap[0] = this.heap.pop();
    this._sinkDown(0);
    return min;
  }

  _bubbleUp(i) {
    while (i > 0) {
      const parent = Math.floor((i - 1) / 2);
      if (this.heap[parent] <= this.heap[i]) break;
      [this.heap[parent], this.heap[i]] = [this.heap[i], this.heap[parent]];
      i = parent;
    }
  }

  _sinkDown(i) {
    const n = this.heap.length;
    while (true) {
      let smallest = i;
      const left = 2 * i + 1, right = 2 * i + 2;

      if (left < n && this.heap[left] < this.heap[smallest]) smallest = left;
      if (right < n && this.heap[right] < this.heap[smallest]) smallest = right;
      if (smallest === i) break;

      [this.heap[i], this.heap[smallest]] = [this.heap[smallest], this.heap[i]];
      i = smallest;
    }
  }

  peek() { return this.heap[0]; }
  size() { return this.heap.length; }
}

const heap = new MinHeap();
[5, 3, 8, 1, 2].forEach(v => heap.insert(v));
console.log(heap.extractMin()); // 1
console.log(heap.extractMin()); // 2
```

**Find K Largest Elements**
```javascript
function findKLargest(nums, k) {
  const minHeap = new MinHeap();

  for (const num of nums) {
    minHeap.insert(num);
    if (minHeap.size() > k) minHeap.extractMin();
  }

  return minHeap.heap;
}

console.log(findKLargest([3, 2, 1, 5, 6, 4], 2)); // [5, 6]
```

### ❓ Interview Questions
1. Find the median from a data stream.
2. Merge K sorted lists using a heap.
3. Task scheduler problem.
4. K closest points to origin.

---

## 12. Graphs

### 📖 Definition
A **Graph** is a non-linear data structure consisting of **vertices (nodes)** and **edges (connections)**. Graphs can be **directed** or **undirected**, **weighted** or **unweighted**, and **cyclic** or **acyclic**.

### ⚙️ Complexity

| Representation | Space | Add Edge | Has Edge |
|----------------|-------|----------|----------|
| Adjacency Matrix | O(V²) | O(1) | O(1) |
| Adjacency List | O(V+E) | O(1) | O(V) |

### 💻 Code Examples

**Graph Implementation (Adjacency List)**
```javascript
class Graph {
  constructor(directed = false) {
    this.adjacencyList = new Map();
    this.directed = directed;
  }

  addVertex(vertex) {
    if (!this.adjacencyList.has(vertex))
      this.adjacencyList.set(vertex, []);
  }

  addEdge(v1, v2, weight = 1) {
    this.addVertex(v1); this.addVertex(v2);
    this.adjacencyList.get(v1).push({ node: v2, weight });
    if (!this.directed)
      this.adjacencyList.get(v2).push({ node: v1, weight });
  }

  getNeighbors(vertex) { return this.adjacencyList.get(vertex) || []; }
}
```

**DFS — Depth First Search**
```javascript
function dfs(graph, start, visited = new Set()) {
  visited.add(start);
  console.log(start);

  for (const { node } of graph.getNeighbors(start)) {
    if (!visited.has(node)) {
      dfs(graph, node, visited);
    }
  }
}
```

**BFS — Breadth First Search**
```javascript
function bfsGraph(graph, start) {
  const visited = new Set([start]);
  const queue = [start];
  const result = [];

  while (queue.length) {
    const vertex = queue.shift();
    result.push(vertex);

    for (const { node } of graph.getNeighbors(vertex)) {
      if (!visited.has(node)) {
        visited.add(node);
        queue.push(node);
      }
    }
  }
  return result;
}
```

**Dijkstra's Shortest Path**
```javascript
function dijkstra(graph, start) {
  const dist = {};
  const visited = new Set();

  for (const vertex of graph.adjacencyList.keys()) dist[vertex] = Infinity;
  dist[start] = 0;

  while (true) {
    // Pick unvisited vertex with smallest distance
    let curr = null;
    for (const v of graph.adjacencyList.keys()) {
      if (!visited.has(v) && (curr === null || dist[v] < dist[curr]))
        curr = v;
    }

    if (curr === null || dist[curr] === Infinity) break;
    visited.add(curr);

    for (const { node, weight } of graph.getNeighbors(curr)) {
      const newDist = dist[curr] + weight;
      if (newDist < dist[node]) dist[node] = newDist;
    }
  }

  return dist;
}
```

**Detect Cycle in Directed Graph**
```javascript
function hasCycleDirected(graph) {
  const visited = new Set();
  const recStack = new Set();

  function dfsCycle(node) {
    visited.add(node);
    recStack.add(node);

    for (const { node: neighbor } of graph.getNeighbors(node)) {
      if (!visited.has(neighbor) && dfsCycle(neighbor)) return true;
      if (recStack.has(neighbor)) return true;
    }

    recStack.delete(node);
    return false;
  }

  for (const vertex of graph.adjacencyList.keys()) {
    if (!visited.has(vertex) && dfsCycle(vertex)) return true;
  }
  return false;
}
```

### ❓ Interview Questions
1. Number of islands problem.
2. Course schedule — detect if it's possible to finish all courses (cycle detection).
3. Clone a graph.
4. Find all paths from source to target.

---

## 13. Dynamic Programming

### 📖 Definition
**Dynamic Programming (DP)** is an optimization technique that solves complex problems by breaking them into **overlapping subproblems** and storing their results (**memoization/tabulation**) to avoid redundant computation. Key requirement: **Optimal Substructure** + **Overlapping Subproblems**.

### 💻 Code Examples

**Fibonacci — Tabulation (Bottom-Up)**
```javascript
function fibDP(n) {
  if (n <= 1) return n;
  const dp = [0, 1];
  for (let i = 2; i <= n; i++) dp[i] = dp[i - 1] + dp[i - 2];
  return dp[n];
}

console.log(fibDP(10)); // 55
```

**0/1 Knapsack Problem**
```javascript
function knapsack(weights, values, capacity) {
  const n = weights.length;
  const dp = Array.from({ length: n + 1 }, () => new Array(capacity + 1).fill(0));

  for (let i = 1; i <= n; i++) {
    for (let w = 0; w <= capacity; w++) {
      // Don't take item i
      dp[i][w] = dp[i - 1][w];
      // Take item i (if it fits)
      if (weights[i - 1] <= w) {
        dp[i][w] = Math.max(dp[i][w], dp[i - 1][w - weights[i - 1]] + values[i - 1]);
      }
    }
  }
  return dp[n][capacity];
}

console.log(knapsack([1, 3, 4, 5], [1, 4, 5, 7], 7)); // 9
```

**Longest Common Subsequence**
```javascript
function lcs(s1, s2) {
  const m = s1.length, n = s2.length;
  const dp = Array.from({ length: m + 1 }, () => new Array(n + 1).fill(0));

  for (let i = 1; i <= m; i++) {
    for (let j = 1; j <= n; j++) {
      if (s1[i - 1] === s2[j - 1]) dp[i][j] = dp[i - 1][j - 1] + 1;
      else dp[i][j] = Math.max(dp[i - 1][j], dp[i][j - 1]);
    }
  }
  return dp[m][n];
}

console.log(lcs("ABCBDAB", "BDCAB")); // 4 (BCAB or BDAB)
```

**Coin Change — Minimum Coins**
```javascript
function coinChange(coins, amount) {
  const dp = new Array(amount + 1).fill(Infinity);
  dp[0] = 0;

  for (let i = 1; i <= amount; i++) {
    for (const coin of coins) {
      if (coin <= i) dp[i] = Math.min(dp[i], dp[i - coin] + 1);
    }
  }
  return dp[amount] === Infinity ? -1 : dp[amount];
}

console.log(coinChange([1, 5, 6, 9], 11)); // 2 (5+6)
```

**Longest Increasing Subsequence**
```javascript
function lengthOfLIS(nums) {
  const dp = new Array(nums.length).fill(1);

  for (let i = 1; i < nums.length; i++) {
    for (let j = 0; j < i; j++) {
      if (nums[j] < nums[i]) dp[i] = Math.max(dp[i], dp[j] + 1);
    }
  }
  return Math.max(...dp);
}

console.log(lengthOfLIS([10, 9, 2, 5, 3, 7, 101, 18])); // 4
```

### ❓ Interview Questions
1. Climbing stairs (how many ways to reach the top).
2. House robber problem.
3. Edit distance between two strings.
4. Partition equal subset sum.

---

## 14. Sliding Window Pattern

### 📖 Definition
The **Sliding Window** pattern uses a window (subarray/substring) that slides over the data. It's used to reduce nested loops (O(n²)) to O(n) for problems involving **contiguous subarrays or substrings**.

### 💻 Code Examples

**Fixed Size Window — Max Sum of K Elements**
```javascript
function maxSumSubarray(arr, k) {
  let windowSum = arr.slice(0, k).reduce((a, b) => a + b, 0);
  let maxSum = windowSum;

  for (let i = k; i < arr.length; i++) {
    windowSum += arr[i] - arr[i - k]; // Slide the window
    maxSum = Math.max(maxSum, windowSum);
  }
  return maxSum;
}

console.log(maxSumSubarray([2, 1, 5, 1, 3, 2], 3)); // 9
```

**Variable Size Window — Smallest Subarray with Sum ≥ S**
```javascript
function minSubarrayLen(target, nums) {
  let left = 0, sum = 0, minLen = Infinity;

  for (let right = 0; right < nums.length; right++) {
    sum += nums[right];
    while (sum >= target) {
      minLen = Math.min(minLen, right - left + 1);
      sum -= nums[left++];
    }
  }
  return minLen === Infinity ? 0 : minLen;
}

console.log(minSubarrayLen(7, [2, 3, 1, 2, 4, 3])); // 2 (subarray [4,3])
```

---

## 15. Two Pointers Pattern

### 📖 Definition
The **Two Pointers** technique uses two pointers that move through the data structure simultaneously, often from opposite ends. It reduces O(n²) brute-force solutions to O(n).

### 💻 Code Examples

**Two Sum in Sorted Array**
```javascript
function twoSumSorted(arr, target) {
  let left = 0, right = arr.length - 1;

  while (left < right) {
    const sum = arr[left] + arr[right];
    if (sum === target) return [left, right];
    else if (sum < target) left++;
    else right--;
  }
  return [];
}

console.log(twoSumSorted([1, 2, 3, 4, 6], 6)); // [1, 3]
```

**Container With Most Water**
```javascript
function maxArea(height) {
  let left = 0, right = height.length - 1, max = 0;

  while (left < right) {
    const area = Math.min(height[left], height[right]) * (right - left);
    max = Math.max(max, area);
    if (height[left] < height[right]) left++;
    else right--;
  }
  return max;
}

console.log(maxArea([1, 8, 6, 2, 5, 4, 8, 3, 7])); // 49
```

**3Sum**
```javascript
function threeSum(nums) {
  nums.sort((a, b) => a - b);
  const result = [];

  for (let i = 0; i < nums.length - 2; i++) {
    if (i > 0 && nums[i] === nums[i - 1]) continue; // Skip duplicates

    let left = i + 1, right = nums.length - 1;
    while (left < right) {
      const sum = nums[i] + nums[left] + nums[right];
      if (sum === 0) {
        result.push([nums[i], nums[left], nums[right]]);
        while (left < right && nums[left] === nums[left + 1]) left++;
        while (left < right && nums[right] === nums[right - 1]) right--;
        left++; right--;
      } else if (sum < 0) left++;
      else right--;
    }
  }
  return result;
}

console.log(threeSum([-1, 0, 1, 2, -1, -4]));
// [[-1,-1,2],[-1,0,1]]
```

---

## 16. Prefix Sum

### 📖 Definition
**Prefix Sum** (also called cumulative sum) is a technique where you precompute the sum of elements from index 0 to i. This allows range sum queries in O(1) after O(n) preprocessing.

### 💻 Code Examples

**Range Sum Query**
```javascript
class PrefixSum {
  constructor(nums) {
    this.prefix = [0];
    for (const num of nums) {
      this.prefix.push(this.prefix[this.prefix.length - 1] + num);
    }
  }

  // Sum from index l to r (inclusive) — O(1)
  query(l, r) {
    return this.prefix[r + 1] - this.prefix[l];
  }
}

const ps = new PrefixSum([2, 4, 3, 1, 6, 1, 8]);
console.log(ps.query(2, 5)); // 11 (3+1+6+1)
console.log(ps.query(0, 3)); // 10 (2+4+3+1)
```

**Subarray Sum Equals K**
```javascript
function subarraySum(nums, k) {
  const map = new Map([[0, 1]]);
  let count = 0, sum = 0;

  for (const num of nums) {
    sum += num;
    count += (map.get(sum - k) || 0);
    map.set(sum, (map.get(sum) || 0) + 1);
  }
  return count;
}

console.log(subarraySum([1, 1, 1], 2)); // 2
console.log(subarraySum([1, 2, 3], 3)); // 2
```

---

## 17. Backtracking

### 📖 Definition
**Backtracking** is a recursive algorithm that builds solutions incrementally and **abandons** (backtracks) a path as soon as it determines that path cannot lead to a valid solution. Used in constraint satisfaction problems.

### 💻 Code Examples

**Generate All Subsets (Power Set)**
```javascript
function subsets(nums) {
  const result = [];

  function backtrack(start, current) {
    result.push([...current]);

    for (let i = start; i < nums.length; i++) {
      current.push(nums[i]);
      backtrack(i + 1, current);
      current.pop(); // Backtrack
    }
  }

  backtrack(0, []);
  return result;
}

console.log(subsets([1, 2, 3]));
// [[], [1], [1,2], [1,2,3], [1,3], [2], [2,3], [3]]
```

**Generate All Permutations**
```javascript
function permutations(nums) {
  const result = [];

  function backtrack(current, remaining) {
    if (!remaining.length) { result.push([...current]); return; }

    for (let i = 0; i < remaining.length; i++) {
      current.push(remaining[i]);
      backtrack(current, [...remaining.slice(0, i), ...remaining.slice(i + 1)]);
      current.pop(); // Backtrack
    }
  }

  backtrack([], nums);
  return result;
}

console.log(permutations([1, 2, 3]).length); // 6
```

**N-Queens Problem**
```javascript
function solveNQueens(n) {
  const result = [];
  const board = Array.from({ length: n }, () => '.'.repeat(n));

  function isValid(row, col, board) {
    for (let i = 0; i < row; i++) if (board[i][col] === 'Q') return false;
    for (let i = row - 1, j = col - 1; i >= 0 && j >= 0; i--, j--)
      if (board[i][j] === 'Q') return false;
    for (let i = row - 1, j = col + 1; i >= 0 && j < n; i--, j++)
      if (board[i][j] === 'Q') return false;
    return true;
  }

  function backtrack(row) {
    if (row === n) { result.push([...board]); return; }
    for (let col = 0; col < n; col++) {
      if (isValid(row, col, board)) {
        board[row] = board[row].substring(0, col) + 'Q' + board[row].substring(col + 1);
        backtrack(row + 1);
        board[row] = board[row].substring(0, col) + '.' + board[row].substring(col + 1);
      }
    }
  }

  backtrack(0);
  return result;
}

console.log(solveNQueens(4).length); // 2
```

---

## 18. Bit Manipulation

### 📖 Definition
**Bit Manipulation** involves operations directly on binary representations of integers. These operations are extremely fast (O(1)) and often help optimize space and time.

### 📊 Bitwise Operators

| Operator | Symbol | Example | Result |
|----------|--------|---------|--------|
| AND | `&` | `5 & 3` | `1` |
| OR | `\|` | `5 \| 3` | `7` |
| XOR | `^` | `5 ^ 3` | `6` |
| NOT | `~` | `~5` | `-6` |
| Left Shift | `<<` | `5 << 1` | `10` |
| Right Shift | `>>` | `5 >> 1` | `2` |

### 💻 Code Examples

```javascript
// Check if number is even or odd
const isEven = n => (n & 1) === 0;
console.log(isEven(4)); // true
console.log(isEven(7)); // false

// Check if number is power of 2
const isPowerOfTwo = n => n > 0 && (n & (n - 1)) === 0;
console.log(isPowerOfTwo(16)); // true
console.log(isPowerOfTwo(18)); // false

// Count set bits (Brian Kernighan's algorithm)
function countSetBits(n) {
  let count = 0;
  while (n) { n &= n - 1; count++; }
  return count;
}
console.log(countSetBits(13)); // 3 (1101)

// Find single number (all others appear twice)
function singleNumber(nums) {
  return nums.reduce((acc, n) => acc ^ n, 0);
}
console.log(singleNumber([4, 1, 2, 1, 2])); // 4

// Swap two numbers without temp variable
let a = 5, b = 3;
a ^= b; b ^= a; a ^= b;
console.log(a, b); // 3 5

// Get, Set, Clear, Toggle bit at position i
const getBit    = (n, i) => (n >> i) & 1;
const setBit    = (n, i) => n | (1 << i);
const clearBit  = (n, i) => n & ~(1 << i);
const toggleBit = (n, i) => n ^ (1 << i);
```

---

## 19. Big-O Cheat Sheet

### Time Complexity

| Notation | Name | Example |
|----------|------|---------|
| O(1) | Constant | Hash map lookup, array access |
| O(log n) | Logarithmic | Binary search, BST operations |
| O(n) | Linear | Linear search, single loop |
| O(n log n) | Linearithmic | Merge sort, heap sort |
| O(n²) | Quadratic | Bubble sort, nested loops |
| O(n³) | Cubic | Matrix multiplication (naive) |
| O(2ⁿ) | Exponential | Recursive Fibonacci, subsets |
| O(n!) | Factorial | All permutations |

### Space Complexity

| Structure | Space |
|-----------|-------|
| Array of n elements | O(n) |
| 2D Matrix (n×m) | O(n·m) |
| Recursive call stack depth d | O(d) |
| Hash map with n entries | O(n) |

### Growth Rate (Fastest → Slowest)
```
O(1) < O(log n) < O(√n) < O(n) < O(n log n) < O(n²) < O(2ⁿ) < O(n!)
```

---

## 20. Top Interview Questions

### 🟢 Easy
| # | Problem | Key Concept |
|---|---------|------------|
| 1 | Two Sum | Hash Map |
| 2 | Valid Parentheses | Stack |
| 3 | Merge Two Sorted Lists | Linked List |
| 4 | Best Time to Buy and Sell Stock | Sliding Window |
| 5 | Contains Duplicate | Hash Set |
| 6 | Maximum Subarray | Kadane's Algorithm |
| 7 | Reverse Linked List | Two Pointers |
| 8 | Climbing Stairs | Dynamic Programming |

### 🟡 Medium
| # | Problem | Key Concept |
|---|---------|------------|
| 1 | 3Sum | Two Pointers + Sort |
| 2 | Longest Substring Without Repeating | Sliding Window |
| 3 | Binary Tree Level Order Traversal | BFS / Queue |
| 4 | Number of Islands | DFS / BFS on Grid |
| 5 | Coin Change | Dynamic Programming |
| 6 | Product of Array Except Self | Prefix Sum |
| 7 | Longest Increasing Subsequence | DP |
| 8 | Course Schedule | Topological Sort |

### 🔴 Hard
| # | Problem | Key Concept |
|---|---------|------------|
| 1 | Trapping Rain Water | Two Pointers / Stack |
| 2 | Sliding Window Maximum | Monotonic Deque |
| 3 | Merge K Sorted Lists | Heap |
| 4 | Word Break II | Backtracking + DP |
| 5 | LRU Cache | HashMap + DLL |
| 6 | N-Queens | Backtracking |
| 7 | Serialize / Deserialize Binary Tree | BFS / DFS |
| 8 | Median of Two Sorted Arrays | Binary Search |

---

## 🗺️ Learning Roadmap

```
Phase 1 — Foundation (Week 1–2)
  └── Arrays → Strings → Hash Maps → Recursion

Phase 2 — Linear Structures (Week 3–4)
  └── Linked Lists → Stacks → Queues → Searching → Sorting

Phase 3 — Non-Linear Structures (Week 5–7)
  └── Trees → BST → Heaps → Graphs

Phase 4 — Advanced Patterns (Week 8–10)
  └── Dynamic Programming → Backtracking → Sliding Window
      → Two Pointers → Prefix Sum → Bit Manipulation

Phase 5 — Interview Prep (Week 11–12)
  └── LeetCode Easy (50+) → Medium (100+) → Hard (20+)
      → Mock Interviews → System Design Basics
```

---

<div align="center">

## ⭐ Support This Project

If this helps you crack your interviews, consider:

[![Star](https://img.shields.io/badge/⭐%20Star-this%20repo-yellow?style=for-the-badge)](https://github.com)
[![Fork](https://img.shields.io/badge/🍴%20Fork-this%20repo-blue?style=for-the-badge)](https://github.com)
[![Share](https://img.shields.io/badge/📢%20Share-with%20others-green?style=for-the-badge)](https://github.com)

---

### 👨‍💻 Author

**Lalit Katheirya**

*Full Stack Developer · Angular · React · Node.js · MongoDB*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://linkedin.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com)

---

*Made with ❤️ for developers preparing for technical interviews*

</div>
