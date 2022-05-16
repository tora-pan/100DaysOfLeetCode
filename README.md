# 100 days of leetcode

## Why am i doing this?

Now that i am officially a fulltime software engineer, i thought it was about time that i start diving deeper into data structures and algorithms.

I did a quick search on google and multiple sources pointed toward something known as the [blind 75](https://www.teamblind.com/post/new-year-gift---curated-list-of-top-75-leetcode-questions-to-save-your-time-oam1oreu) .

This list was curated by a facebook tech lead to help all of the "time-constrained engineers" out there looking for a job.

These questions teach you the core concepts and techniques for each category/type of problem. many of the leetcode type interview questions that you will most definitely run into when trying to break into "big tech" are either directly chosen from this list or a combination/mashup of a few of them.

## Categories

1. [array](#array)
2. [binary](#binary)
3. [dynamic programming](#dynamic-programming)
4. [graph](#graph)
5. [interval](#interval)
6. [linked list](#linked-list)
7. [matrix](#matrix)
8. [string](#string)
9. [tree](#tree)
10. [heap](#heap)
  
[Common Patterns](#patterns)

<hr>

## Array

<details>
<summary>two sum</summary>

### prompt:

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

### my solution:

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
  //set up results object
  results = {};

  for (let i = 0; i < nums.length; i++) {
    // check to see if complement exists
    let complement = target - nums[i];
    if (results.hasOwnProperty(complement)) {
      return [results[complement], i];
    }
    results[nums[i]] = i;
  }

  return null;
};
```

### notes:

The _hasOwnProperty()_ method returns a boolean indicating whether the object has the specified property as its own property (as opposed to inheriting it).

[link to leetcode](https://leetcode.com/problems/two-sum/)

</details>

<details>
<summary>best time to buy and sell stock</summary>

### prompt:

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

### my solution:

```js
// My initial naive solution timed out.
/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function (prices) {
  let buyPrice = 0;
  let sellPrice = 0;
  let profit = 0;

  for (let i = 0; i < prices.length; i++) {
    buyPrice = prices[i];
    for (let j = i + 1; j < prices.length; j++) {
      if (prices[j] > buyPrice) {
        sellPrice = prices[j];
        if (sellPrice - buyPrice > profit) {
          profit = sellPrice - buyPrice;
        }
      }
    }
  }
  return profit;
};

// After checking the discussion, I came to this solution.

/**
 * @param {number[]} prices
 * @return {number}
 */
var maxProfit = function (prices) {
  // trying sliding window

  let buy = 0;
  let sell = 1;
  let profit = 0;

  for (let i = 0; i < prices.length - 1; i++) {
    if (prices[sell] - prices[buy] > profit) {
      profit = prices[sell] - prices[buy];
    }

    if (prices[buy] > prices[sell]) {
      buy = sell;
    }
    sell = sell + 1;
  }
  return profit;
};
```

### notes:

The condition to use the sliding window technique is that the problem asks to find the maximum (or minimum) value for a function that calculates the answer repeatedly for a set of ranges from an array.

[link to leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

</details>

<details>
<summary>contains duplicate</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/contains-duplicate/)

</details>

<details>
<summary>product of array except self</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/product-of-array-except-self/)

</details>

<details>
<summary>maximum subarray</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/maximum-subarray/)

</details>

<details>
<summary>maximum product subarray</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/maximum-product-subarray/)

</details>

<details>
<summary>find minimum in rotated sorted array</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)

</details>

<details>
<summary>search in rotated sorted array</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/search-in-rotated-sorted-array/)

</details>

<details>
<summary>3sum</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/3sum/)

</details>

<details>
<summary>container with most water</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/container-with-most-water/)

</details>

<hr>

## Binary

<details>
<summary>sum of two integers</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/sum-of-two-integers/)

</details>

<details>
<summary>number of 1 bits</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/number-of-1-bits/)

</details>

<details>
<summary>counting bits</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/counting-bits/)

</details>

<details>
<summary>missing number</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/missing-number/)

</details>

<details>
<summary>reverse bits</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/reverse-bits/)

</details>

<hr>

## Dynamic programming

<details>
<summary>climbing stairs</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/climbing-stairs/)

</details>

<details>
<summary>coin change</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/coin-change/)

</details>

<details>
<summary>longest increasing subsequence</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/longest-increasing-subsequence/)

</details>

<details>
<summary>longest common subsequence</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode]()

</details>

<details>
<summary>word break problem</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/word-break/)

</details>

<details>
<summary>combination sum</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/combination-sum-iv/)

</details>

<details>
<summary>house robber</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/house-robber/)

</details>

<details>
<summary>house robber ii</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/house-robber-ii/)

</details>

<details>
<summary>decode ways</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/decode-ways/)

</details>

<details>
<summary>unique paths</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/unique-paths/)

</details>

<details>
<summary>Jump Game</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/jump-game/)

</details>

<hr>

## Graph

<details>
<summary>Clone Graph</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/clone-graph/)

</details>

<details>
<summary>Course Schedule</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/course-schedule/)

</details>

<details>
<summary>Pacific Atlantic Water Flow</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/pacific-atlantic-water-flow/)

</details>

<details>
<summary>Number of Islands</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/number-of-islands/)

</details>

<details>
<summary>Longest Consecutive Sequence</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/longest-consecutive-sequence/)

</details>

<details>
<summary>Alien Dictionary</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/alien-dictionary/)

</details>

<details>
<summary>Graph Valid Tree</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/graph-valid-tree/)

</details>

<details>
<summary>Number of Connected Components in an Undirected Graph</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/number-of-connected-components-in-an-undirected-graph/)

</details>

<hr>

## Interval

<details>
<summary>Insert Interval</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/insert-interval/)

</details>

<details>
<summary>Merge Intervals</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/merge-intervals/)

</details>

<details>
<summary>Non-overlapping Intervals</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/non-overlapping-intervals/)

</details>

<details>
<summary>Meeting Rooms</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/meeting-rooms/)

</details>

<details>
<summary>Meeting Rooms II</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/meeting-rooms-ii/)

</details>

<hr>

## Linked list

<details>
<summary>Reverse a Linked List</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/reverse-linked-list/)

</details>

<details>
<summary>Detect Cycle in a Linked List</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/linked-list-cycle/)

</details>

<details>
<summary>Merge Two Sorted Lists</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/merge-two-sorted-lists/)

</details>

<details>
<summary>Merge K Sorted Lists</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/merge-k-sorted-lists/)

</details>

<details>
<summary>Remove Nth Node From End of List </summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

</details>

<details>
<summary>Reorder List</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/reorder-list/)

</details>

<hr>

## Matrix

<details>
<summary>Set Matrix Zeros</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/set-matrix-zeroes/)

</details>

<details>
<summary>Spiral Matrix</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/spiral-matrix/)

</details>

<details>
<summary>Rotate Image</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/rotate-image/)

</details>

<details>
<summary>Word Search</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/word-search/)

</details>

<hr>

## String

<details>
<summary>Longest Substring Without Repeating Characters</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

</details>

<details>
<summary>Longest Repeating Character Replacement</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/longest-repeating-character-replacement/)

</details>

<details>
<summary>Minimum Window Substring</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/minimum-window-substring/)

</details>

<details>
<summary>Valid Anagram</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/valid-anagram/)

</details>

<details>
<summary>Group Anagrams</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/group-anagrams/)

</details>

<details>
<summary>Valid Parentheses</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/valid-parentheses/)

</details>

<details>
<summary>Valid Palindrome</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/valid-palindrome/)

</details>

<details>
<summary>Longest Palindromic Substring</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/longest-palindromic-substring/)

</details>

<details>
<summary>Palindromic Substrings</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/palindromic-substrings/)

</details>

<details>
<summary>Encode and Decode Strings</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/encode-and-decode-strings/)

</details>

<hr>

## Tree

<details>
<summary>MaximumDepth of Binary Tree</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

</details>

<details>
<summary>Same Tree</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/same-tree/)

</details>

<details>
<summary>Invert/Flip Binary Tree</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/invert-binary-tree/)

</details>

<details>
<summary>Binary Tree Maximum Path Sum</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/binary-tree-maximum-path-sum/)

</details>

<details>
<summary>Binary Tree Level Order Traversal</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/binary-tree-level-order-traversal/)

</details>

<details>
<summary>Serialize and Deserialize Binary Tree</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/serialize-and-deserialize-binary-tree/)

</details>

<details>
<summary>Subtree of Another Tree</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/subtree-of-another-tree/)

</details>

<details>
<summary>Construct Binary Tree from Preorder and Inorder Traversal</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)

</details>

<details>
<summary>Validate Binary Search Tree</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/validate-binary-search-tree/)

</details>

<details>
<summary>Kth Smallest Element in a BST</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)

</details>

<details>
<summary>Lowest Common Ancestor of BST</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/lowest-common-ancestor-of-a-binary-search-tree/)

</details>

<details>
<summary>Implement Trie (Prefix Tree)</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/implement-trie-prefix-tree/)

</details>

<details>
<summary>Add and Search Word</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/add-and-search-word-data-structure-design/)

</details>

<details>
<summary>Word Search II</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/word-search-ii/)

</details>

<hr>

## Heap

<details>
<summary>Merge K Sorted Lists</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/merge-k-sorted-lists/)

</details>

<details>
<summary>Top K Frequent Elements</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/top-k-frequent-elements/)

</details>

<details>
<summary>Find Median from Data Stream</summary>

### prompt:

### my solution:

```js
// insert solution here
```

### notes:

[link to leetcode](https://leetcode.com/problems/find-median-from-data-stream/)

</details>
  
<hr>

## Patterns  
- Sliding Window
- Two Pointers or Iterators
- Fast and Slow Pointers
- Merge Intervals
- Cyclic Sort
- In-Place Reversal of - Linked List
- Tree BFS
- Tree DFS
- Two Heaps
- Subsets
- Modified Binary Search
- Top K Elements
- K-Way Merge 
- Topological Sort