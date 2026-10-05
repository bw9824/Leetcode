# LeetCode Progress Chart — Embedded / Firmware

> Reordered based on [[Embedded Firmware Engineer 面試準備攻略|Embedded Firmware Interview Prep Guide]]: **high-frequency embedded topics first, Tree / Graph / DP last**.
> Problems = **Blind 75** ∪ **NeetCode 75 / 150 / 250** ∪ **LeetCode Top Interview 150** ∪ **LeetCode Hot 100** ∪ extra embedded problems from interview reports. Solve everything in **C**.

## Legend

| Tag | Meaning |
|---|---|
| `75` | In both **Blind 75** (original list) and **NeetCode 75** (NeetCode's Blind 75 edition) |
| `B75` / `N75` | Only in Blind 75 (377) / only in NeetCode 75 (39) |
| `N150` | NeetCode 150 (not in NeetCode 75) — NeetCode 75 ⊂ 150 ⊂ 250, so only the smallest NeetCode list is shown |
| `N250` | NeetCode 250 (not in NeetCode 150) |
| `I150` | LeetCode Top Interview 150 |
| `H100` | LeetCode Hot 100 (Top 100 Liked) |
| `FW` | Not in any list above — extra embedded problem added from the prep guide |
| ⭐ | Actually asked in interviews / called out as high-frequency in the guide |
| 🔒 | LeetCode Premium (free on NeetCode / LintCode) |

## Suggested Order

1. **Round 1**: ⭐ and `75` problems in Tier 1 → fastest coverage of high-frequency questions
2. **Round 2**: the rest of Tier 1 + Tier 2 Concurrency (hand-write with pthread)
3. **Round 3**: `N150` / `I150` / `H100` problems in Tier 2
4. **Extra time**: `75` problems in Tier 3 → then `N150` / `H100` / `I150` → `N250` last
5. For every problem: list edge cases (NULL / empty / single element / overflow), dry run it yourself, and state time / space complexity

## Overview

| Tier | Category | Total | ⭐ | Blind 75 | NC 75 | NC 150 | NC 250 | Top Int. 150 | Hot 100 | FW |
|---|---|---|---|---|---|---|---|---|---|---|
| Tier 1 | [[#Linked List]] | 27 | 12 | 6 | 6 | 11 | 14 | 13 | 15 | 5 |
| Tier 1 | [[#Bit Manipulation]] | 18 | 3 | 5 | 5 | 7 | 10 | 6 | 1 | 7 |
| Tier 1 | [[#String]] | 18 | 2 | 3 | 3 | 4 | 7 | 13 | 1 | 2 |
| Tier 1 | [[#Array & Hashing]] | 25 | 1 | 5 | 5 | 5 | 20 | 12 | 11 | 0 |
| Tier 1 | [[#Stack & Queue]] | 19 | 3 | 1 | 1 | 7 | 16 | 6 | 7 | 1 |
| Tier 1 | [[#Matrix & Math]] | 18 | 1 | 3 | 3 | 8 | 12 | 12 | 4 | 1 |
| Tier 2 | [[#Two Pointers]] | 10 | 0 | 3 | 3 | 5 | 9 | 6 | 3 | 0 |
| Tier 2 | [[#Sliding Window]] | 10 | 0 | 4 | 4 | 6 | 8 | 5 | 5 | 0 |
| Tier 2 | [[#Binary Search]] | 16 | 0 | 2 | 2 | 7 | 13 | 7 | 7 | 0 |
| Tier 2 | [[#Concurrency]] | 7 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 7 |
| Tier 2 | [[#Intervals]] | 9 | 0 | 5 | 5 | 6 | 7 | 4 | 1 | 0 |
| Tier 2 | [[#Heap (Priority Queue)]] | 13 | 0 | 1 | 1 | 7 | 12 | 4 | 2 | 0 |
| Tier 3 | [[#Tree]] | 37 | 0 | 11 | 11 | 15 | 23 | 23 | 15 | 0 |
| Tier 3 | [[#Trie]] | 4 | 0 | 3 | 3 | 3 | 4 | 3 | 1 | 0 |
| Tier 3 | [[#Backtracking]] | 16 | 0 | 1 | 2 | 9 | 16 | 6 | 7 | 0 |
| Tier 3 | [[#Graph]] | 23 | 0 | 6 | 6 | 13 | 21 | 9 | 3 | 0 |
| Tier 3 | [[#Advanced Graph]] | 10 | 0 | 1 | 1 | 6 | 10 | 0 | 0 | 0 |
| Tier 3 | [[#Greedy]] | 15 | 0 | 2 | 2 | 8 | 15 | 7 | 4 | 0 |
| Tier 3 | [[#1-D Dynamic Programming]] | 17 | 0 | 11 | 10 | 12 | 17 | 6 | 9 | 0 |
| Tier 3 | [[#2-D Dynamic Programming]] | 20 | 0 | 2 | 2 | 11 | 16 | 8 | 4 | 0 |
| | **Total** | **332** | **24** | **75** | **75** | **150** | **250** | **150** | **100** | **23** |

---

# Tier 1 — Must Do (Core Embedded Interview Topics)

## Linked List

> The most frequently asked topic: reverse (iterative + recursive), dummy node vs `Node **`, fast/slow pointers, merge. Be able to hand-write struct / malloc / free in C.

| #    | Title                                                                                                                           | Difficulty | Source               | ⭐   | Date       |
| ---- | ------------------------------------------------------------------------------------------------------------------------------- | ---------- | -------------------- | --- | ---------- |
| 206  | [Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)                                                       | Easy       | `75` `H100`          | ⭐   | 2026/09/30 |
| 21   | [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)                                                 | Easy       | `75` `I150` `H100`   | ⭐   | 2026/09/30 |
| 141  | [Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)                                                           | Easy       | `75` `I150` `H100`   | ⭐   | 2026/09/30 |
| 876  | [Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)                                           | Easy       | `FW`                 | ⭐   |            |
| 234  | [Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)                                                 | Easy       | `H100`               | ⭐   |            |
| 203  | [Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/)                                       | Easy       | `FW`                 |     |            |
| 83   | [Remove Duplicates From Sorted List](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)                         | Easy       | `FW`                 |     |            |
| 160  | [Intersection of Two Linked Lists](https://leetcode.com/problems/intersection-of-two-linked-lists/)                             | Easy       | `H100`               |     |            |
| 707  | [Design Linked List](https://leetcode.com/problems/design-linked-list/)                                                         | Medium     | `FW`                 | ⭐   |            |
| 92   | [Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/)                                                 | Medium     | `N250` `I150`        | ⭐   |            |
| 24   | [Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/)                                                       | Medium     | `H100`               | ⭐   |            |
| 61   | [Rotate List](https://leetcode.com/problems/rotate-list/)                                                                       | Medium     | `I150`               | ⭐   |            |
| 328  | [Odd Even Linked List](https://leetcode.com/problems/odd-even-linked-list/)                                                     | Medium     | `FW`                 | ⭐   |            |
| 142  | [Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)                                                     | Medium     | `H100`               |     |            |
| 19   | [Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)                             | Medium     | `75` `I150` `H100`   |     | 2026/09/29 |
| 143  | [Reorder List](https://leetcode.com/problems/reorder-list/)                                                                     | Medium     | `75`                 |     | 2026/09/30 |
| 2    | [Add Two Numbers](https://leetcode.com/problems/add-two-numbers/)                                                               | Medium     | `N150` `I150` `H100` |     |            |
| 82   | [Remove Duplicates From Sorted List II](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/)                   | Medium     | `I150`               |     |            |
| 86   | [Partition List](https://leetcode.com/problems/partition-list/)                                                                 | Medium     | `I150`               |     |            |
| 138  | [Copy List With Random Pointer](https://leetcode.com/problems/copy-list-with-random-pointer/)                                   | Medium     | `N150` `I150` `H100` |     |            |
| 287  | [Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/)                                           | Medium     | `N150` `H100`        |     |            |
| 148  | [Sort List](https://leetcode.com/problems/sort-list/)                                                                           | Medium     | `I150` `H100`        | ⭐   |            |
| 146  | [LRU Cache](https://leetcode.com/problems/lru-cache/)                                                                           | Medium     | `N150` `I150` `H100` |     |            |
| 2807 | [Insert Greatest Common Divisors in Linked List](https://leetcode.com/problems/insert-greatest-common-divisors-in-linked-list/) | Medium     | `N250`               |     |            |
| 23   | [Merge K Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)                                                     | Hard       | `75` `I150` `H100`   | ⭐   | 2026/09/30 |
| 25   | [Reverse Nodes in K-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/)                                             | Hard       | `N150` `I150` `H100` |     |            |
| 460  | [LFU Cache](https://leetcode.com/problems/lfu-cache/)                                                                           | Hard       | `N250`               |     |            |

## Bit Manipulation

> set / clear / toggle / mask / shift; know at least two ways to count bits; reverse / swap bits, 2's complement, addition without `+`. Also go through GeeksforGeeks easy + medium.

| #    | Title                                                                                                     | Difficulty | Source               | ⭐   | Date       |
| ---- | --------------------------------------------------------------------------------------------------------- | ---------- | -------------------- | --- | ---------- |
| 191  | [Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/)                                       | Easy       | `75` `I150`          | ⭐   | 2026/09/30 |
| 338  | [Counting Bits](https://leetcode.com/problems/counting-bits/)                                             | Easy       | `75`                 |     | 2026/09/30 |
| 190  | [Reverse Bits](https://leetcode.com/problems/reverse-bits/)                                               | Easy       | `75` `I150`          | ⭐   | 2026/09/30 |
| 268  | [Missing Number](https://leetcode.com/problems/missing-number/)                                           | Easy       | `75`                 |     | 2026/09/30 |
| 136  | [Single Number](https://leetcode.com/problems/single-number/)                                             | Easy       | `N150` `I150` `H100` |     |            |
| 231  | [Power of Two](https://leetcode.com/problems/power-of-two/)                                               | Easy       | `FW`                 |     |            |
| 342  | [Power of Four](https://leetcode.com/problems/power-of-four/)                                             | Easy       | `FW`                 |     |            |
| 461  | [Hamming Distance](https://leetcode.com/problems/hamming-distance/)                                       | Easy       | `FW`                 |     |            |
| 476  | [Number Complement](https://leetcode.com/problems/number-complement/)                                     | Easy       | `FW`                 |     |            |
| 693  | [Binary Number With Alternating Bits](https://leetcode.com/problems/binary-number-with-alternating-bits/) | Easy       | `FW`                 |     |            |
| 405  | [Convert a Number to Hexadecimal](https://leetcode.com/problems/convert-a-number-to-hexadecimal/)         | Easy       | `FW`                 |     |            |
| 67   | [Add Binary](https://leetcode.com/problems/add-binary/)                                                   | Easy       | `N250` `I150`        |     |            |
| 371  | [Sum of Two Integers](https://leetcode.com/problems/sum-of-two-integers/)                                 | Medium     | `75`                 | ⭐   | 2026/09/30 |
| 7    | [Reverse Integer](https://leetcode.com/problems/reverse-integer/)                                         | Medium     | `N150`               |     |            |
| 137  | [Single Number II](https://leetcode.com/problems/single-number-ii/)                                       | Medium     | `I150`               |     |            |
| 201  | [Bitwise AND of Numbers Range](https://leetcode.com/problems/bitwise-and-of-numbers-range/)               | Medium     | `N250` `I150`        |     |            |
| 29   | [Divide Two Integers](https://leetcode.com/problems/divide-two-integers/)                                 | Medium     | `FW`                 |     |            |
| 3133 | [Minimum Array End](https://leetcode.com/problems/minimum-array-end/)                                     | Medium     | `N250`               |     |            |

## String

> Two pointers, hashing (in C use `int cnt[256]`), case conversion, in-place modification; for atoi / itoa watch for overflow and negative signs.

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 242 | [Valid Anagram](https://leetcode.com/problems/valid-anagram/) | Easy | `75` `I150` |  |  |
| 383 | [Ransom Note](https://leetcode.com/problems/ransom-note/) | Easy | `I150` |  |  |
| 205 | [Isomorphic Strings](https://leetcode.com/problems/isomorphic-strings/) | Easy | `I150` |  |  |
| 290 | [Word Pattern](https://leetcode.com/problems/word-pattern/) | Easy | `I150` |  |  |
| 344 | [Reverse String](https://leetcode.com/problems/reverse-string/) | Easy | `N250` |  |  |
| 13 | [Roman to Integer](https://leetcode.com/problems/roman-to-integer/) | Easy | `N250` `I150` |  |  |
| 58 | [Length of Last Word](https://leetcode.com/problems/length-of-last-word/) | Easy | `I150` |  |  |
| 14 | [Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/) | Easy | `N250` `I150` |  |  |
| 28 | [Find the Index of the First Occurrence in a String](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/) | Easy | `I150` |  |  |
| 8 | [String to Integer (atoi)](https://leetcode.com/problems/string-to-integer-atoi/) | Medium | `FW` | ⭐ |  |
| 443 | [String Compression](https://leetcode.com/problems/string-compression/) | Medium | `FW` | ⭐ |  |
| 49 | [Group Anagrams](https://leetcode.com/problems/group-anagrams/) | Medium | `75` `I150` `H100` |  |  |
| 271 | [Encode and Decode Strings](https://leetcode.com/problems/encode-and-decode-strings/) 🔒 | Medium | `75` |  |  |
| 12 | [Integer to Roman](https://leetcode.com/problems/integer-to-roman/) | Medium | `I150` |  |  |
| 151 | [Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/) | Medium | `I150` |  |  |
| 6 | [Zigzag Conversion](https://leetcode.com/problems/zigzag-conversion/) | Medium | `I150` |  |  |
| 43 | [Multiply Strings](https://leetcode.com/problems/multiply-strings/) | Medium | `N150` |  |  |
| 68 | [Text Justification](https://leetcode.com/problems/text-justification/) | Hard | `I150` |  |  |

## Array & Hashing

> In-place operations (read/write pointers), prefix/suffix, hash set; be able to hand-write quick sort / merge sort.

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 217 | [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/) | Easy | `75` |  | 2026/08/30 |
| 1 | [Two Sum](https://leetcode.com/problems/two-sum/) | Easy | `75` `I150` `H100` |  |  |
| 88 | [Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/) | Easy | `N250` `I150` |  |  |
| 27 | [Remove Element](https://leetcode.com/problems/remove-element/) | Easy | `N250` `I150` |  |  |
| 26 | [Remove Duplicates From Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/) | Easy | `N250` `I150` |  |  |
| 169 | [Majority Element](https://leetcode.com/problems/majority-element/) | Easy | `N250` `I150` `H100` |  |  |
| 219 | [Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/) | Easy | `N250` `I150` |  |  |
| 283 | [Move Zeroes](https://leetcode.com/problems/move-zeroes/) | Easy | `H100` |  |  |
| 1929 | [Concatenation of Array](https://leetcode.com/problems/concatenation-of-array/) | Easy | `N250` |  |  |
| 705 | [Design HashSet](https://leetcode.com/problems/design-hashset/) | Easy | `N250` |  |  |
| 706 | [Design HashMap](https://leetcode.com/problems/design-hashmap/) | Easy | `N250` |  |  |
| 80 | [Remove Duplicates From Sorted Array II](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/) | Medium | `I150` |  |  |
| 189 | [Rotate Array](https://leetcode.com/problems/rotate-array/) | Medium | `N250` `I150` `H100` |  |  |
| 75 | [Sort Colors](https://leetcode.com/problems/sort-colors/) | Medium | `N250` `H100` |  |  |
| 912 | [Sort an Array](https://leetcode.com/problems/sort-an-array/) | Medium | `N250` | ⭐ |  |
| 274 | [H-Index](https://leetcode.com/problems/h-index/) | Medium | `I150` |  |  |
| 380 | [Insert Delete GetRandom O(1)](https://leetcode.com/problems/insert-delete-getrandom-o1/) | Medium | `I150` |  |  |
| 347 | [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/) | Medium | `75` `H100` |  |  |
| 238 | [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/) | Medium | `75` `I150` `H100` |  |  |
| 128 | [Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/) | Medium | `75` `I150` `H100` |  |  |
| 229 | [Majority Element II](https://leetcode.com/problems/majority-element-ii/) | Medium | `N250` |  |  |
| 560 | [Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/) | Medium | `N250` `H100` |  |  |
| 304 | [Range Sum Query 2D - Immutable](https://leetcode.com/problems/range-sum-query-2d-immutable/) | Medium | `N250` |  |  |
| 31 | [Next Permutation](https://leetcode.com/problems/next-permutation/) | Medium | `H100` |  |  |
| 41 | [First Missing Positive](https://leetcode.com/problems/first-missing-positive/) | Hard | `N250` `H100` |  |  |

## Stack & Queue

> Implement stack, queue, and circular buffer with an array / linked list; stack is often paired with LC 20; the queue follow-up is producer–consumer.

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 20 | [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/) | Easy | `75` `I150` `H100` | ⭐ | 2026/08/30 |
| 232 | [Implement Queue Using Stacks](https://leetcode.com/problems/implement-queue-using-stacks/) | Easy | `N250` | ⭐ |  |
| 225 | [Implement Stack Using Queues](https://leetcode.com/problems/implement-stack-using-queues/) | Easy | `N250` |  |  |
| 682 | [Baseball Game](https://leetcode.com/problems/baseball-game/) | Easy | `N250` |  |  |
| 155 | [Min Stack](https://leetcode.com/problems/min-stack/) | Medium | `N150` `I150` `H100` |  |  |
| 622 | [Design Circular Queue](https://leetcode.com/problems/design-circular-queue/) | Medium | `N250` | ⭐ |  |
| 641 | [Design Circular Deque](https://leetcode.com/problems/design-circular-deque/) | Medium | `FW` |  |  |
| 150 | [Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/) | Medium | `N150` `I150` |  |  |
| 71 | [Simplify Path](https://leetcode.com/problems/simplify-path/) | Medium | `N250` `I150` |  |  |
| 22 | [Generate Parentheses](https://leetcode.com/problems/generate-parentheses/) | Medium | `N150` `I150` `H100` |  |  |
| 739 | [Daily Temperatures](https://leetcode.com/problems/daily-temperatures/) | Medium | `N150` `H100` |  |  |
| 853 | [Car Fleet](https://leetcode.com/problems/car-fleet/) | Medium | `N150` |  |  |
| 735 | [Asteroid Collision](https://leetcode.com/problems/asteroid-collision/) | Medium | `N250` |  |  |
| 901 | [Online Stock Span](https://leetcode.com/problems/online-stock-span/) | Medium | `N250` |  |  |
| 394 | [Decode String](https://leetcode.com/problems/decode-string/) | Medium | `N250` `H100` |  |  |
| 84 | [Largest Rectangle in Histogram](https://leetcode.com/problems/largest-rectangle-in-histogram/) | Hard | `N150` `H100` |  |  |
| 224 | [Basic Calculator](https://leetcode.com/problems/basic-calculator/) | Hard | `I150` |  |  |
| 895 | [Maximum Frequency Stack](https://leetcode.com/problems/maximum-frequency-stack/) | Hard | `N250` |  |  |
| 32 | [Longest Valid Parentheses](https://leetcode.com/problems/longest-valid-parentheses/) | Hard | `H100` |  |  |

## Matrix & Math

> Dynamic 2D array allocation, row-major / column-major flattening, matmul; overflow handling.

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 566 | [Reshape the Matrix](https://leetcode.com/problems/reshape-the-matrix/) | Easy | `FW` | ⭐ |  |
| 867 | [Transpose Matrix](https://leetcode.com/problems/transpose-matrix/) | Easy | `N250` |  |  |
| 9 | [Palindrome Number](https://leetcode.com/problems/palindrome-number/) | Easy | `I150` |  |  |
| 66 | [Plus One](https://leetcode.com/problems/plus-one/) | Easy | `N150` `I150` |  |  |
| 202 | [Happy Number](https://leetcode.com/problems/happy-number/) | Easy | `N150` `I150` |  |  |
| 69 | [Sqrt(x)](https://leetcode.com/problems/sqrtx/) | Easy | `N250` `I150` |  |  |
| 118 | [Pascal's Triangle](https://leetcode.com/problems/pascals-triangle/) | Easy | `H100` |  |  |
| 168 | [Excel Sheet Column Title](https://leetcode.com/problems/excel-sheet-column-title/) | Easy | `N250` |  |  |
| 1071 | [Greatest Common Divisor of Strings](https://leetcode.com/problems/greatest-common-divisor-of-strings/) | Easy | `N250` |  |  |
| 48 | [Rotate Image](https://leetcode.com/problems/rotate-image/) | Medium | `75` `I150` `H100` |  | 2026/09/04 |
| 54 | [Spiral Matrix](https://leetcode.com/problems/spiral-matrix/) | Medium | `75` `I150` `H100` |  | 2026/09/04 |
| 73 | [Set Matrix Zeroes](https://leetcode.com/problems/set-matrix-zeroes/) | Medium | `75` `I150` `H100` |  | 2026/09/04 |
| 36 | [Valid Sudoku](https://leetcode.com/problems/valid-sudoku/) | Medium | `N150` `I150` |  |  |
| 289 | [Game of Life](https://leetcode.com/problems/game-of-life/) | Medium | `I150` |  |  |
| 172 | [Factorial Trailing Zeroes](https://leetcode.com/problems/factorial-trailing-zeroes/) | Medium | `I150` |  |  |
| 50 | [Pow(x, n)](https://leetcode.com/problems/powx-n/) | Medium | `N150` `I150` |  |  |
| 2013 | [Detect Squares](https://leetcode.com/problems/detect-squares/) | Medium | `N150` |  |  |
| 149 | [Max Points on a Line](https://leetcode.com/problems/max-points-on-a-line/) | Hard | `I150` |  |  |

---

# Tier 2 — Intermediate (Common Variations)

## Two Pointers

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 125 | [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) | Easy | `75` `I150` |  | 2026/09/02 |
| 392 | [Is Subsequence](https://leetcode.com/problems/is-subsequence/) | Easy | `I150` |  |  |
| 680 | [Valid Palindrome II](https://leetcode.com/problems/valid-palindrome-ii/) | Easy | `N250` |  |  |
| 1768 | [Merge Strings Alternately](https://leetcode.com/problems/merge-strings-alternately/) | Easy | `N250` |  |  |
| 167 | [Two Sum II Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/) | Medium | `N150` `I150` |  |  |
| 15 | [3Sum](https://leetcode.com/problems/3sum/) | Medium | `75` `I150` `H100` |  |  |
| 11 | [Container With Most Water](https://leetcode.com/problems/container-with-most-water/) | Medium | `75` `I150` `H100` |  | 2026/09/02 |
| 18 | [4Sum](https://leetcode.com/problems/4sum/) | Medium | `N250` |  |  |
| 881 | [Boats to Save People](https://leetcode.com/problems/boats-to-save-people/) | Medium | `N250` |  |  |
| 42 | [Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/) | Hard | `N150` `I150` `H100` |  |  |

## Sliding Window

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 121 | [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/) | Easy | `75` `I150` `H100` |  | 2026/09/05 |
| 3 | [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/) | Medium | `75` `I150` `H100` |  |  |
| 424 | [Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/) | Medium | `75` |  |  |
| 567 | [Permutation in String](https://leetcode.com/problems/permutation-in-string/) | Medium | `N150` |  |  |
| 209 | [Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/) | Medium | `N250` `I150` |  |  |
| 438 | [Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/) | Medium | `H100` |  |  |
| 658 | [Find K Closest Elements](https://leetcode.com/problems/find-k-closest-elements/) | Medium | `N250` |  |  |
| 76 | [Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/) | Hard | `75` `I150` `H100` |  |  |
| 239 | [Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/) | Hard | `N150` `H100` |  |  |
| 30 | [Substring With Concatenation of All Words](https://leetcode.com/problems/substring-with-concatenation-of-all-words/) | Hard | `I150` |  |  |

## Binary Search

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 704 | [Binary Search](https://leetcode.com/problems/binary-search/) | Easy | `N150` |  |  |
| 35 | [Search Insert Position](https://leetcode.com/problems/search-insert-position/) | Easy | `N250` `I150` `H100` |  |  |
| 374 | [Guess Number Higher or Lower](https://leetcode.com/problems/guess-number-higher-or-lower/) | Easy | `N250` |  |  |
| 74 | [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/) | Medium | `N150` `I150` `H100` |  |  |
| 162 | [Find Peak Element](https://leetcode.com/problems/find-peak-element/) | Medium | `I150` |  |  |
| 34 | [Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/) | Medium | `I150` `H100` |  |  |
| 875 | [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/) | Medium | `N150` |  |  |
| 153 | [Find Minimum in Rotated Sorted Array](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/) | Medium | `75` `I150` `H100` |  | 2026/09/05 |
| 33 | [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/) | Medium | `75` `I150` `H100` |  | 2026/09/05 |
| 981 | [Time Based Key-Value Store](https://leetcode.com/problems/time-based-key-value-store/) | Medium | `N150` |  |  |
| 240 | [Search a 2D Matrix II](https://leetcode.com/problems/search-a-2d-matrix-ii/) | Medium | `H100` |  |  |
| 1011 | [Capacity To Ship Packages Within D Days](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/) | Medium | `N250` |  |  |
| 81 | [Search in Rotated Sorted Array II](https://leetcode.com/problems/search-in-rotated-sorted-array-ii/) | Medium | `N250` |  |  |
| 4 | [Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) | Hard | `N150` `I150` `H100` |  |  |
| 410 | [Split Array Largest Sum](https://leetcode.com/problems/split-array-largest-sum/) | Hard | `N250` |  |  |
| 1095 | [Find in Mountain Array](https://leetcode.com/problems/find-in-mountain-array/) | Hard | `N250` |  |  |

## Concurrency

> LeetCode Concurrency problems (C / pthread). Asked in interviews: two threads printing odd/even alternately, producer–consumer, bounded buffer.

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 1114 | [Print in Order](https://leetcode.com/problems/print-in-order/) | Easy | `FW` |  |  |
| 1115 | [Print FooBar Alternately](https://leetcode.com/problems/print-foobar-alternately/) | Medium | `FW` |  |  |
| 1116 | [Print Zero Even Odd](https://leetcode.com/problems/print-zero-even-odd/) | Medium | `FW` | ⭐ |  |
| 1195 | [Fizz Buzz Multithreaded](https://leetcode.com/problems/fizz-buzz-multithreaded/) | Medium | `FW` |  |  |
| 1117 | [Building H2O](https://leetcode.com/problems/building-h2o/) | Medium | `FW` |  |  |
| 1226 | [The Dining Philosophers](https://leetcode.com/problems/the-dining-philosophers/) | Medium | `FW` |  |  |
| 1188 | [Design Bounded Blocking Queue](https://leetcode.com/problems/design-bounded-blocking-queue/) 🔒 | Medium | `FW` | ⭐ |  |

## Intervals

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 252 | [Meeting Rooms](https://leetcode.com/problems/meeting-rooms/) 🔒 | Easy | `75` |  | 2026/09/04 |
| 228 | [Summary Ranges](https://leetcode.com/problems/summary-ranges/) | Easy | `I150` |  |  |
| 57 | [Insert Interval](https://leetcode.com/problems/insert-interval/) | Medium | `75` `I150` |  |  |
| 56 | [Merge Intervals](https://leetcode.com/problems/merge-intervals/) | Medium | `75` `I150` `H100` |  |  |
| 435 | [Non-Overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/) | Medium | `75` |  |  |
| 452 | [Minimum Number of Arrows to Burst Balloons](https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons/) | Medium | `I150` |  |  |
| 253 | [Meeting Rooms II](https://leetcode.com/problems/meeting-rooms-ii/) 🔒 | Medium | `75` |  | 2026/09/06 |
| 1851 | [Minimum Interval to Include Each Query](https://leetcode.com/problems/minimum-interval-to-include-each-query/) | Hard | `N150` |  |  |
| 2402 | [Meeting Rooms III](https://leetcode.com/problems/meeting-rooms-iii/) | Hard | `N250` |  |  |

## Heap (Priority Queue)

> C has no built-in heap — be able to write heapify / push / pop yourself.

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 703 | [Kth Largest Element in a Stream](https://leetcode.com/problems/kth-largest-element-in-a-stream/) | Easy | `N150` |  |  |
| 1046 | [Last Stone Weight](https://leetcode.com/problems/last-stone-weight/) | Easy | `N150` |  |  |
| 973 | [K Closest Points to Origin](https://leetcode.com/problems/k-closest-points-to-origin/) | Medium | `N150` |  |  |
| 215 | [Kth Largest Element in an Array](https://leetcode.com/problems/kth-largest-element-in-an-array/) | Medium | `N150` `I150` `H100` |  |  |
| 621 | [Task Scheduler](https://leetcode.com/problems/task-scheduler/) | Medium | `N150` |  |  |
| 355 | [Design Twitter](https://leetcode.com/problems/design-twitter/) | Medium | `N150` |  |  |
| 373 | [Find K Pairs With Smallest Sums](https://leetcode.com/problems/find-k-pairs-with-smallest-sums/) | Medium | `I150` |  |  |
| 1834 | [Single-Threaded CPU](https://leetcode.com/problems/single-threaded-cpu/) | Medium | `N250` |  |  |
| 767 | [Reorganize String](https://leetcode.com/problems/reorganize-string/) | Medium | `N250` |  |  |
| 1405 | [Longest Happy String](https://leetcode.com/problems/longest-happy-string/) | Medium | `N250` |  |  |
| 1094 | [Car Pooling](https://leetcode.com/problems/car-pooling/) | Medium | `N250` |  |  |
| 502 | [IPO](https://leetcode.com/problems/ipo/) | Hard | `N250` `I150` |  |  |
| 295 | [Find Median From Data Stream](https://leetcode.com/problems/find-median-from-data-stream/) | Hard | `75` `I150` `H100` |  |  |

---

# Tier 3 — If Time Permits (Rarely Asked in Embedded Interviews)

## Tree

> Almost never asked, though some candidates got BST questions; at least know traversals and BST insert / search.

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 226 | [Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/) | Easy | `75` `I150` `H100` |  |  |
| 104 | [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/) | Easy | `75` `I150` `H100` |  |  |
| 100 | [Same Tree](https://leetcode.com/problems/same-tree/) | Easy | `75` `I150` |  |  |
| 101 | [Symmetric Tree](https://leetcode.com/problems/symmetric-tree/) | Easy | `I150` `H100` |  |  |
| 543 | [Diameter of Binary Tree](https://leetcode.com/problems/diameter-of-binary-tree/) | Easy | `N150` `H100` |  |  |
| 110 | [Balanced Binary Tree](https://leetcode.com/problems/balanced-binary-tree/) | Easy | `N150` |  |  |
| 572 | [Subtree of Another Tree](https://leetcode.com/problems/subtree-of-another-tree/) | Easy | `75` |  |  |
| 112 | [Path Sum](https://leetcode.com/problems/path-sum/) | Easy | `I150` |  |  |
| 108 | [Convert Sorted Array to Binary Search Tree](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/) | Easy | `I150` `H100` |  |  |
| 530 | [Minimum Absolute Difference in BST](https://leetcode.com/problems/minimum-absolute-difference-in-bst/) | Easy | `I150` |  |  |
| 637 | [Average of Levels in Binary Tree](https://leetcode.com/problems/average-of-levels-in-binary-tree/) | Easy | `I150` |  |  |
| 222 | [Count Complete Tree Nodes](https://leetcode.com/problems/count-complete-tree-nodes/) | Easy | `I150` |  |  |
| 94 | [Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/) | Easy | `N250` `H100` |  |  |
| 144 | [Binary Tree Preorder Traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/) | Easy | `N250` |  |  |
| 145 | [Binary Tree Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/) | Easy | `N250` |  |  |
| 235 | [Lowest Common Ancestor of a Binary Search Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) | Medium | `75` |  |  |
| 236 | [Lowest Common Ancestor of a Binary Tree](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-tree/) | Medium | `I150` `H100` |  |  |
| 102 | [Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/) | Medium | `75` `I150` `H100` |  |  |
| 103 | [Binary Tree Zigzag Level Order Traversal](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/) | Medium | `I150` |  |  |
| 199 | [Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view/) | Medium | `N150` `I150` `H100` |  |  |
| 1448 | [Count Good Nodes in Binary Tree](https://leetcode.com/problems/count-good-nodes-in-binary-tree/) | Medium | `N150` |  |  |
| 98 | [Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/) | Medium | `75` `I150` `H100` |  |  |
| 230 | [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/) | Medium | `75` `I150` `H100` |  |  |
| 105 | [Construct Binary Tree From Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/) | Medium | `75` `I150` `H100` |  |  |
| 106 | [Construct Binary Tree From Inorder and Postorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/) | Medium | `I150` |  |  |
| 117 | [Populating Next Right Pointers in Each Node II](https://leetcode.com/problems/populating-next-right-pointers-in-each-node-ii/) | Medium | `I150` |  |  |
| 114 | [Flatten Binary Tree to Linked List](https://leetcode.com/problems/flatten-binary-tree-to-linked-list/) | Medium | `I150` `H100` |  |  |
| 129 | [Sum Root to Leaf Numbers](https://leetcode.com/problems/sum-root-to-leaf-numbers/) | Medium | `I150` |  |  |
| 173 | [Binary Search Tree Iterator](https://leetcode.com/problems/binary-search-tree-iterator/) | Medium | `I150` |  |  |
| 427 | [Construct Quad Tree](https://leetcode.com/problems/construct-quad-tree/) | Medium | `N250` `I150` |  |  |
| 701 | [Insert into a Binary Search Tree](https://leetcode.com/problems/insert-into-a-binary-search-tree/) | Medium | `N250` |  |  |
| 450 | [Delete Node in a BST](https://leetcode.com/problems/delete-node-in-a-bst/) | Medium | `N250` |  |  |
| 337 | [House Robber III](https://leetcode.com/problems/house-robber-iii/) | Medium | `N250` |  |  |
| 1325 | [Delete Leaves With a Given Value](https://leetcode.com/problems/delete-leaves-with-a-given-value/) | Medium | `N250` |  |  |
| 437 | [Path Sum III](https://leetcode.com/problems/path-sum-iii/) | Medium | `H100` |  |  |
| 124 | [Binary Tree Maximum Path Sum](https://leetcode.com/problems/binary-tree-maximum-path-sum/) | Hard | `75` `I150` `H100` |  |  |
| 297 | [Serialize and Deserialize Binary Tree](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/) | Hard | `75` |  |  |

## Trie

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 208 | [Implement Trie (Prefix Tree)](https://leetcode.com/problems/implement-trie-prefix-tree/) | Medium | `75` `I150` `H100` |  |  |
| 211 | [Design Add and Search Words Data Structure](https://leetcode.com/problems/design-add-and-search-words-data-structure/) | Medium | `75` `I150` |  |  |
| 2707 | [Extra Characters in a String](https://leetcode.com/problems/extra-characters-in-a-string/) | Medium | `N250` |  |  |
| 212 | [Word Search II](https://leetcode.com/problems/word-search-ii/) | Hard | `75` `I150` |  |  |

## Backtracking

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 1863 | [Sum of All Subset XOR Totals](https://leetcode.com/problems/sum-of-all-subset-xor-totals/) | Easy | `N250` |  |  |
| 78 | [Subsets](https://leetcode.com/problems/subsets/) | Medium | `N150` `H100` |  |  |
| 77 | [Combinations](https://leetcode.com/problems/combinations/) | Medium | `N250` `I150` |  |  |
| 39 | [Combination Sum](https://leetcode.com/problems/combination-sum/) | Medium | `N75` `I150` `H100` |  |  |
| 40 | [Combination Sum II](https://leetcode.com/problems/combination-sum-ii/) | Medium | `N150` |  |  |
| 46 | [Permutations](https://leetcode.com/problems/permutations/) | Medium | `N150` `I150` `H100` |  |  |
| 90 | [Subsets II](https://leetcode.com/problems/subsets-ii/) | Medium | `N150` |  |  |
| 79 | [Word Search](https://leetcode.com/problems/word-search/) | Medium | `75` `I150` `H100` |  |  |
| 131 | [Palindrome Partitioning](https://leetcode.com/problems/palindrome-partitioning/) | Medium | `N150` `H100` |  |  |
| 17 | [Letter Combinations of a Phone Number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/) | Medium | `N150` `I150` `H100` |  |  |
| 47 | [Permutations II](https://leetcode.com/problems/permutations-ii/) | Medium | `N250` |  |  |
| 473 | [Matchsticks to Square](https://leetcode.com/problems/matchsticks-to-square/) | Medium | `N250` |  |  |
| 698 | [Partition to K Equal Sum Subsets](https://leetcode.com/problems/partition-to-k-equal-sum-subsets/) | Medium | `N250` |  |  |
| 51 | [N-Queens](https://leetcode.com/problems/n-queens/) | Hard | `N150` `H100` |  |  |
| 52 | [N-Queens II](https://leetcode.com/problems/n-queens-ii/) | Hard | `N250` `I150` |  |  |
| 140 | [Word Break II](https://leetcode.com/problems/word-break-ii/) | Hard | `N250` |  |  |

## Graph

> Only seen when redirected to an SDE interview (topological sort, 207 / 210).

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 463 | [Island Perimeter](https://leetcode.com/problems/island-perimeter/) | Easy | `N250` |  |  |
| 953 | [Verifying an Alien Dictionary](https://leetcode.com/problems/verifying-an-alien-dictionary/) | Easy | `N250` |  |  |
| 997 | [Find the Town Judge](https://leetcode.com/problems/find-the-town-judge/) | Easy | `N250` |  |  |
| 200 | [Number of Islands](https://leetcode.com/problems/number-of-islands/) | Medium | `75` `I150` `H100` |  |  |
| 695 | [Max Area of Island](https://leetcode.com/problems/max-area-of-island/) | Medium | `N150` |  |  |
| 133 | [Clone Graph](https://leetcode.com/problems/clone-graph/) | Medium | `75` `I150` |  |  |
| 286 | [Walls and Gates](https://leetcode.com/problems/walls-and-gates/) 🔒 | Medium | `N150` |  |  |
| 994 | [Rotting Oranges](https://leetcode.com/problems/rotting-oranges/) | Medium | `N150` `H100` |  |  |
| 417 | [Pacific Atlantic Water Flow](https://leetcode.com/problems/pacific-atlantic-water-flow/) | Medium | `75` |  |  |
| 130 | [Surrounded Regions](https://leetcode.com/problems/surrounded-regions/) | Medium | `N150` `I150` |  |  |
| 207 | [Course Schedule](https://leetcode.com/problems/course-schedule/) | Medium | `75` `I150` `H100` |  |  |
| 210 | [Course Schedule II](https://leetcode.com/problems/course-schedule-ii/) | Medium | `N150` `I150` |  |  |
| 684 | [Redundant Connection](https://leetcode.com/problems/redundant-connection/) | Medium | `N150` |  |  |
| 323 | [Number of Connected Components in an Undirected Graph](https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/) 🔒 | Medium | `75` |  |  |
| 261 | [Graph Valid Tree](https://leetcode.com/problems/graph-valid-tree/) 🔒 | Medium | `75` |  |  |
| 399 | [Evaluate Division](https://leetcode.com/problems/evaluate-division/) | Medium | `N250` `I150` |  |  |
| 909 | [Snakes and Ladders](https://leetcode.com/problems/snakes-and-ladders/) | Medium | `I150` |  |  |
| 433 | [Minimum Genetic Mutation](https://leetcode.com/problems/minimum-genetic-mutation/) | Medium | `I150` |  |  |
| 752 | [Open the Lock](https://leetcode.com/problems/open-the-lock/) | Medium | `N250` |  |  |
| 1462 | [Course Schedule IV](https://leetcode.com/problems/course-schedule-iv/) | Medium | `N250` |  |  |
| 721 | [Accounts Merge](https://leetcode.com/problems/accounts-merge/) | Medium | `N250` |  |  |
| 310 | [Minimum Height Trees](https://leetcode.com/problems/minimum-height-trees/) | Medium | `N250` |  |  |
| 127 | [Word Ladder](https://leetcode.com/problems/word-ladder/) | Hard | `N150` `I150` |  |  |

## Advanced Graph

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 743 | [Network Delay Time](https://leetcode.com/problems/network-delay-time/) | Medium | `N150` |  |  |
| 1584 | [Min Cost to Connect All Points](https://leetcode.com/problems/min-cost-to-connect-all-points/) | Medium | `N150` |  |  |
| 787 | [Cheapest Flights Within K Stops](https://leetcode.com/problems/cheapest-flights-within-k-stops/) | Medium | `N150` |  |  |
| 1631 | [Path With Minimum Effort](https://leetcode.com/problems/path-with-minimum-effort/) | Medium | `N250` |  |  |
| 332 | [Reconstruct Itinerary](https://leetcode.com/problems/reconstruct-itinerary/) | Hard | `N150` |  |  |
| 778 | [Swim in Rising Water](https://leetcode.com/problems/swim-in-rising-water/) | Hard | `N150` |  |  |
| 269 | [Alien Dictionary](https://leetcode.com/problems/alien-dictionary/) 🔒 | Hard | `75` |  |  |
| 1489 | [Find Critical and Pseudo-Critical Edges in Minimum Spanning Tree](https://leetcode.com/problems/find-critical-and-pseudo-critical-edges-in-minimum-spanning-tree/) | Hard | `N250` |  |  |
| 2392 | [Build a Matrix With Conditions](https://leetcode.com/problems/build-a-matrix-with-conditions/) | Hard | `N250` |  |  |
| 2709 | [Greatest Common Divisor Traversal](https://leetcode.com/problems/greatest-common-divisor-traversal/) | Hard | `N250` |  |  |

## Greedy

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 860 | [Lemonade Change](https://leetcode.com/problems/lemonade-change/) | Easy | `N250` |  |  |
| 53 | [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/) | Medium | `75` `I150` `H100` |  |  |
| 918 | [Maximum Sum Circular Subarray](https://leetcode.com/problems/maximum-sum-circular-subarray/) | Medium | `N250` `I150` |  |  |
| 122 | [Best Time to Buy and Sell Stock II](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii/) | Medium | `N250` `I150` |  |  |
| 55 | [Jump Game](https://leetcode.com/problems/jump-game/) | Medium | `75` `I150` `H100` |  |  |
| 45 | [Jump Game II](https://leetcode.com/problems/jump-game-ii/) | Medium | `N150` `I150` `H100` |  |  |
| 134 | [Gas Station](https://leetcode.com/problems/gas-station/) | Medium | `N150` `I150` |  |  |
| 846 | [Hand of Straights](https://leetcode.com/problems/hand-of-straights/) | Medium | `N150` |  |  |
| 1899 | [Merge Triplets to Form Target Triplet](https://leetcode.com/problems/merge-triplets-to-form-target-triplet/) | Medium | `N150` |  |  |
| 763 | [Partition Labels](https://leetcode.com/problems/partition-labels/) | Medium | `N150` `H100` |  |  |
| 678 | [Valid Parenthesis String](https://leetcode.com/problems/valid-parenthesis-string/) | Medium | `N150` |  |  |
| 978 | [Longest Turbulent Subarray](https://leetcode.com/problems/longest-turbulent-subarray/) | Medium | `N250` |  |  |
| 1871 | [Jump Game VII](https://leetcode.com/problems/jump-game-vii/) | Medium | `N250` |  |  |
| 649 | [Dota2 Senate](https://leetcode.com/problems/dota2-senate/) | Medium | `N250` |  |  |
| 135 | [Candy](https://leetcode.com/problems/candy/) | Hard | `N250` `I150` |  |  |

## 1-D Dynamic Programming

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 70 | [Climbing Stairs](https://leetcode.com/problems/climbing-stairs/) | Easy | `75` `I150` `H100` |  |  |
| 746 | [Min Cost Climbing Stairs](https://leetcode.com/problems/min-cost-climbing-stairs/) | Easy | `N150` |  |  |
| 1137 | [N-th Tribonacci Number](https://leetcode.com/problems/n-th-tribonacci-number/) | Easy | `N250` |  |  |
| 198 | [House Robber](https://leetcode.com/problems/house-robber/) | Medium | `75` `I150` `H100` |  |  |
| 213 | [House Robber II](https://leetcode.com/problems/house-robber-ii/) | Medium | `75` |  |  |
| 5 | [Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/) | Medium | `75` `I150` `H100` |  |  |
| 647 | [Palindromic Substrings](https://leetcode.com/problems/palindromic-substrings/) | Medium | `75` |  |  |
| 91 | [Decode Ways](https://leetcode.com/problems/decode-ways/) | Medium | `75` |  |  |
| 322 | [Coin Change](https://leetcode.com/problems/coin-change/) | Medium | `75` `I150` `H100` |  |  |
| 152 | [Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/) | Medium | `75` `H100` |  |  |
| 139 | [Word Break](https://leetcode.com/problems/word-break/) | Medium | `75` `I150` `H100` |  |  |
| 300 | [Longest Increasing Subsequence](https://leetcode.com/problems/longest-increasing-subsequence/) | Medium | `75` `I150` `H100` |  |  |
| 416 | [Partition Equal Subset Sum](https://leetcode.com/problems/partition-equal-subset-sum/) | Medium | `N150` `H100` |  |  |
| 377 | [Combination Sum IV](https://leetcode.com/problems/combination-sum-iv/) | Medium | `B75` `N250` |  |  |
| 279 | [Perfect Squares](https://leetcode.com/problems/perfect-squares/) | Medium | `N250` `H100` |  |  |
| 343 | [Integer Break](https://leetcode.com/problems/integer-break/) | Medium | `N250` |  |  |
| 1406 | [Stone Game III](https://leetcode.com/problems/stone-game-iii/) | Hard | `N250` |  |  |

## 2-D Dynamic Programming

| # | Title | Difficulty | Source | ⭐ | Date |
|---|---|---|---|---|---|
| 62 | [Unique Paths](https://leetcode.com/problems/unique-paths/) | Medium | `75` `H100` |  |  |
| 63 | [Unique Paths II](https://leetcode.com/problems/unique-paths-ii/) | Medium | `N250` `I150` |  |  |
| 64 | [Minimum Path Sum](https://leetcode.com/problems/minimum-path-sum/) | Medium | `N250` `I150` `H100` |  |  |
| 120 | [Triangle](https://leetcode.com/problems/triangle/) | Medium | `I150` |  |  |
| 221 | [Maximal Square](https://leetcode.com/problems/maximal-square/) | Medium | `I150` |  |  |
| 1143 | [Longest Common Subsequence](https://leetcode.com/problems/longest-common-subsequence/) | Medium | `75` `H100` |  |  |
| 309 | [Best Time to Buy and Sell Stock With Cooldown](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/) | Medium | `N150` |  |  |
| 518 | [Coin Change II](https://leetcode.com/problems/coin-change-ii/) | Medium | `N150` |  |  |
| 494 | [Target Sum](https://leetcode.com/problems/target-sum/) | Medium | `N150` |  |  |
| 97 | [Interleaving String](https://leetcode.com/problems/interleaving-string/) | Medium | `N150` `I150` |  |  |
| 72 | [Edit Distance](https://leetcode.com/problems/edit-distance/) | Medium | `N150` `I150` `H100` |  |  |
| 877 | [Stone Game](https://leetcode.com/problems/stone-game/) | Medium | `N250` |  |  |
| 1049 | [Last Stone Weight II](https://leetcode.com/problems/last-stone-weight-ii/) | Medium | `N250` |  |  |
| 1140 | [Stone Game II](https://leetcode.com/problems/stone-game-ii/) | Medium | `N250` |  |  |
| 329 | [Longest Increasing Path in a Matrix](https://leetcode.com/problems/longest-increasing-path-in-a-matrix/) | Hard | `N150` |  |  |
| 115 | [Distinct Subsequences](https://leetcode.com/problems/distinct-subsequences/) | Hard | `N150` |  |  |
| 123 | [Best Time to Buy and Sell Stock III](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii/) | Hard | `I150` |  |  |
| 188 | [Best Time to Buy and Sell Stock IV](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv/) | Hard | `I150` |  |  |
| 312 | [Burst Balloons](https://leetcode.com/problems/burst-balloons/) | Hard | `N150` |  |  |
| 10 | [Regular Expression Matching](https://leetcode.com/problems/regular-expression-matching/) | Hard | `N150` |  |  |
