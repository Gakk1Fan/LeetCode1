## 代码

```c++
//头插法
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
    vector<int> reversePrint(ListNode* head) {
        vector<int> res;
        ListNode *dummy = new ListNode(-1);
        while (head) {
            ListNode *r = head->next;
            head->next = dummy->next;
            dummy->next = head;
            head = r;
        }
        dummy = dummy->next;
        while (dummy) {
            res.push_back(dummy->val);
            dummy = dummy->next;
        }
        return res;
    }
};

//时间复杂度O(n)
//空间复杂度O(1)
```

