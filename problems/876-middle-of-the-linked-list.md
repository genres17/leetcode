## 876. Middle of the Linked List - 链表的中间结点

<!--If you want to use the English description, use `question.content` instead-->

<p>给定一个带有头结点&nbsp;<code>head</code>&nbsp;的非空单链表，返回链表的中间结点。</p>

<p>如果有两个中间结点，则返回第二个中间结点。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre><strong>输入：</strong>[1,2,3,4,5]
<strong>输出：</strong>此列表中的结点 3 (序列化形式：[3,4,5])
返回的结点值为 3 。 (测评系统对该结点序列化表述是 [3,4,5])。
注意，我们返回了一个 ListNode 类型的对象 ans，这样：
ans.val = 3, ans.next.val = 4, ans.next.next.val = 5, 以及 ans.next.next.next = NULL.
</pre>

<p><strong>示例&nbsp;2：</strong></p>

<pre><strong>输入：</strong>[1,2,3,4,5,6]
<strong>输出：</strong>此列表中的结点 4 (序列化形式：[4,5,6])
由于该列表有两个中间结点，值分别为 3 和 4，我们返回第二个结点。
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li>给定链表的结点数介于&nbsp;<code>1</code>&nbsp;和&nbsp;<code>100</code>&nbsp;之间。</li>
</ul>



-----

题目标签：Linked List

题目链接：[LeetCode](https://leetcode.com/problems/middle-of-the-linked-list/description/)  /  [LeetCode中国](https://leetcode-cn.com/problems/middle-of-the-linked-list/description/)

## 题解



| Language | Runtime | Memory |
|:---:|:---:|:---:|
| cpp  | 0 ms | 8.6 MB |

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* middleNode(ListNode* head) {
        ListNode *fast,*mid;
        fast=mid=head;
        int count=0;
        while(fast->next!=NULL){

            fast = fast->next;
            count++;

        }
        int sum=0;
        if(count%2==0){
           while(mid->next!=NULL&&count/2!=sum){
               mid=mid->next;
               sum++;
           }
           return mid;
        }else{
             while(mid->next!=NULL&&count/2+1!=sum){
               mid=mid->next;
               sum++;
           }
           return mid;

        }
    }
};
```
