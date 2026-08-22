# path sum/submissions/2116288471

**Platform:** LeetCode  
**Date:** 2026-08-22  

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
    bool hasPathSum(TreeNode* root, int targetSum) {

        if(root==nullptr) return false;

        queue<pair<TreeNode*,int>> q;   
        q.push({root, root->val});
        int sum=root->val;
        if(sum>targetSum) return false;

        while(!q.empty()){

            auto [a, sum]= q.front();
            q.pop();

            if(a->left==NULL && a->right==NULL && sum==targetSum){
                return true;
            }

            if(sum<targetSum){
                if(a->left!=NULL) q.push({a->left, sum+a->left->val});
                if(a->right!=NULL) q.push({a->right, sum+a->right->val});
            }
        }
        return false;
        
    }
};
```
