# LeetCode Solutions
My solutions to LeetCode problems.
## Easy array problems

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
