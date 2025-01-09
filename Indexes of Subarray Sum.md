# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array arr[] containing only non-negative integers, your task is to find a continuous subarray (a contiguous sequence of elements) whose sum equals a specified value target. You need to return the 1-based indices of the leftmost and rightmost elements of this subarray. You need to find the first subarray whose sum is equal to the target.

Note: If no such array is possible then, return [-1].


# 📝Code ⬇:-


# C++
``` cpp []

class Solution {
  public:
    vector<int> subarraySum(vector<int> &arr, int target) {
        // CodeGenius
        int s=0,e=0;
        int sum=0;
        vector<int>ans;
        for(int i=0;i<arr.size();i++){
            sum+=arr[i];
           // if(sum<target) // ignore
           if(sum>=target){
               e=i;
               while(sum>target){
                   sum-=arr[s];
                   ++s;
               }
               if(sum==target){
                   ans.push_back(s+1);
                   ans.push_back(e+1);
                   return ans;
               }
           }
        }
        return {-1};
    }
};
```



>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
