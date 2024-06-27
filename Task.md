
## Question 1
### [Two Sum](https://leetcode.com/problems/two-sum/)
![image](https://github.com/Balekundribhakti/leetcode-python-easy/assets/166371317/a63e84ea-46b2-4e30-b038-eef7936aee66)
### Answer
```
class Solution(object):
    def twoSum(self, nums, target):
        hash_map = {}

        for i,num in enumerate(nums):
            if target - num in hash_map:
                return [hash_map[target-num],i]
            hash_map[num] = i

        return []
    
        
```
### Explanation
Sure, let's break down the `twoSum` function from the provided Python code:

```python
class Solution(object):
    def twoSum(self, nums, target):
        hash_map = {}

        # Iterate through each number in the nums list along with its index
        for i, num in enumerate(nums):
            # Calculate the complement needed to achieve the target sum
            complement = target - num
            
            # Check if the complement (target - num) is already in the hash_map
            if complement in hash_map:
                # If found, return the indices of the two numbers that add up to the target
                return [hash_map[complement], i]
            
            # If the complement is not found in the hash_map, store the current number
            # along with its index in the hash_map for future reference
            hash_map[num] = i

        # If no valid pairs are found, return an empty list
        return []
```

### Explanation:

1. **Initialization**:
   - `hash_map = {}`: This initializes an empty dictionary `hash_map` where we will store numbers from the `nums` list along with their indices.

2. **Iteration through `nums`**:
   - `for i, num in enumerate(nums):` This loop iterates through each element (`num`) in the `nums` list, along with its index (`i`).

3. **Finding the Complement**:
   - `complement = target - num`: For each `num`, calculate its complement which is `target - num`. This is the number we need to find in `nums` to make up the `target`.

4. **Checking in `hash_map`**:
   - `if complement in hash_map:` Checks if the `complement` (the number needed to reach `target`) is already in `hash_map`.
     - If it is found (`if` condition is true), it means we have already encountered the number that sums up to `target` with the current `num`. So, we return the indices `[hash_map[complement], i]`, where `hash_map[complement]` gives the index of the previously stored number and `i` gives the index of the current number.

5. **Storing in `hash_map`**:
   - `hash_map[num] = i`: If the `complement` is not found in `hash_map`, store the current `num` in `hash_map` with its index `i`.

6. **Return**:
   - If no two numbers are found that add up to `target`, the function returns an empty list `[]`.



## Question 2
![image](https://github.com/Balekundribhakti/leetcode-python-easy/assets/166371317/821f8ed9-cd3c-479a-8408-54fb03c4f583)

### Answer
```

```
### Explanation
