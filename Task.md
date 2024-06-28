
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
### [Palindrome Number](https://leetcode.com/problems/palindrome-number/description/)
![image](https://github.com/Balekundribhakti/leetcode-python-easy/assets/166371317/821f8ed9-cd3c-479a-8408-54fb03c4f583)

### Answer
```
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        if (x<0):
            return False
        i = x
        s = 0
        while(i > 0):
            d = i % 10
            s = s * 10 + d
            i = i / 10
        if (x == s):
            return True
        return False
        
```
### Explanation
Certainly! Let's break down the provided code in simple terms:

```python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        # Check if the number is negative
        if (x < 0):
            return False
        
        # Initialize variables
        i = x  # i will be used to manipulate the number
        s = 0  # s will store the reversed number
        
        # Reverse the number
        while (i > 0):
            d = i % 10       # Get the last digit of i
            s = s * 10 + d   # Append the last digit to s in reverse order
            i = i // 10      # Remove the last digit from i
        
        # Check if the original number x is equal to the reversed number s
        if (x == s):
            return True
        else:
            return False
```

### Explanation:

1. **Function Definition**: The code defines a class `Solution` with a method `isPalindrome` that checks if a given integer `x` is a palindrome.

2. **Handling Negative Numbers**: 
   - If `x` is negative (`x < 0`), it immediately returns `False`. Palindromes are typically considered only for non-negative integers.

3. **Reversing the Number**:
   - Initialize `i` with the value of `x`. `i` is used to iterate through and manipulate the number.
   - Initialize `s` to `0`. `s` will store the reversed version of `x`.
   - Using a `while` loop, continue until `i` is greater than `0`.
   - Inside the loop:
     - `d = i % 10`: Obtain the last digit of `i`.
     - `s = s * 10 + d`: Build the reversed number `s` by appending the last digit `d` in reverse order.
     - `i = i // 10`: Remove the last digit from `i` using integer division to prepare for the next iteration.

4. **Comparison**:
   - After exiting the loop, compare the original number `x` with the reversed number `s`.
   - If they are equal (`x == s`), return `True`, indicating `x` is a palindrome.
   - Otherwise, return `False`.

### Example:
- For `x = 121`:
  - Initial check: `x` is not negative, so continue.
  - During the loop:
    - `i` becomes `121`, `12`, `1` and eventually `0`.
    - `s` accumulates digits to become `121`, `12`, `1` (reversed).
  - After the loop:
    - Check `121 == 121`, which is `True`.

- For `x = 123`:
  - Initial check: `x` is not negative, so continue.
  - During the loop:
    - `i` becomes `123`, `12`, `1` and eventually `0`.
    - `s` accumulates digits to become `321`.
  - After the loop:
    - Check `123 == 321`, which is `False`.

This function effectively determines if `x` is a palindrome by reversing its digits and comparing the reversed version to the original.


## Question 3
### [Roman to Integer](https://leetcode.com/problems/roman-to-integer/description/)
![image](https://github.com/Balekundribhakti/leetcode-python-easy/assets/166371317/84c34f95-ea56-4725-9528-c33e66714e65)


### Answer
```
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        symbol_hash = {
            'I': 1,
            'IV': 4,
            'V': 5,
            'IX': 9,
            'X': 10,
            'XL': 40,
            'L': 50,
            'XC': 90,
            'C': 100,
            'CD': 400,
            'D': 500,
            'CM': 900,
            'M': 1000,
        }

        integer = 0
        i = 0
        while i < len(s):
            two_val = symbol_hash.get(s[i:i + 2])
            if two_val:
                integer += two_val
                i += 2
            else:
                integer += symbol_hash[s[i]]
                i += 1
        return integer

```
### Explanation
