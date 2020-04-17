## 55. Jump Game - 跳跃游戏

<!--If you want to use the English description, use `question.content` instead-->

<p>给定一个非负整数数组，你最初位于数组的第一个位置。</p>

<p>数组中的每个元素代表你在该位置可以跳跃的最大长度。</p>

<p>判断你是否能够到达最后一个位置。</p>

<p><strong>示例&nbsp;1:</strong></p>

<pre><strong>输入:</strong> [2,3,1,1,4]
<strong>输出:</strong> true
<strong>解释:</strong> 我们可以先跳 1 步，从位置 0 到达 位置 1, 然后再从位置 1 跳 3 步到达最后一个位置。
</pre>

<p><strong>示例&nbsp;2:</strong></p>

<pre><strong>输入:</strong> [3,2,1,0,4]
<strong>输出:</strong> false
<strong>解释:</strong> 无论怎样，你总会到达索引为 3 的位置。但该位置的最大跳跃长度是 0 ， 所以你永远不可能到达最后一个位置。
</pre>



-----

题目标签：Greedy / Array

题目链接：[LeetCode](https://leetcode.com/problems/jump-game/description/)  /  [LeetCode中国](https://leetcode-cn.com/problems/jump-game/description/)

## 题解



| Language | Runtime | Memory |
|:---:|:---:|:---:|
| cpp  | 1616 ms | 7.7 MB |

```cpp
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int last=nums.size();
        bool dp[last+1];
        dp[0]=true;//设定0的位置一定能到达
        for(int j=1;j<last;j++){
            dp[j]=false;
            for(int i=0;i<j;i++){
                if(dp[i]&&i+nums[i]>=j){
                    dp[j]=true;
                    break;
                }
            }
        }
        return dp[last-1];
    }
};
```
