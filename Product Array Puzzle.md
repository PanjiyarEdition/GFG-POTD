# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given an array arr[] of size n. Your task is to construct an array res[] such that res[i] is equal to the product of all the elements of arr[] except arr[i]. Return the resultant array res[].
Note: Each element in res[] lies within the 32-bit integer range.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public static int[] productExceptSelf(int[] arr) {
        int n = arr.length, product = 1, zeroCount = 0;
        for (int x : arr) if (x == 0) zeroCount++; else product *= x;
        if (zeroCount > 1) return new int[n];
        for (int i = 0; i < n; i++) 
            arr[i] = zeroCount > 0 ? (arr[i] == 0 ? product : 0) : product / arr[i];
        return arr;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    vector<int> productExceptSelf(vector<int>& arr) {
        int n = arr.size(), product = 1, zeroCount = count(arr.begin(), arr.end(), 0);
        if (zeroCount > 1) return vector<int>(n, 0);
        for (int x : arr) if (x) product *= x;
        for (int i = 0; i < n; i++) arr[i] = zeroCount ? (arr[i] ? 0 : product) : product / arr[i];
        return arr;
    }
};
```

# Python
``` python []

class Solution:
    def productExceptSelf(self, arr):
        product, zero_count = 1, arr.count(0)
        if zero_count > 1:
            return [0] * len(arr)
        for x in arr:
            if x != 0:
                product *= x
        return [product if x == 0 else 0 if zero_count else product // x for x in arr]
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
