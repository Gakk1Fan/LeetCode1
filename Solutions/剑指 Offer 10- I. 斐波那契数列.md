## 代码

```c++
class Solution {
public:
    int fib(int n) {
        int a = 0, b = 1;
        const int P = 1e9 + 7;
        while ( n -- ) {
            int c = (a + b) % P;
            a = b;
            b = c;
        }
        return a;
    }
};
```

