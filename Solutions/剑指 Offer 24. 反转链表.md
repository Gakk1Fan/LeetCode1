```c++
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
    ListNode* reverseList(ListNode* head) {
        ListNode *dummy = new ListNode(-1);
        while (head) {
            ListNode *r = head->next;
            head->next = dummy->next;
            dummy->next = head;
            head = r;
        }
        return dummy->next;
    }
};
```

