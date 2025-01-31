# 📍Description ➡:-
<!-- Describe your first thoughts on how to solve this problem. -->
Given an incomplete Sudoku configuration in terms of a 9x9  2-D interger square matrix, mat[][], the task is to solve the Sudoku. It is guaranteed that the input Sudoku will have exactly one solution.

A sudoku solution must satisfy all of the following rules:

Each of the digits 1-9 must occur exactly once in each row.
Each of the digits 1-9 must occur exactly once in each column.
Each of the digits 1-9 must occur exactly once in each of the 9 3x3 sub-boxes of the grid.
Note: Zeros represent blanks to be filled with numbers 1-9, while non-zero cells are fixed and cannot be changed.


# 📝Code ⬇:-



# Java
```java []

class Solution {
    static void solveSudoku(int[][] b) {
        int[] r = new int[9], c = new int[9], box = new int[9];
        for (int i = 0; i < 9; i++)
            for (int j = 0; j < 9; j++)
                if (b[i][j] != 0) {
                    int m = 1 << b[i][j], idx = i / 3 * 3 + j / 3;
                    r[i] |= m; c[j] |= m; box[idx] |= m;
                }
        solve(b, r, c, box, 0, 0);
    }

    static boolean solve(int[][] b, int[] r, int[] c, int[] box, int i, int j) {
        if (i == 9) return true;
        if (j == 9) return solve(b, r, c, box, i + 1, 0);
        if (b[i][j] != 0) return solve(b, r, c, box, i, j + 1);
        for (int num = 1, m; num <= 9; num++) {
            m = 1 << num;
            int idx = i / 3 * 3 + j / 3;
            if ((r[i] & m) != 0 || (c[j] & m) != 0 || (box[idx] & m) != 0) continue;
            b[i][j] = num; r[i] |= m; c[j] |= m; box[idx] |= m;
            if (solve(b, r, c, box, i, j + 1)) return true;
            b[i][j] = 0; r[i] &= ~m; c[j] &= ~m; box[idx] &= ~m;
        }
        return false;
    }
}

```

# C++
``` cpp []

class Solution {
public:
    void solveSudoku(vector<vector<int>> &board) {
        vector<int> row(9, 0), col(9, 0), box(9, 0);
        for (int i = 0; i < 9; i++)
            for (int j = 0; j < 9; j++)
                if (board[i][j])
                    row[i] |= 1 << board[i][j], col[j] |= 1 << board[i][j], box[i / 3 * 3 + j / 3] |= 1 << board[i][j];
        solve(board, row, col, box, 0, 0);
    }

private:
    bool solve(vector<vector<int>> &board, vector<int> &row, vector<int> &col, vector<int> &box, int i, int j) {
        if (i == 9) return true;
        if (j == 9) return solve(board, row, col, box, i + 1, 0);
        if (board[i][j]) return solve(board, row, col, box, i, j + 1);
        for (int num = 1; num <= 9; num++) {
            int mask = 1 << num, idx = i / 3 * 3 + j / 3;
            if (row[i] & mask || col[j] & mask || box[idx] & mask) continue;
            board[i][j] = num, row[i] |= mask, col[j] |= mask, box[idx] |= mask;
            if (solve(board, row, col, box, i, j + 1)) return true;
            board[i][j] = 0, row[i] &= ~mask, col[j] &= ~mask, box[idx] &= ~mask;
        }
        return false;
    }
};
```

# Python
``` python []

class Solution:
    def solveSudoku(self, b):
        r, c, box = [0] * 9, [0] * 9, [0] * 9
        for i in range(9):
            for j in range(9):
                if b[i][j]:
                    m = 1 << b[i][j]
                    r[i] |= m; c[j] |= m; box[i // 3 * 3 + j // 3] |= m
        self.solve(b, r, c, box, 0, 0)
    
    def solve(self, b, r, c, box, i, j):
        if i == 9: return True
        if j == 9: return self.solve(b, r, c, box, i + 1, 0)
        if b[i][j]: return self.solve(b, r, c, box, i, j + 1)
        for num in range(1, 10):
            m = 1 << num
            idx = i // 3 * 3 + j // 3
            if r[i] & m or c[j] & m or box[idx] & m: continue
            b[i][j] = num; r[i] |= m; c[j] |= m; box[idx] |= m
            if self.solve(b, r, c, box, i, j + 1): return True
            b[i][j] = 0; r[i] &= ~m; c[j] &= ~m; box[idx] &= ~m
        return False 
```

---

>    **Coded** By $$Panjiyar EDITION 🖋  $$

               
