## 136. Single Number - 只出现一次的数字

<!--If you want to use the English description, use `question.content` instead-->

<p>给定一个<strong>非空</strong>整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。</p>

<p><strong>说明：</strong></p>

<p>你的算法应该具有线性时间复杂度。 你可以不使用额外空间来实现吗？</p>

<p><strong>示例 1:</strong></p>

<pre><strong>输入:</strong> [2,2,1]
<strong>输出:</strong> 1
</pre>

<p><strong>示例&nbsp;2:</strong></p>

<pre><strong>输入:</strong> [4,1,2,1,2]
<strong>输出:</strong> 4</pre>



-----

题目标签：Bit Manipulation / Hash Table

题目链接：[LeetCode](https://leetcode.com/problems/single-number/description/)  /  [LeetCode中国](https://leetcode-cn.com/problems/single-number/description/)

## 题解



| Language | Runtime | Memory |
|:---:|:---:|:---:|
| python3  | 92 ms | 15.7 MB |

```python3
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        """利用牛客上看见的高级做法异或思想：
           1.a^b^c=a^c^b
           2.0^n=n(任何数与0异或都是任何数)
           3.相同的数异或为0：n^n=0"""
        a=0
        for i in nums:
            a=a^i 
        return a
```
