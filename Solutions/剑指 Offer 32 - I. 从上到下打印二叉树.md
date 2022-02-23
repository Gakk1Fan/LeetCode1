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
    vector<int> levelOrder(TreeNode* root) {
        vector<int> res;
        if (!root) return res;
        queue<TreeNode*> q;
        q.push(root);
        while (!q.empty()) {
            auto cur = q.front();
            q.pop();
            res.push_back(cur->val);
            if (cur->left) q.push(cur->left);
            if (cur->right) q.push(cur->right);
        }
        return res;
    }
};
//时间复杂度 O(N)：N为二叉树的节点数量
//空间复杂度 O(N)：最差情况下，即当树为平衡二叉树时，最多有N/2个树节点同时在queue中，使用O(N)大小的额外空间
```

