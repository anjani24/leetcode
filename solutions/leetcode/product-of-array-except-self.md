# product of array except self

**Platform:** LeetCode  
**Date:** 2026-07-01  

## Solution

```
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n= nums.size();
        vector<int> ans(n);
        vector<int> left(n);
        vector<int> right(n);
        int p=1;
        int q=1;
        left[0]=1;
        right[n-1]=1;
        for(int i=1; i<n; i++){
            p= nums[i-1]*p;
            left[i]= p; 
        }
        
        for(int i=n-2; i>=0; i--){
            q= nums[i+1] *q;
            right[i]= q;  
        }
        
        for(int i=0; i<n ;i++){
            ans[i]= left[i]* right[i];
        }
        return ans;
        //okiiii
        //bubu left[0] to kuch hai hi nahi and right[n-1] 1 hoga na bubu kyuki kuch hai hi nahi sides mein to pehle hi define krke chod diya main to
        
        
        // ni samjh ara
        //ummm if we use space than toh n^2 hi aari tc 
        // map use krke 
        // ohh hnn dekh
        //noo sun ek for loop for each element in nums and ek for multiplying 
        // cz we cant use divide 
        // this is brute force only//
        // map mai ={element, index} or vice versa
        //yesss
        // wht else can i do 
        // mtlbb wht is prefix suffix?
        
        //to aise har kisi ke liye krna hoga? saare elements ka left and right banega?
        // toh ye bhi to woi ni? n^2?
        // ohhhhh okokk samjhaaaa yess wowwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwwww
        // okokokk samjha 
        // but this is not O(1) space? follow up mai likha
        // kro think ye likhti tb tk
        
        
        //likh ke dekho bubu no what wo want O(1) space
        //vo to think krna padega :cry
        //okay
        //hnnn for every element yes mtlb uss index pe store ho jayega array bana lete na
        //how? mtlb pehle left bhar liya fir right n mein ho gya fir teesre for mein ans bhar diya
        //kaise? n^2 how? nested loops wherE? mtlb map mein kya daal rhe? to you are multiplying using nested loops for each element?
        //hnn mtlb maine bhi yehi socha tha isme lc mein hint likha prefix suffix use krke krlo
        //mtlb aise 2 array bana lete na ek left ek right to jaise index hai mera 3 to left mein uske left vaalo ka multiplication store hoga right mein right ka fir answer will be left[i]*right[i]
        //
        
    //
    
        
        
        
        
        
    }
};


/*
int n=nums.size();
vector<int>ans(n,1);
for(int i=1;i<n;i++)
{
ans[i]=ans[i-1]*nums[i-1];
}
for(int i=n-2;i>=0;i--)
{
ans[i]*=ans[i+1]*nums[i+1];
}
return ans;
*/


```
