# find the minimum and maximum number of nodes between critical points

**Platform:** LeetCode  
**Date:** 2026-08-31  

## Solution

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    vector<int> nodesBetweenCriticalPoints(ListNode* head) {

        if(head==nullptr || head->next==nullptr || head->next->next==nullptr){
            return {-1,-1};
        }

        ListNode* a=head->next;
        ListNode* temp=head;
        int n=2;
        vector<int> v;

        while(a!=nullptr && a->next!=nullptr){
            if(temp->val<a->val && a->next->val<a->val){
                v.push_back(n);
            }
            if(temp->val>a->val && a->next->val>a->val){
                v.push_back(n);
            }
            n++;
            a=a->next;
            temp=temp->next;
        } 

        if(v.size()<=1) return {-1,-1};

        int maxima=v.back()-v.front();
        int minima=INT_MAX;  
        for(int i=1; i< v.size(); i++){
            minima= min(minima, v[i]-v[i-1]);
        }  

        return {minima,maxima}; 
    }
};
```
