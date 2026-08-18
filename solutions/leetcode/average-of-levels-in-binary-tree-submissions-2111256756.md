# average of levels in binary tree/submissions/2111256756

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
    vector<double> averageOfLevels(TreeNode* root) {
        vector<double> ans;
        if(root==nullptr) return {};
        queue<TreeNode*>q;
        q.push(root);

        while(!q.empty()){
            int size= q.size();
            double sum=0;
            int count=0;

            while(size--){

                TreeNode* a= q.front();
                q.pop();
                count++;

                sum += (double)a->val;

                if(a->left!=nullptr) q.push(a->left);
                if(a->right!=nullptr) q.push(a->right);

            }
            ans.push_back(sum/count);
        }
        return ans;
    }
};
```
