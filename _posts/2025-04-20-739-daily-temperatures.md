---
title: Leetcode 739 - Daily Temperatures
date: 2025-04-20 10:25:00 +0530
categories: [leetcode, stack]
tags: [leetcode]
---

# Leetcode 739 - Daily Temperatures

## Intuition
1. Need to find next maximum
2. This operation requires just one element in consideration, moreover we need to remember previous element in order to make the decision
   3. This forms the basis of using stack since only last element is required.


## Logic
1. Loop for all elements
2. Check if current element is greater than stack's peeked element, if yes add into result array
   3. if not, persist the element and index in stack

## _Notes_
1. New element in consideration, via loop increment will pop all the elements less than it, then it'll make it's entry into the stack(while loop)

## Code

<iframe src="https://github.com/vkku/LeetCode/blob/b4d5da6fce0d696b5328a8f00eb01aafe6718b44/src/main/java/me/vkku/stack/Daily_Temperature_739.java" width="100%" height="500px" style="border:none;"></iframe>
