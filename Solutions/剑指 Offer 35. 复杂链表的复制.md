## 思路

```c++
分为三个步骤
    1.复制链表的每一个节点，插入到后面
    2.复制节点的random指针
    3.拆出复制的节点
```



## 代码

```c++
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* next;
    Node* random;
    
    Node(int _val) {
        val = _val;
        next = NULL;
        random = NULL;
    }
};
*/
class Solution {
public:
    Node* copyRandomList(Node* head) {
        for (auto p = head; p; p = p->next->next) {
            auto np = new Node(p->val);
            np->next = p->next;
            p->next = np;
        }

        for (auto p = head; p; p = p->next->next) {
            if (p->random) {
                p->next->random = p->random->next;
            }
        }

        auto dummy = new Node(-1);
        auto cur = dummy;
        for (auto p = head; p; p = p->next) {
            cur->next = p->next;
            cur = cur->next;
            p->next = p->next->next;
        }

        return dummy->next;

    }
};

//时间复杂度O(n)
//空间复杂度O(1)
```

