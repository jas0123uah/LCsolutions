# LeetCode Solutions
My solutions to LeetCode problems.
## Easy Array Problems


Given a zero-based permutation nums (0-indexed), build an array ans of the same length where ans[i] = nums[nums[i]] for each 0 <= i < nums.length and return it.

A zero-based permutation nums is an array of distinct integers from 0 to nums.length - 1 (inclusive).

### Problem 1920. Build Array from Permutation
Given a zero-based permutation `nums` (<b>0-indexed</b>), build an array `ans` of the same length where `ans[i] = nums[nums[i]]` for each `0 <= i < nums.length` and return it.

A <b>>zero-based permutation</b> `nums` is an array of <b>distinct</b> integers from 0 to nums.length - 1 (<b>inclusive</b>).
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

- `1 <= nums.length <= 1000`
- `0 <= nums[i] < nums.length`
- `The elements in nums are distinct.`
 

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

### 1672. Richest Customer Wealth
#### Description
You are given an `m x n` integer grid `accounts` where `accounts[i][j]` is the amount of money the `i​​​​​​​​​​​th`​​​​ customer has in the `j​​​​​​​​​​​th​​​​` bank. Return the wealth that the richest customer has.

A customer's wealth is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum wealth.

##### Example 1:
```
Input: accounts = [[1,2,3],[3,2,1]]
Output: 6
Explanation:
1st customer has wealth = 1 + 2 + 3 = 6
2nd customer has wealth = 3 + 2 + 1 = 6
Both customers are considered the richest with a wealth of 6 each, so return 6.
```
##### Example 2:
```
Input: accounts = [[1,5],[7,3],[3,5]]
Output: 10
Explanation: 
1st customer has wealth = 6
2nd customer has wealth = 10 
3rd customer has wealth = 8
The 2nd customer is the richest with a wealth of 10.
```
##### Example 3:
```
Input: accounts = [[2,8,7],[7,1,3],[1,9,5]]
Output: 17
```

Constraints:


- `m == accounts.length`
- `n == accounts[i].length`
- `1 <= m, n <= 50`
- `1 <= accounts[i][j] <= 100`

#### My solution
```
class Solution:
    def maximumWealth(self, accounts: List[List[int]]) -> int:
        maxWealth=0
        for subArray in accounts:
            total=0
            for element in subArray:
                total+=element
            if total > maxWealth:
                maxWealth=total
        return maxWealth
```
- Runtime: 52 ms, faster than 79.78% of Python3 online submissions for Richest Customer Wealth.
- Memory Usage: 14.2 MB, less than 60.90% of Python3 online submissions for Richest Customer Wealth.
