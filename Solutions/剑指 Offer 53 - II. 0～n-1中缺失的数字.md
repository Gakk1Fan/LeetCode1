```c++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        if (nums[nums.size() - 1] == nums.size() - 1) return nums.size();
        int l = 0, r = nums.size() - 1;
        while (l < r) {
            int mid = (l + r) / 2;
            if (nums[mid] > mid) r = mid;
            else l = mid + 1;
        }
        return l;
    }
};
```

