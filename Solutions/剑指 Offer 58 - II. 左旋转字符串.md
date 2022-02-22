## 代码

```c++
class Solution {
public:
    string reverseLeftWords(string s, int n) {
        s = s.substr(n, s.size()) + s.substr(0, n);
        return s;
    }
};
//时间复杂度O(n)
//空间复杂度O(1)
```

