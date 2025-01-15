# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array arr[] containing integers and an integer k, your task is to find the length of the longest subarray where the sum of its elements is equal to the given value k. If there is no subarray with sum equal to k, return 0.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public int longestSubarray(int[] arr, int k) {
        Map<Integer, Integer> mp = new HashMap<>();
        int sum = 0, res = 0;
        for (int i = 0; i < arr.length; ++i) {
            if ((sum += arr[i]) == k) res = i + 1;
            if (mp.containsKey(sum - k)) res = Math.max(res, i - mp.get(sum - k));
            mp.putIfAbsent(sum, i);
        }
        return res;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int longestSubarray(vector<int>& arr, int k) {
        unordered_map<int, int> mp;
        int sum = 0, res = 0;
        for (int i = 0; i < arr.size(); ++i) {
            sum += arr[i];
            if (sum == k) res = i + 1;
            if (mp.count(sum - k)) res = max(res, i - mp[sum - k]);
            if (!mp.count(sum)) mp[sum] = i;
        }
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def longestSubarray(self, arr, k):
        mp, sum, res = {}, 0, 0
        for i, num in enumerate(arr):
            sum += num
            if sum == k:
                res = i + 1
            if sum - k in mp:
                res = max(res, i - mp[sum - k])
            mp.setdefault(sum, i)
        return res   
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
