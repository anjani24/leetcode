# maximum level sum of a binary tree/submissions/2111227905

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
    int maxLevelSum(TreeNode* root) {

        if(root==NULL) return 0;

        pair<int,int> maxsum={0,0};
        int level=1;

        queue<TreeNode*>q;
        q.push(root);

        while(!q.empty()){
            int size= q.size();
            int sum=0;

            while(size--){
                TreeNode* a= q.front();
                sum +=a->val;
                q.pop();

                if(a->right!=nullptr) q.push(a->right);
                if(a->left!=nullptr) q.push(a->left);

            }
            if(sum>maxsum.first){
                maxsum.first=sum;
                maxsum.second=level;
            }
            level++;
        }
        return maxsum.second;
        
    }
};
```
