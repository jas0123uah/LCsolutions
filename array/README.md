## Easy array Problems
## Medium array Problems
### 35. Search Insert Position
#### Description
<div><p>Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.</p>

<p>You must&nbsp;write an algorithm with&nbsp;<code>O(log n)</code> runtime complexity.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<pre><strong>Input:</strong> nums = [1,3,5,6], target = 5
<strong>Output:</strong> 2
</pre><p><strong>Example 2:</strong></p>
<pre><strong>Input:</strong> nums = [1,3,5,6], target = 2
<strong>Output:</strong> 1
</pre><p><strong>Example 3:</strong></p>
<pre><strong>Input:</strong> nums = [1,3,5,6], target = 7
<strong>Output:</strong> 4
</pre><p><strong>Example 4:</strong></p>
<pre><strong>Input:</strong> nums = [1,3,5,6], target = 0
<strong>Output:</strong> 0
</pre><p><strong>Example 5:</strong></p>
<pre><strong>Input:</strong> nums = [1], target = 0
<strong>Output:</strong> 0
</pre>
<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>4</sup></code></li>
	<li><code>-10<sup>4</sup> &lt;= nums[i] &lt;= 10<sup>4</sup></code></li>
	<li><code>nums</code> contains <strong>distinct</strong> values sorted in <strong>ascending</strong> order.</li>
	<li><code>-10<sup>4</sup> &lt;= target &lt;= 10<sup>4</sup></code></li>
</ul>
</div>

#### My solution
```
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        def s1(nums, target):
            n = len(nums)
            6
            if nums[0] >= target:
                return 0
            if nums[-1] < target:
                return n
            11
            i = 0
            j = n - 1
            while i < j:
                k = (i + j) // 2
                print(k)
                if nums[k] < target:
                    if k + 1 >= n:
                        return n
                    if nums[k + 1] >= target:
                        return k + 1
                    i = k
                elif nums[k] > target:
                    if k - 1 < 0:
                        return 0
                    if nums[k - 1] < target:
                        return k
                    j = k
                else:
                    return k
            31
            return 0 if k <= 0 else n
        33
        return s1(nums, target)
```
## Hard array Problems
