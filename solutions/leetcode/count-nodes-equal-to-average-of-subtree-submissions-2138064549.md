# count nodes equal to average of subtree/submissions/2138064549

**Platform:** LeetCode  
**Date:** 2026-09-11  

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
    int solver(TreeNode* node){

        int sum=0;
        int n=0;
        queue<TreeNode*> q;
        q.push(node);

        while(!q.empty()){
            TreeNode* node= q.front();
            q.pop();
            n++;
            sum +=node->val;

            if(node->left != nullptr){
                q.push(node->left);
            }
            if(node->right !=nullptr){
                q.push(node->right);
            }
        }
        return sum/n;

    }
    int averageOfSubtree(TreeNode* root) {

        if(root==nullptr) return 0;
        int count=0;

        queue<TreeNode*> q;
        q.push(root);

        while(!q.empty()){

            TreeNode* node= q.front();
            q.pop();
            int a=solver(node);
            if(node->val==a){
                count++;
            }
            if(node->right!=nullptr) q.push(node->right);
            if(node->left!=nullptr) q.push(node->left);
        }
        return count;
    }
};
```
