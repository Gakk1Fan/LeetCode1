## 思路

```c++
从右上方开始遍历
    如果等于target，返回true;
	如果大于target，遍历前一列;
	如果小于target，遍历下一行
```



## 代码

```c++
class Solution {
public:
    bool findNumberIn2DArray(vector<vector<int>>& matrix, int target) {
        int cols = matrix.size();
        if (cols == 0) return false;
        int rows = matrix[0].size();
        int col = 0, row = rows - 1;
        while (col <= cols - 1 && row >= 0) {
            if (matrix[col][row] == target) return true;
            else if (matrix[col][row] > target) row -- ;
            else col ++ ;
        }
        return false;
    }
};
//时间复杂度O(m+n)
//空间复杂度O(1)
```

