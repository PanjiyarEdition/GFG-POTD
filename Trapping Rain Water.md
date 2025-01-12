# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array arr[] with non-negative integers representing the height of blocks. If the width of each block is 1, compute how much water can be trapped between the blocks during the rainy season. 


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public int maxWater(int[] arr) {
        int l = 0, r = arr.length - 1, res = 0, lMax = 0, rMax = 0;
        while (l < r) {
            if (arr[l] < arr[r]) {
                lMax = lMax > arr[l] ? lMax : arr[l];
                res += lMax - arr[l++];
            } else {
                rMax = rMax > arr[r] ? rMax : arr[r];
                res += rMax - arr[r--];
            }
        }
        return res;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int maxWater(vector<int>& arr) {
        int l = 0, r = arr.size() - 1, res = 0, lMax = 0, rMax = 0;
        while (l < r) {
            arr[l] < arr[r] ? (lMax = max(lMax, arr[l]), res += lMax - arr[l++]) : (rMax = max(rMax, arr[r]), res += rMax - arr[r--]);
        }
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def maxWater(self, arr):
        l, r, res, lMax, rMax = 0, len(arr) - 1, 0, 0, 0
        while l < r:
            if arr[l] < arr[r]: res += max(0, lMax - arr[l]); lMax = max(lMax, arr[l]); l += 1
            else: res += max(0, rMax - arr[r]); rMax = max(rMax, arr[r]); r -= 1
        return res  
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
