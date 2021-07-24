# LeetCode Solutions
My solutions to LeetCode problems.
## Easy Array Problems


Given a zero-based permutation nums (0-indexed), build an array ans of the same length where ans[i] = nums[nums[i]] for each 0 <= i < nums.length and return it.

A zero-based permutation nums is an array of distinct integers from 0 to nums.length - 1 (inclusive).

### Problem 1920 Build Array from Permutation
#### Description
##### Example 1:
```
Input: nums = [0,2,1,5,3,4]
Output: [0,1,2,4,5,3]
Explanation: The array ans is built as follows: 
ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
    = [nums[0], nums[2], nums[1], nums[5], nums[3], nums[4]]
    = [0,1,2,4,5,3]
```
##### Example 2:
```
Input: nums = [5,0,1,2,3,4]
Output: [4,5,0,1,2,3]
Explanation: The array ans is built as follows:
ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
    = [nums[5], nums[0], nums[1], nums[2], nums[3], nums[4]]
    = [4,5,0,1,2,3]
```

Constraints:

1 <= nums.length <= 1000
0 <= nums[i] < nums.length
The elements in nums are distinct.
 

Follow-up: Can you solve it without using an extra space (i.e., O(1) memory)?
#### My solution
```
class Solution:
    def buildArray(self, nums: List[int]) -> List[int]:
        ans=[]
        for i in nums:
            ans.append(nums[i])
        return ans
```

### Problem 1480 Running Sum of 1d Array
#### Description
Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.

##### Example 1:
```
Input: nums = [1,2,3,4]
Output: [1,3,6,10]
Explanation: Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].
```
##### Example 2:
```
Input: nums = [1,1,1,1,1]
Output: [1,2,3,4,5]
Explanation: Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].
```
##### Example 3:
```
Input: nums = [3,1,2,10,1]
Output: [3,4,6,16,17]
```

Constraints:

1 <= nums.length <= 1000
-10^6 <= nums[i] <= 10^6


#### My solution
```
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        totalsum=0
        ans=[]
        for i in nums:
            totalsum+=i
            ans.append(totalsum)
        return ans
```
- Runtime: 64 ms, faster than 12.69% of Python3 online submissions for Running Sum of 1d Array.
- Memory Usage: 14.2 MB, less than 97.71% of Python3 online submissions for Running Sum of 1d Array.

#### Solution with accumulate
```
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        return accumulate(nums)
```
