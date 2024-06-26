
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
