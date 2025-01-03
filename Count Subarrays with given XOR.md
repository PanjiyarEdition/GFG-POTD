# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array of integers arr[] and a number k, count the number of subarrays having XOR of their elements as k.


# 📝Code ⬇:-




# C++
``` cpp []

class Solution {
public:
    long subarrayXor(vector<int> &arr, int k) {
        long res = 0, prefXOR = 0;
        unordered_map<int, int> mp;
        for (int val : arr) {
            prefXOR ^= val;
            res += mp[prefXOR ^ k] + (prefXOR == k);
            mp[prefXOR]++;
        }
        return res;
    }
};

```


---

>    **Coded** By $$Panjiyar EDITION 🖋 date $$

               
