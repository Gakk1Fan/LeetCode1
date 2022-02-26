## 代码

```c++
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        if (prices.size() == 0) return 0;
        int minP = prices[0];
        int maxP = 0;
        for (int i = 1; i < prices.size(); i ++ ) {
            //求出当日卖出的利润
            maxP = max(maxP, prices[i] - minP);
            //更新买入最小值
            minP = min(minP, prices[i]);
        }
        return maxP;
    }
};
//时间复杂度O(n)
//空间复杂度O(1)
```

