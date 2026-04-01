# leetcode-notes

## 数组

### 二分查找

二分查找需要先讲一下方法论，主要是针对区间以及搜索算法。简单说，不理解为元素查找，而理解为位置查找。直接采用算竞的模板
- 区间的写法
    - 合法区间[low, high]
    - 判断区间[low, high)
    - 拓展，引入非法位置，即[low, high + 1)，引入一个非法下标，处理无解的情形。
    - 如果用higher_bound作为主算法，下标区间拓展为[low-1, high)
- 搜索算法的写法
    - lower_bound or upper_bound都行。
    - lower_bound: 在序列中找到x <= ele的数中最小的一个。所以，向左查找，是下界，lower bound.，向下界寻找。
    - upper_bound: 在序列中找到x >= ele的数中最大的一个。所以，是上界，upper bound. 向上界寻找。

```cpp
int lower_bound(const std::vector<int>& nums, int low, int high, int x) {
  while (low < high) {
    int mid = low + (high - low) / 2;  // (low + high) >> 1
    if (x <= nums[mid]) high = mid;
    else low = mid + 1;
  }
  return low;
}

/**
[2,3,5] x = 1
low = 0, high = 3, mid = 1
low = 0, high = 1, mid = 0
low = 0, high = 0,
*/

int higher_bound(const std::vector<int>& nums, int low, int high, int x) {
  while (low < high) {
    int mid = low + (high - low) / 2 + 1;  // (low + high + 1) >> 1
    if (nums[mid] <= x) low = mid;
    else high = mid - 1;
  }
  return low;
}
```

### 双指针

#### [704. Binary Search](https://leetcode.com/problems/binary-search/description/)

- 一刷
    - 思路：标准二分，采用lower_bound.
    - 注意点，lower_bound是找位置，不是找元素。下面情况需要处理
        - 位置不合法。(只能右侧不合法)
        - 位置合法，但元素不是target，不一定找到。

```cpp
class Solution {
public:
    int search(vector<int>& nums, int target) {
        auto pos = lower_bound(nums, 0, nums.size(), target);
        if (pos >= nums.size()) return -1;
        if (nums[pos] != target) return -1;
        return pos;
    }
private:
    int lower_bound(const vector<int>& nums, int low, int high, int x) {
        while (low < high) {
            int mid = low + (high - low) / 2;
            if (x <= nums[mid]) { high = mid; }
            else {low = mid + 1;}
        }
        return low;
    }
};
```

#### [27. Remove Element](https://leetcode.com/problems/remove-element/description/)
- 一刷
    - 我的思路：一眼双指针，这类题就是把一类数据放到一段，把另一类放到另一端。两根指针分别移动即可。
    - 不过这个题小细节挺多
        - 数组问题，边界处理好。
        - 最后返回left，不是right，因为它需要个数。
    - 最优解：快慢指针。最优解注意到我没有注意到的一点是，另一端的数据，其实它不care，所以慢指针直接被覆盖就好。
        - 快指针寻找迁移元素，慢指针留在替换位置。
        - 线性时间复杂度。

```cpp
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int len = nums.size();
        int left = 0, right = len - 1;
        int k = 0;
        while (left <= right) {
            while (left < len and nums[left] != val) {
                ++left;
            }
            while (0 <= right and nums[right] == val) {
                --right;
            }
            if (left < right) {
                std::swap(nums[left], nums[right]);
            }
        }
        return left;
    }
};
```

```cpp
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int len = nums.size();
        int fast = 0, slow = 0;
        while (fast < len) {
            if (nums[fast] == val) fast++;
            else nums[slow++] = nums[fast++];
        }
        return slow;
    }
};
```

#### [977. Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/submissions/1965807869/)

- 一刷
    - 我的思路：遍历平方，排序。非最优。
    - 最优解：双指针
        - 题目特点：**数组有序，这说明最大值只会出现在两侧**。
        - 解法：双指针在两次进行遍历即可。
        - 时间复杂度线性
        - 细节：数组问题，处理好边界的问题。

```cpp
class Solution {
public:
    vector<int> sortedSquares(vector<int>& nums) {
        vector<int> result(nums.size(), 0);
        int left = 0;
        int right = nums.size() - 1;
        int k = right;
        while (left <= right) {
            auto left_val = nums[left] * nums[left];
            auto right_val = nums[right] * nums[right];
            if (left_val < right_val) { result[k--] = right_val; --right;}
            else { result[k--] = left_val; ++left;}
        }
        return result;
    }
};
```