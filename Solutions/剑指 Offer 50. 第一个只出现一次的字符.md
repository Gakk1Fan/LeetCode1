## 代码

```c++ 
class Solution {
public:
    char firstUniqChar(string s) {
        unordered_map<char, int> cnt;
        for (char c : s) {
            cnt[c] ++ ;
        }
        for (char c : s) {
            if (cnt[c] == 1) return c;
        }
        return ' ';
    }
};
//时间复杂度O(n)
//空间复杂度O(26)
```

