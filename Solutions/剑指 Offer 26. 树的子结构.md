## 代码

```c++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    bool isSubStructure(TreeNode* A, TreeNode* B) {
        if (!A || !B) return false;
        return recur(A, B) || isSubStructure(A->left, B) || isSubStructure(A->right, B);
    }

    bool recur(TreeNode* p, TreeNode* q) {
        //判断以q结点为跟是不是以p结点的子树
        if (!q) return true;
        if (!p || p->val != q->val) return false;
        return recur(p->left, q->left) && recur(p->right, q->right);
    }
};
//时间复杂度O(MN)
//空间复杂度O(M)
//M是A树结点的数量，N是树B结点的数量
```

