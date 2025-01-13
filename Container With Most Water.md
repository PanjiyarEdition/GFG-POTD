# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array arr[] of non-negative integers, where each element arr[i] represents the height of the vertical lines, find the maximum amount of water that can be contained between any two lines, together with the x-axis.

Note: In the case of a single vertical line it will not be able to hold water.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public int maxWater(int[] arr) {
        int l = 0, r = arr.length - 1, res = 0;
        while (l < r) res = Math.max(res, (r - l) * (arr[l] < arr[r] ? arr[l++] : arr[r--]));
        return res;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int maxWater(vector<int>& arr) {
        int l = 0, r = arr.size() - 1, res = 0;
        while (l < r) res = max(res, (r - l) * (arr[l] < arr[r] ? arr[l++] : arr[r--]));
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def maxWater(self, arr):
        l, r, res = 0, len(arr) - 1, 0
        while l < r:
            res = max(res, (r - l) * (arr[l] if arr[l] < arr[r] else arr[r]))
            l, r = (l + 1, r) if arr[l] < arr[r] else (l, r - 1)
        return res
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
