# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array arr[] and an integer target. You have to find the number of pairs in the array whose sum is strictly less than the target.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    int countPairs(int[] arr, int target) {
        Arrays.sort(arr);
        int l = 0, r = arr.length - 1, ans = 0;
        while (l < r) if (arr[l] + arr[r] < target) ans += (r - l++);
        else r--;
        return ans;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int countPairs(vector<int>& arr, int target) {
        sort(arr.begin(), arr.end());
        int l = 0, r = arr.size() - 1, ans = 0;
        while (l < r) (arr[l] + arr[r] < target) ? ans += (r - l), l++ : r--;
        return ans;
    }
};
```

# Python
``` python []

class Solution:
    def countPairs(self, arr, target):
        arr.sort()
        l, r, ans = 0, len(arr) - 1, 0
        while l < r:
            if arr[l] + arr[r] < target: ans += (r - l); l += 1
            else: r -= 1
        return ans
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
