```c++
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int res = -1e9;
        int cursum = 0;
        for (int i = 0; i < nums.size(); i ++ ) {
            if (cursum <= 0) {
                cursum = 0;
            }
            cursum += nums[i];
            res = max(res, cursum);
        }
        return res;
    }
};
```

