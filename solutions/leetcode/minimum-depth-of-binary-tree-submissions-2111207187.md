# minimum depth of binary tree/submissions/2111207187

**Platform:** LeetCode  
**Date:** 2026-08-18  

## Solution

```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    int minDepth(TreeNode* root) {

        if(root==NULL){ return 0;}
        queue<TreeNode*> q;
        q.push(root);
        int ans=1;

        while(!q.empty()){
            int size= q.size();

            while(size--){
                TreeNode* a= q.front();
                q.pop();

                if(a->left==NULL  && a->right==NULL){return ans;}
                else if(a->left!=NULL) q.push(a->left);
                else if(a->right!=NULL) q.push(a->right);
            }
            ans++;
        }
        return ans;

    }
};
```
