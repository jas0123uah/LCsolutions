# LeetCode Solutions
My solutions to LeetCode problems.
## Easy array problems

### Problem 1480 

#### My solution
<code>
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        totalsum=0
        ans=[]
        for i in nums:
            totalsum+=i
            ans.append(totalsum)
        return ans
    </code>
Runtime: 64 ms, faster than 12.69% of Python3 online submissions for Running Sum of 1d Array.
Memory Usage: 14.2 MB, less than 97.71% of Python3 online submissions for Running Sum of 1d Array.

#### Solution with accumulate
<code>
class Solution:
    def runningSum(self, nums: List[int]) -> List[int]:
        return accumulate(nums)   
        </code>
