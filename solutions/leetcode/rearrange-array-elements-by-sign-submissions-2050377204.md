# rearrange array elements by sign/submissions/2050377204

**Platform:** LeetCode  
**Date:** 2026-06-29  

## Solution

```
class Solution {
public:
    vector<int> rearrangeArray(vector<int>& nums) {

        int n= nums.size();
        vector<int> ans(n);
        int p=0;
        int q=1;

        for(int i=0; i< n; i++){
            if(nums[i]>0){
                ans[p]= nums[i];
                p=p+2;
            }
        }

        for(int i=0; i<n ;i++){
            if(nums[i]<0){
                ans[q]= nums[i];
                q= q+2;
            }
        }
        return ans;
        
    }
};


/*
common space :sax space:



think time!!!!!!!! 15 min

if done write upr TTTTTTT TUNTUNN TATVAMMSSS



//tatvam's space : kissus from annie: 

lets make two pointers on stays on positive one on negative and then put in another vector
for example
nums = [3,1,-2,-5,2,-4]
pos=3 neg=3
if index odd then we put pointer with neg value and increment neg pointer if value is pos and vice versa
ur approach seems better swapping
vector<int>ans;
int pos=0;
int neg=0;
for(int i=0;i<n;i++)
{
if(nums[pos]<0)pos++; continue;
if(nums[neg]>0)neg--; continue;
if()
}













// annie's think space :angry: :peace: :annie loves noni: 


annie misses noni :(((

ummm  swapping kr skte 
in place ni krna zaroori toh we can make another vector than start adding elements one by one :think:

vector<int> ans(n);

for(int i=0; i< n; i++){
if nums[i] > 0

}



*/
```
