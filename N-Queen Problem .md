# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
The n-queens puzzle is the problem of placing n queens on a (n × n) chessboard such that no two queens can attack each other. Note that two queens attack each other if they are placed on the same row, the same column, or the same diagonal.

Given an integer n, find all distinct solutions to the n-queens puzzle.
You can return your answer in any order but each solution should represent a distinct board configuration of the queen placements, where the solutions are represented as permutations of [1, 2, 3, ..., n]. In this representation, the number in the ith position denotes the row in which the queen is placed in the ith column.
For eg. below figure represents a chessboard [3 1 4 2].


# 📝Code ⬇:-



# Java
```java []

class Solution {
    public ArrayList<ArrayList<Integer>> nQueen(int n) {
        if (n < 4 && n != 1) return new ArrayList<>();
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        int[] row = new int[n];
        solve(0, 0, 0, 0, n, row, res);
        return res;
    }

    private void solve(int c, int cols, int d1, int d2, int n, int[] row, ArrayList<ArrayList<Integer>> res) {
        if (c == n) {
            ArrayList<Integer> temp = new ArrayList<>();
            for (int r : row) temp.add(r + 1);
            res.add(temp);
            return;
        }
        for (int r = 0, pos = 1; r < n; ++r, pos <<= 1) 
            if ((cols & pos) == 0 && (d1 & (pos << c)) == 0 && (d2 & (pos << (n - 1 - c))) == 0) {
                row[c] = r;
                solve(c + 1, cols | pos, d1 | (pos << c), d2 | (pos << (n - 1 - c)), n, row, res);
            }
    }
}

```

# C++
``` cpp []

class Solution {
public:
    vector<vector<int>> nQueen(int n) {
        if (n < 4 && n != 1) return {};
        vector<vector<int>> res;
        vector<int> row(n);

        auto solve = [&](auto&& self, int c, int cols, int d1, int d2) -> void {
            if (c == n) { res.push_back(row); return; }
            for (int r = 0, pos = 1; r < n; ++r, pos <<= 1) 
                if (!(cols & pos || d1 & (pos << c) || d2 & (pos << (n - 1 - c)))) 
                    row[c] = r + 1, self(self, c + 1, cols | pos, d1 | (pos << c), d2 | (pos << (n - 1 - c)));
        };

        solve(solve, 0, 0, 0, 0);
        return res;
    }
};
```

# Python
``` python []

class Solution:
    def nQueen(self, n):
        if n < 4 and n != 1:
            return []
        res = []
        row = [0] * n

        def solve(c, cols, d1, d2):
            if c == n:
                res.append([r + 1 for r in row])
                return
            for r in range(n):
                pos = 1 << r
                if not (cols & pos or d1 & (pos << c) or d2 & (pos << (n - 1 - c))):
                    row[c] = r
                    solve(c + 1, cols | pos, d1 | (pos << c), d2 | (pos << (n - 1 - c)))

        solve(0, 0, 0, 0)
        return res
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
