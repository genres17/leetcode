## 322. Coin Change - 零钱兑换

<!--If you want to use the English description, use `question.content` instead-->

<p>给定不同面额的硬币 coins 和一个总金额 amount。编写一个函数来计算可以凑成总金额所需的最少的硬币个数。如果没有任何一种硬币组合能组成总金额，返回&nbsp;<code>-1</code>。</p>

<p>&nbsp;</p>

<p><strong>示例&nbsp;1:</strong></p>

<pre><strong>输入: </strong>coins = <code>[1, 2, 5]</code>, amount = <code>11</code>
<strong>输出: </strong><code>3</code> 
<strong>解释:</strong> 11 = 5 + 5 + 1</pre>

<p><strong>示例 2:</strong></p>

<pre><strong>输入: </strong>coins = <code>[2]</code>, amount = <code>3</code>
<strong>输出: </strong>-1</pre>

<p>&nbsp;</p>

<p><strong>说明</strong>:<br>
你可以认为每种硬币的数量是无限的。</p>



-----

题目标签：Dynamic Programming

题目链接：[LeetCode](https://leetcode.com/problems/coin-change/description/)  /  [LeetCode中国](https://leetcode-cn.com/problems/coin-change/description/)

## 题解



| Language | Runtime | Memory |
|:---:|:---:|:---:|
| cpp  | 148 ms | 9.7 MB |

```cpp
class Solution {
public:
    int coinChange(vector<int>& coins, int amount) {
        int dp[amount+1];
        dp[0]=0;//初始化条件
        for(int i=1;i<=amount;i++){
            dp[i]=INT_MAX;
            for(int j=0;j<coins.size();j++){
                if(i>=coins[j]&&dp[i-coins[j]]!=INT_MAX&&dp[i-coins[j]]+1<dp[i]){
                    dp[i]=dp[i-coins[j]]+1;
                }
            }
        }
        if(dp[amount]==INT_MAX)return -1;
        return dp[amount];
    }
};
```
