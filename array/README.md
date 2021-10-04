## Easy array Problems
### 1. Two Sum
#### Description
<div><p>Given an array of integers <code>nums</code>&nbsp;and an integer <code>target</code>, return <em>indices of the two numbers such that they add up to <code>target</code></em>.</p>

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
<strong>Follow-up:&nbsp;</strong>Can you come up with an algorithm that is less than&nbsp;<code>O(n<sup>2</sup>)&nbsp;</code>time complexity?</div>

#### My solution
```
class Solution:
    #1. Declare empty dict
    #2. Iterate over the array, store each num and idx in empty dict
    #3. Calculate the difference. If difference in empty dict return early, pushing indices ri array.
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        numbers_and_index={}
        for i in range(len(nums)):
            difference=target-nums[i]
            if difference in numbers_and_index.keys():
                return([numbers_and_index.get(difference), i])
            else:
                numbers_and_index[nums[i]]=i
```
### 1920. Build Array from Permutation
#### Description
<div><p>Given a <strong>zero-based permutation</strong> <code>nums</code> (<strong>0-indexed</strong>), build an array <code>ans</code> of the <strong>same length</strong> where <code>ans[i] = nums[nums[i]]</code> for each <code>0 &lt;= i &lt; nums.length</code> and return it.</p>

<p>A <strong>zero-based permutation</strong> <code>nums</code> is an array of <strong>distinct</strong> integers from <code>0</code> to <code>nums.length - 1</code> (<strong>inclusive</strong>).</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> nums = [0,2,1,5,3,4]
<strong>Output:</strong> [0,1,2,4,5,3]<strong>
Explanation:</strong> The array ans is built as follows: 
ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
    = [nums[0], nums[2], nums[1], nums[5], nums[3], nums[4]]
    = [0,1,2,4,5,3]</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> nums = [5,0,1,2,3,4]
<strong>Output:</strong> [4,5,0,1,2,3]
<strong>Explanation:</strong> The array ans is built as follows:
ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
    = [nums[5], nums[0], nums[1], nums[2], nums[3], nums[4]]
    = [4,5,0,1,2,3]</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 1000</code></li>
	<li><code>0 &lt;= nums[i] &lt; nums.length</code></li>
	<li>The elements in <code>nums</code> are <strong>distinct</strong>.</li>
</ul>

<p>&nbsp;</p>
<p><strong>Follow-up:</strong> Can you solve it without using an extra space (i.e., <code>O(1)</code> memory)?</p>
</div>

#### My solution
```
class Solution:
    def buildArray(self, nums: List[int]) -> List[int]:
        ans=[]
        for i in nums:
            ans.append(nums[i])
        return ans
```
### 1528. Shuffle String
#### Description
<div><p>Given a string <code>s</code>&nbsp;and an integer array <code>indices</code> of the <strong>same length</strong>.</p>

<p>The string <code>s</code> will be shuffled such that the character at the <code>i<sup>th</sup></code> position moves to&nbsp;<code>indices[i]</code> in the shuffled string.</p>

<p>Return <em>the shuffled string</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/07/09/q1.jpg" style="width: 321px; height: 243px;">
<pre><strong>Input:</strong> s = "codeleet", <code>indices</code> = [4,5,6,7,0,2,1,3]
<strong>Output:</strong> "leetcode"
<strong>Explanation:</strong> As shown, "codeleet" becomes "leetcode" after shuffling.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> s = "abc", <code>indices</code> = [0,1,2]
<strong>Output:</strong> "abc"
<strong>Explanation:</strong> After shuffling, each character remains in its position.
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> s = "aiohn", <code>indices</code> = [3,1,4,2,0]
<strong>Output:</strong> "nihao"
</pre>

<p><strong>Example 4:</strong></p>

<pre><strong>Input:</strong> s = "aaiougrt", <code>indices</code> = [4,0,2,6,7,3,1,5]
<strong>Output:</strong> "arigatou"
</pre>

<p><strong>Example 5:</strong></p>

<pre><strong>Input:</strong> s = "art", <code>indices</code> = [1,0,2]
<strong>Output:</strong> "rat"
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>s.length == indices.length == n</code></li>
	<li><code>1 &lt;= n &lt;= 100</code></li>
	<li><code>s</code> contains only lower-case English letters.</li>
	<li><code>0 &lt;= indices[i] &lt;&nbsp;n</code></li>
	<li>All values of <code>indices</code> are unique (i.e. <code>indices</code> is a permutation of the integers from <code>0</code> to <code>n - 1</code>).</li>
</ul></div>

#### My solution
```
# UTP: Move the characters of a string to a new index given a string and an array of indices
#Plan 
#1. Create empty dict for chars and their new index position
#2. Create an empty string to append the letters to it
#3. Use enumerate to access both the string and the array of new indices to add letters and their new index to the dict. Indices are keys, letters are values.
#4. Use range to get the keys/ indices and their corresponding letter in order
#5. return growing_string
class Solution:
    def restoreString(self, s: str, indices: List[int]) -> str:
        dict_of_chars_and_indices={}
        growing_string=""
        length_of_string=len(s)
        for idx, letter in enumerate(s):
            new_index=indices[idx]
            dict_of_chars_and_indices[new_index]=letter
        for i in range(0, length_of_string):
            nth_character=dict_of_chars_and_indices.get(i)
            growing_string+=nth_character
        return growing_string
```
### 1572. Matrix Diagonal Sum
#### Description
<div><p>Given a&nbsp;square&nbsp;matrix&nbsp;<code>mat</code>, return the sum of the matrix diagonals.</p>

<p>Only include the sum of all the elements on the primary diagonal and all the elements on the secondary diagonal that are not part of the primary diagonal.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2020/08/14/sample_1911.png" style="width: 336px; height: 174px;">
<pre><strong>Input:</strong> mat = [[<strong>1</strong>,2,<strong>3</strong>],
&nbsp;             [4,<strong>5</strong>,6],
&nbsp;             [<strong>7</strong>,8,<strong>9</strong>]]
<strong>Output:</strong> 25
<strong>Explanation: </strong>Diagonals sum: 1 + 5 + 9 + 3 + 7 = 25
Notice that element mat[1][1] = 5 is counted only once.
</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> mat = [[<strong>1</strong>,1,1,<strong>1</strong>],
&nbsp;             [1,<strong>1</strong>,<strong>1</strong>,1],
&nbsp;             [1,<strong>1</strong>,<strong>1</strong>,1],
&nbsp;             [<strong>1</strong>,1,1,<strong>1</strong>]]
<strong>Output:</strong> 8
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> mat = [[<strong>5</strong>]]
<strong>Output:</strong> 5
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>n == mat.length == mat[i].length</code></li>
	<li><code>1 &lt;= n &lt;= 100</code></li>
	<li><code>1 &lt;= mat[i][j] &lt;= 100</code></li>
</ul>
</div>

#### My solution
```
# UTP: Iterate over the left and right diagonals of an array calculating a total sum of subarrays/matrix. Count the middle of the matrix only once.
# 1. At the right diagonal i and j = are == so use for i in range()
# 2. At the left diagonal i and j increment toward each other. Icrease sum when i!=j. Continue while loop if j>=0
#3. Return sum
class Solution:
    def diagonalSum(self, mat: List[List[int]]) -> int:
        sum=0
        #Get left diagonal
        i=0
        j=len(mat)-1
        while j>=0:
            if i !=j:
                sum+=mat[i][j]
            i+=1
            j-=1
        #Get Right diagonal
        for i in range(0, len(mat)):
            sum+=mat[i][i]
        return sum
```
### 1662. Check If Two String Arrays are Equivalent
#### Description
<div><p>Given two string arrays <code>word1</code> and <code>word2</code>, return<em> </em><code>true</code><em> if the two arrays <strong>represent</strong> the same string, and </em><code>false</code><em> otherwise.</em></p>

<p>A string is <strong>represented</strong> by an array if the array elements concatenated <strong>in order</strong> forms the string.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre><strong>Input:</strong> word1 = ["ab", "c"], word2 = ["a", "bc"]
<strong>Output:</strong> true
<strong>Explanation:</strong>
word1 represents string "ab" + "c" -&gt; "abc"
word2 represents string "a" + "bc" -&gt; "abc"
The strings are the same, so return true.</pre>

<p><strong>Example 2:</strong></p>

<pre><strong>Input:</strong> word1 = ["a", "cb"], word2 = ["ab", "c"]
<strong>Output:</strong> false
</pre>

<p><strong>Example 3:</strong></p>

<pre><strong>Input:</strong> word1  = ["abc", "d", "defg"], word2 = ["abcddefg"]
<strong>Output:</strong> true
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= word1.length, word2.length &lt;= 10<sup>3</sup></code></li>
	<li><code>1 &lt;= word1[i].length, word2[i].length &lt;= 10<sup>3</sup></code></li>
	<li><code>1 &lt;= sum(word1[i].length), sum(word2[i].length) &lt;= 10<sup>3</sup></code></li>
	<li><code>word1[i]</code> and <code>word2[i]</code> consist of lowercase letters.</li>
</ul>
</div>

#### My solution
```
class Solution:
    def arrayStringsAreEqual(self, word1: List[str], word2: List[str]) -> bool:
        joined_word_1="".join(word1)
        joined_word_2="".join(word2)
        return joined_word_1==joined_word_2
```
## Medium array Problems
## Hard array Problems
