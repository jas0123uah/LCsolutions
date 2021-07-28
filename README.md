# LeetCode Solutions
My solutions to LeetCode problems.

<span>Runtime:&nbsp;<span class="data__HC-i">56 ms</span><span>, faster than <span class="data__HC-i">89.62%</span> of Python3 online submissions for Two Sum.</span></span>
<span>Memory Usage:&nbsp;<span class="data__HC-i">15.2 MB</span><span>, less than <span class="data__HC-i">53.71%</span> of Python3 online submissions for Two Sum.</span></span>
## Easy Array Problems

### Problem 1920. Build Array from Permutation
Given a zero-based permutation `nums` (<b>0-indexed</b>), build an array `ans` of the same length where `ans[i] = nums[nums[i]]` for each `0 <= i < nums.length` and return it.

A <b>>zero-based permutation</b> `nums` is an array of <b>distinct</b> integers from `0 to nums.length - 1` (<b>inclusive</b>).
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

### Problem 1431 Kids With The Greatest Number of Candies
#### Description
There are `n` kids with candies. You are given an integer array `candies`, where each `candies[i]` represents the number of candies the `ith` kid has, and an integer `extraCandies`, denoting the number of extra candies that you have.

Return a boolean array `result` of length `n`, where `result[i]` is `true` if, after giving the `ith` kid all the `extraCandies`, they will have the <b>greatest</b> number of candies among all the kids, or `false` otherwise.

Note that <b>multiple</b> kids can have the <b>greatest</b> number of candies.

##### Example 1:
```
Input: candies = [2,3,5,1,3], extraCandies = 3
Output: [true,true,true,false,true] 
Explanation: If you give all extraCandies to:
- Kid 1, they will have 2 + 3 = 5 candies, which is the greatest among the kids.
- Kid 2, they will have 3 + 3 = 6 candies, which is the greatest among the kids.
- Kid 3, they will have 5 + 3 = 8 candies, which is the greatest among the kids.
- Kid 4, they will have 1 + 3 = 4 candies, which is not the greatest among the kids.
- Kid 5, they will have 3 + 3 = 6 candies, which is the greatest among the kids.
```
##### Example 2:
```
Input: candies = [4,2,1,1,2], extraCandies = 1
Output: [true,false,false,false,false] 
Explanation: There is only 1 extra candy.
Kid 1 will always have the greatest number of candies, even if a different kid is given the extra candy.
```
##### Example 3:
```
Input: candies = [12,1,12], extraCandies = 10
Output: [true,false,true]
```

Constraints:
- `n == candies.length`
- `2 <= n <= 100`
- `1 <= candies[i] <= 100`
- `1 <= extraCandies <= 50`



#### My solution
```
class Solution:
    def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List[bool]:
        maxCandies= max(candies)
        booleanArray=[]
        for i in candies:
            booleanArray.append(False) if i +extraCandies < maxCandies else booleanArray.append(True)
        return booleanArray
```
- Runtime: 36 ms, faster than 82.55% of Python3 online submissions for Kids With the Greatest Number of Candies.
- Memory Usage: 14.3 MB, less than 52.47% of Python3 online submissions for Kids With the Greatest Number of Candies

### Problem 1480 Running Sum of 1d Array
#### Description
Given the array `nums` consisting of `2n` elements in the form `[x1,x2,...,xn,y1,y2,...,yn]`.

Return the array in the form `[x1,y1,x2,y2,...,xn,yn]`.

##### Example 1:
```
Input: nums = [2,5,1,3,4,7], n = 3
Output: [2,3,5,4,1,7] 
Explanation: Since x1=2, x2=5, x3=1, y1=3, y2=4, y3=7 then the answer is [2,3,5,4,1,7].
```
##### Example 2:
```
Input: nums = [1,2,3,4,4,3,2,1], n = 4
Output: [1,4,2,3,3,2,4,1]

```
##### Example 3:
```
Input: nums = [1,1,2,2], n = 2
Output: [1,2,1,2]
```

Constraints:
`1 <= n <= 500`
`nums.length == 2n`
`1 <= nums[i] <= 10^3`



#### My solution
```
class Solution:
    def shuffle(self, nums: List[int], n: int) -> List[int]:
        shuffledArray=[]
        leftArray=nums[0:n]
        rightArray=nums[n:]
        for idx in range(0,(n)):
            shuffledArray.append(leftArray[idx])
            shuffledArray.append(rightArray[idx])
        return shuffledArray
```
- Runtime: 64 ms, faster than 38.08% of Python3 online submissions for Shuffle the Array.

- Memory Usage: 14.4 MB, less than 77.02% of Python3 online submissions for Shuffle the Array.
 
### 1512. Number of Good Pairs
#### Description
Given an array of integers `nums`.

A pair `(i,j) `is called good if `nums[i] == nums[j] and i < j`.

Return the number of good pairs.

##### Example 1:
```
Input: nums = [1,2,3,1,1,3]
Output: 4
Explanation: There are 4 good pairs (0,3), (0,4), (3,4), (2,5) 0-indexed.
```
##### Example 2:
```
Input: nums = [1,1,1,1]
Output: 6
Explanation: Each pair in the array are good.
```
##### Example 3:
```
Input: nums = [1,2,3]
Output: 0
```

Constraints:
- `1 <= nums.length <= 100`
- `1 <= nums[i] <= 100`



#### My solution
```
class Solution:
    def numIdenticalPairs(self, nums: List[int]) -> int:
        numGoodPairs=0
        for idx1, num1 in enumerate(nums):
            for idx2, num2 in enumerate(nums):
                if idx1 <idx2 and (nums[idx1]==nums[idx2]):
                    numGoodPairs+=1
        return numGoodPairs
```
- Runtime: 40 ms, faster than 29.87% of Python3 online submissions for Number of Good Pairs.
- Memory Usage: 14.4 MB, less than 10.98% of Python3 online submissions for Number of Good Pairs.
1. Two Sum<div><p>Given an array of integers <code>nums</code>&nbsp;and an integer <code>target</code>, return <em>indices of the two numbers such that they add up to <code>target</code></em>.</p>

<p>You may assume that each input would have <strong><em>exactly</em> one solution</strong>, and you may not use the <em>same</em> element twice.</p>

<p>You can return the answer in any order.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> nums = [2,7,11,15], target = 9
<strong>Output:</strong> [0,1]
<strong>Output:</strong> Because nums[0] + nums[1] == 9, we return [0, 1].
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> nums = [3,2,4], target = 6
<strong>Output:</strong> [1,2]
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> nums = [3,3], target = 6
<strong>Output:</strong> [0,1]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>2 &lt;= nums.length &lt;= 10<sup>4</sup></code></li>
	<li><code>-10<sup>9</sup> &lt;= nums[i] &lt;= 10<sup>9</sup></code></li>
	<li><code>-10<sup>9</sup> &lt;= target &lt;= 10<sup>9</sup></code></li>
	<li><strong>Only one valid answer exists.</strong></li>
</ul>

<p>&nbsp;</p>
<strong>Follow-up:&nbsp;</strong>Can you come up with an algorithm that is less than&nbsp;<code>O(n<sup>2</sup>)&nbsp;</code>time complexity?</div>#### My solution
```1
class Solution:
2
    def twoSum(self, nums: List[int], target: int) -> List[int]:
3
        numbers_and_index={}
4
        for i in range(len(nums)):
5
            difference=target-nums[i]
6
            if difference in numbers_and_index.keys():
7
                return([numbers_and_index.get(difference), i])
8
            else:
9
                numbers_and_index[nums[i]]=i```
