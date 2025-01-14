# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array of integers arr[], the task is to find the first equilibrium point in the array.

The equilibrium point in an array is an index (0-based indexing) such that the sum of all elements before that index is the same as the sum of elements after it. Return -1 if no such point exists. 


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public static int findEquilibrium(int[] arr) {
        long sum = Arrays.stream(arr).asLongStream().sum(), sum2 = 0;
        for (int i = 0; i < arr.length; sum2 += arr[i++])
            if ((sum -= arr[i]) == sum2) return i;
        return -1;
    }
}
```

# C++
``` cpp []

class Solution {
public:
    int findEquilibrium(vector<int>& arr) {
        for (long long sum = accumulate(arr.begin(), arr.end(), 0LL), sum2 = 0, i = 0; i < arr.size(); sum2 += arr[i++])
            if ((sum -= arr[i]) == sum2) return i;
        return -1;
    }
};
```

# Python
``` python []

class Solution:
    def findEquilibrium(self, arr):
        total, prefix = sum(arr), 0
        for i, val in enumerate(arr):
            total -= val
            if prefix == total:
                return i
            prefix += val
        return -1
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
