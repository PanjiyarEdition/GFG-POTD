# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an integer array arr[]. Find the number of triangles that can be formed with three different array elements as lengths of three sides of the triangle. 

A triangle with three given sides is only possible if sum of any two sides is always greater than the third side.

# 📝Code ⬇:-



# Java
```java []

class Solution {
    static int countTriangles(int[] arr) {
        Arrays.sort(arr);
        int count = 0, n = arr.length;
        for (int i = n - 1; i >= 2; --i) {
            int l = 0, r = i - 1;
            while (l < r) {
                if (arr[l] + arr[r] > arr[i]) count += (r-- - l);
                else ++l;
            }
        }
        return count;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int countTriangles(vector<int>& arr) {
        sort(arr.begin(), arr.end());
        int cnt = 0;
        for (int i = arr.size() - 1; i >= 2; --i)
            for (int l = 0, r = i - 1; l < r; arr[l] + arr[r] > arr[i] ? cnt += r-- - l : ++l);
        return cnt;
    }
};
```

# Python
``` python []

class Solution:
    def countTriangles(self, arr):
        arr.sort()
        n, count = len(arr), 0
        for i in range(n - 1, 1, -1):
            l, r = 0, i - 1
            while l < r:
                if arr[l] + arr[r] > arr[i]:
                    count += r - l
                    r -= 1
                else:
                    l += 1
        return count   
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
