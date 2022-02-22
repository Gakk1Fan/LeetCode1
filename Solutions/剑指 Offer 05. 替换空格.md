## 代码

```c++
class Solution {
public:
    string replaceSpace(string s) {
        string str;
        for (auto c : s) {
            if (c == ' ') str += "%20";
            else str += c;
        }
        return str;
    }
};
//时间复杂度O(n)
//空间复杂度O(1)
```

