# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array arr[] and a number target, find a pair of elements (a, b) in arr[], where a<=b whose sum is closest to target.
Note: Return the pair in sorted order and if there are multiple such pairs return the pair with maximum absolute difference. If no such pair exists return an empty array.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public List<Integer> sumClosest(int[] arr, int target) {
        Arrays.sort(arr);
        int l = 0, r = arr.length - 1, minDiff = Integer.MAX_VALUE;
        List<Integer> res = new ArrayList<>();
        while (l < r) {
            int sum = arr[l] + arr[r], diff = Math.abs(target - sum);
            if (diff < minDiff) {
                minDiff = diff;
                res = Arrays.asList(arr[l], arr[r]);
            }
            if (sum < target) l++;
            else r--;
        }
        return res;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    vector<int> sumClosest(vector<int>& arr, int target) {
        sort(arr.begin(), arr.end());
        vector<int> res;
        for (int l = 0, r = arr.size() - 1, minDiff = INT_MAX; l < r;) {
            int sum = arr[l] + arr[r], diff = abs(target - sum);
            if (diff < minDiff) minDiff = diff, res = {arr[l], arr[r]};
            sum < target ? ++l : --r;
        }
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def sumClosest(self, arr, target):
        arr.sort()
        l, r, minDiff, res = 0, len(arr) - 1, float('inf'), []
        while l < r:
            s = arr[l] + arr[r]
            if abs(target - s) < minDiff:
                minDiff, res = abs(target - s), [arr[l], arr[r]]
            l += s < target
            r -= s >= target
        return res 
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
