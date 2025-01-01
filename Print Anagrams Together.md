# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an array of strings, return all groups of strings that are anagrams. The groups must be created in order of their appearance in the original array. Look at the sample case for clarification.
Note: The final output will be in lexicographic order. 

<date> - 01/01/2025 </date>


# 📝Code ⬇:-



# C++
``` cpp []

class Solution {
  public:
    vector<vector<string>> anagrams(vector<string>& arr) {
        //CodeGenius
        unordered_map<string,vector<string>>mp;
        for(int i=0;i<arr.size();i++){
            string temp=arr[i];
            sort(temp.begin(),temp.end());
            mp[temp].push_back(arr[i]);
        }
        vector<vector<string>>ans;
        for(auto it:mp){
            ans.push_back(it.second);
        }
        return ans;
    }
};
```



---

>    **Coded** By $$Panjiyar EDITION$$

               
