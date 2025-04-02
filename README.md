# Two Sum

## Problem Statement
Given an array of integers `nums` and an integer `target`, return **indices** of the two numbers such that they add up to `target`.

### Constraints
- Each input has **exactly one** solution.
- The same element **cannot be used twice**.
- The answer can be returned in **any order**.

## Example

### Example 1:
**Input:**
```java
nums = [2,7,11,15], target = 9
```
**Output:**
```java
[0,1]
```
**Explanation:** `nums[0] + nums[1] == 9`, so we return `[0, 1]`.

### Example 2:
**Input:**
```java
nums = [3,2,4], target = 6
```
**Output:**
```java
[1,2]
```

### Example 3:
**Input:**
```java
nums = [3,3], target = 6
```
**Output:**
```java
[0,1]
```

## Solution
This solution uses a **HashMap** to store the required difference (`target - nums[i]`) as a key and the index `i` as a value. As we iterate through `nums`, we check if `nums[i]` exists in the HashMap. If it does, we return the stored index along with `i`. Otherwise, we store the difference and continue.

### Code Implementation
```java
import java.util.HashMap;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer, Integer> map = new HashMap<Integer, Integer>();

        for (int i = 0 ; i < nums.length; i++) {
            if (map.containsKey(nums[i])) {
                return new int[] { map.get(nums[i]), i };
            } else {
                map.put(target - nums[i], i);
            }
        }
        
        return new int[] {};
    }
}
```

## Complexity Analysis
- **Time Complexity:** `O(n)` - We iterate through `nums` once.
- **Space Complexity:** `O(n)` - We store at most `n` elements in the HashMap.



