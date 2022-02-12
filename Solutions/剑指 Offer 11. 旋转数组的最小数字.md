## 思路

有序数组旋转后，有两个部分，都是单调不减。

先删除后半部分最后等于nums[0]的数，然后采用二分。

```c++
class Solution {
public:
    int minArray(vector<int>& nums) {
        int n = nums.size() - 1;
        while (n > 0 && nums[0] == nums[n]) n -- ;
        if (nums[n] >= nums[0]) return nums[0];
        int l = 0, r = n;
        while (l < r) {
            int mid = (l + r) / 2;
            if (nums[mid] >= nums[0]) l = mid + 1;
            else r = mid;
        }
        return nums[l];
    }
};
//时间复杂度O(logn)
//空间复杂度O(1)
```

