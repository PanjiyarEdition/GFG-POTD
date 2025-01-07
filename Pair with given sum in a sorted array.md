# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
You are given an integer target and an array arr[]. You have to find number of pairs in arr[] which sums up to target. It is given that the elements of the arr[] are in sorted order.
Note: pairs should have elements of distinct indexes. 


# 📝Code ⬇:-



# Java
```java []

class Solution {
    int countPairs(int[] arr, int target) {
        HashMap<Integer, Integer> freq = new HashMap<>();
        int res = 0;

        for (int num : arr) {
            res += freq.getOrDefault(target - num, 0);
            freq.put(num, freq.getOrDefault(num, 0) + 1);
        }

        return res;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    int countPairs(vector<int>& arr, int target) {
        unordered_map<int, int> freq;
        int res = 0;

        for (int num : arr) {
            int complement = target - num;
            if (freq.count(complement)) 
                res += freq[complement];
            
            freq[num]++;
        }

        return res;
    }
};
```

# Python
``` python []

class Solution:
    def countPairs(self, arr, target):
        freq = {}
        res = 0

        for num in arr:
            res += freq.get(target - num, 0)
            freq[num] = freq.get(num, 0) + 1

        return res
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
