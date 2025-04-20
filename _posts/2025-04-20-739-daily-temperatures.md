---
title: Leetcode 739
date: 2025-04-20 10:25:00 +0530
categories: [leetcode, stack]
tags: [leetcode]
---

# Daily Temperatures

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

```dtd
public class Daily_Temperature_739 {
    public int[] dailyTemperatures(int[] temperatures) {
    Stack<List<Integer>> temperatureIndexedStack = new Stack<>();
    int[] result =  new int[temperatures.length];
    for(int i = 0 ; i < temperatures.length ; i++){
    while(!temperatureIndexedStack.isEmpty() && temperatures[i] > temperatureIndexedStack.peek().get(0)){
    var element = temperatureIndexedStack.pop();
    Integer index = element.get(1);
    result[index] = i - index;
    }
    temperatureIndexedStack.add(List.of(temperatures[i], i));
    }
    return result;
    }
  
    @Test
    public void driver() {
    Daily_Temperature_739_Revision dt = new Daily_Temperature_739_Revision();
    System.out.println(Arrays.toString(dt.dailyTemperatures(new int[]{73, 74, 75, 71, 69, 72, 76, 73})));   //[1, 1, 4, 2, 1, 1, 0, 0]
    }
  }
```
