## 思路

**解法一：** 

使用set

```c++
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        unordered_set<int> s;
        for (auto& x : nums) {
            if (s.count(x)) {
                return x;
            }
            s.insert(x);
        }
        return 0;
    }
};
//时间复杂度O(n)
//空间复杂度O(n)
```



**解法二** 

```
初始时

下标：0 1 2 3 4 5 6

数值：2 3 1 0 2 5 3

由于nums[0]的值为2，nums[2]的值不为2，交换nums[0]与nums[2]

得到：1 3 2 0 2 5 3

此时nums[0] = 1，nums[1] != 1，交换nums[0]与nums[1]

->3 1 2 0 2 5 3，
->0 1 2 3 2 5 3
此时到nums[4] = 2 = nums[2]，所以2为重复的数字
```

```c++
class Solution {
public:
    int findRepeatNumber(vector<int>& nums) {
        for (int i = 0; i < nums.size(); i ++ ) {
            while (nums[i] != i) {
                if (nums[i] == nums[nums[i]]) return nums[i];
                swap(nums[i], nums[nums[i]]);
            }
        }
        return 0;
    }
};
//时间复杂度O(n)
//空间复杂度O(1)
```



