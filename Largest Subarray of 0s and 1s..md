
# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array arr of 0s and 1s. Find and return the length of the longest subarray with equal number of 0s and 1s.



# 📝Code ⬇:-



# Java
```java []

class Solution {
    public int maxLen(int[] arr) {
        Map<Integer, Integer> map = new HashMap<>();
        int sum = 0, maxLen = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += (arr[i] == 0) ? -1 : 1;
            if (sum == 0) maxLen = i + 1;
            else if (map.containsKey(sum)) maxLen = Math.max(maxLen, i - map.get(sum));
            else map.put(sum, i);
        }
        return maxLen;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int maxLen(vector<int>& arr) {
        unordered_map<int, int> hM;
        int sum = 0, max_len = 0;
        for (int i = 0; i < arr.size(); i++) {
            sum += (arr[i] == 0) ? -1 : 1;
            if (sum == 0) max_len = i + 1;
            if (hM.count(sum)) max_len = max(max_len, i - hM[sum]);
            else hM[sum] = i;
        }
        return max_len;
    }
};
```

# Python
``` python []

class Solution:
    def maxLen(self, arr):
        hmap = {}
        sum, max_len = 0, 0
        for i in range(len(arr)):
            sum += -1 if arr[i] == 0 else 1
            if sum == 0:
                max_len = i + 1
            elif sum in hmap:
                max_len = max(max_len, i - hmap[sum])
            else:
                hmap[sum] = i
        return max_len
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
