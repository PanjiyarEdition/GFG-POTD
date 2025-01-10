# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an integer array arr[] and a number k. Find the count of distinct elements in every window of size k in the array.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    ArrayList<Integer> countDistinct(int arr[], int k) {
        HashMap<Integer, Integer> freq = new HashMap<>();
        ArrayList<Integer> res = new ArrayList<>();
        for (int i = 0; i < arr.length; i++) {
            freq.put(arr[i], freq.getOrDefault(arr[i], 0) + 1);
            if (i >= k - 1) {
                res.add(freq.size());
                freq.put(arr[i - k + 1], freq.get(arr[i - k + 1]) - 1);
                if (freq.get(arr[i - k + 1]) == 0) freq.remove(arr[i - k + 1]);
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
    vector<int> countDistinct(vector<int> &arr, int k) {
        unordered_map<int, int> freq;
        vector<int> res;
        for (int i = 0; i < arr.size(); i++) {
            freq[arr[i]]++;
            if (i >= k - 1) {
                res.push_back(freq.size());
                if (--freq[arr[i - k + 1]] == 0) freq.erase(arr[i - k + 1]);
            }
        }
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def countDistinct(self, arr, k):
        freq = {}
        res = []
        for i in range(len(arr)):
            freq[arr[i]] = freq.get(arr[i], 0) + 1
            if i >= k - 1:
                res.append(len(freq))
                freq[arr[i - k + 1]] -= 1
                if freq[arr[i - k + 1]] == 0:
                    del freq[arr[i - k + 1]]
        return res
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
