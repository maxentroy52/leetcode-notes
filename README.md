# leetcode-notes

<!-- toc -->

- [数组](#%E6%95%B0%E7%BB%84)
  * [二分查找](#%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE)
    + [704. Binary Search](#704-binary-search)
    + [35. Search Insert Position](#35-search-insert-position)
    + [34. Find First and Last Position of Element in Sorted Array](#34-find-first-and-last-position-of-element-in-sorted-array)
  * [双指针](#%E5%8F%8C%E6%8C%87%E9%92%88)
    + [27. Remove Element](#27-remove-element)
    + [977. Squares of a Sorted Array](#977-squares-of-a-sorted-array)
    + [209. Minimum Size Subarray Sum](#209-minimum-size-subarray-sum)
    + [1. Two Sum](#1-two-sum)
    + [15. 3Sum](#15-3sum)
    + [18. 4Sum](#18-4sum)
  * [基础](#%E5%9F%BA%E7%A1%80)
    + [59. Spiral Matrix II](#59-spiral-matrix-ii)
- [链表](#%E9%93%BE%E8%A1%A8)
  * [基础](#%E5%9F%BA%E7%A1%80-1)
    + [203. Remove Linked List Elements](#203-remove-linked-list-elements)
    + [707. Design Linked List](#707-design-linked-list)
    + [206. Reverse Linked List](#206-reverse-linked-list)
    + [24. Swap Nodes in Pairs](#24-swap-nodes-in-pairs)
  * [双指针](#%E5%8F%8C%E6%8C%87%E9%92%88-1)
    + [19. Remove Nth Node From End of List](#19-remove-nth-node-from-end-of-list)
    + [160. Intersection of Two Linked Lists](#160-intersection-of-two-linked-lists)
    + [141. Linked List Cycle](#141-linked-list-cycle)
    + [142. Linked List Cycle II](#142-linked-list-cycle-ii)
- [哈希表](#%E5%93%88%E5%B8%8C%E8%A1%A8)
  * [基础](#%E5%9F%BA%E7%A1%80-2)
    + [242. Valid Anagram](#242-valid-anagram)
    + [349. Intersection of Two Arrays](#349-intersection-of-two-arrays)
    + [350. Intersection of Two Arrays II](#350-intersection-of-two-arrays-ii)
    + [202. Happy Number](#202-happy-number)
    + [1. Two Sum](#1-two-sum-1)
    + [454. 4Sum II](#454-4sum-ii)
    + [383. Ransom Note](#383-ransom-note)
- [字符串](#%E5%AD%97%E7%AC%A6%E4%B8%B2)
  * [基础](#%E5%9F%BA%E7%A1%80-3)
    + [344. Reverse String](#344-reverse-string)
    + [541. Reverse String II](#541-reverse-string-ii)
    + [151. Reverse Words in a String](#151-reverse-words-in-a-string)
    + [28. Find the Index of the First Occurrence in a String](#28-find-the-index-of-the-first-occurrence-in-a-string)
    + [459. Repeated Substring Pattern](#459-repeated-substring-pattern)
- [栈和队列](#%E6%A0%88%E5%92%8C%E9%98%9F%E5%88%97)
  * [基础](#%E5%9F%BA%E7%A1%80-4)
    + [232. Implement Queue using Stacks](#232-implement-queue-using-stacks)
    + [225. Implement Stack using Queues](#225-implement-stack-using-queues)
    + [20. Valid Parentheses](#20-valid-parentheses)
    + [1047. Remove All Adjacent Duplicates In String](#1047-remove-all-adjacent-duplicates-in-string)
    + [150. Evaluate Reverse Polish Notation](#150-evaluate-reverse-polish-notation)
- [二叉树](#%E4%BA%8C%E5%8F%89%E6%A0%91)
  * [基本](#%E5%9F%BA%E6%9C%AC)
    + [144. Binary Tree Preorder Traversal](#144-binary-tree-preorder-traversal)
    + [94. Binary Tree Inorder Traversal](#94-binary-tree-inorder-traversal)
    + [145. Binary Tree Postorder Traversal](#145-binary-tree-postorder-traversal)

<!-- tocstop -->

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
    - lower_bound: 在序列中找到x <= ele的数中最小的一个。所以，向左查找，是下界，lower bound，向下界寻找。
    - upper_bound: 在序列中找到x >= ele的数中最大的一个。所以，是上界，upper bound，向上界寻找。

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

#### [35. Search Insert Position](https://leetcode.com/problems/search-insert-position/submissions/1966719953/)

- 一刷
    - 我的思路：二分查位置。
    - 注意：704需要的两个注意点，即位置非法和查不到，本题都不用关心。

```cpp
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        return lower_bound(nums, 0, nums.size(), target);
    }
    int lower_bound(const vector<int>& nums, int low, int high, int x) {
        while (low < high) {
            int mid = low + (high - low) / 2;
            if (x <= nums[mid]) high = mid;
            else low = mid + 1;
        }
        return low;
    }
};
```

#### [34. Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)

- 一刷
    - 我的思路：套模板，同时需要lower_bound and upper_bound.
    - 注意点：这个题是查元素，不是查位置。所以和704一样，需要避免两种情况。
    - 位置非法 or 位置合法但元素不存在
    - [low, high + 1) and [low - 1, high)，多给一个非法位置

```cpp
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        vector<int> res(2, -1);
        auto b = lower_bound(nums, 0, nums.size(), target);
        auto e = upper_bound(nums, -1, nums.size() - 1, target);

        if (b == nums.size() or nums[b] != target) res[0] = -1;
        else res[0] = b;

        if (e == -1 or nums[e] != target) res[1] = -1;
        else res[1] = e;

        return res;
    }
    int lower_bound(vector<int>& nums, int low, int high, int x) {
        while (low < high) {
            int mid = low + (high - low) / 2;
            if (x <= nums[mid]) high = mid;
            else low = mid + 1;
        }
        return low;
    }
     int upper_bound(vector<int>& nums, int low, int high, int x) {
        while (low < high) {
            int mid = low + (high - low) / 2 + 1;
            if (nums[mid] <= x) low = mid;
            else high = mid - 1;
        }
        return low;
    }   
};
```

### 双指针

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

#### [209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)

- 一刷
    - 我的思路：枚举subarray, O(n^2)
    - 难点：线性时间复杂度下，不知道怎么枚举subarray
    - 最优解：双指针枚举subrarray
        - 既然线性时间复杂度，只能有一个for-range-loop
        - left控制起点，right控制终点。遍历right,
        - left根据sum是否大于target，进行退场操作。
        - 有点快慢指针的意思
        - 每个元素，进场一次，出场一次。所以线性

```cpp
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int res = INT32_MAX;
        int sum = 0;
        for (int left = 0, right = 0; right < nums.size(); ++right) {
            sum += nums[right];
            while (sum >= target) {
                int len = right - left + 1;
                res = len < res?len:res;
                sum -= nums[left++];
            }
        }
        return res==INT32_MAX?0:res;
    }
};
```

#### [1. Two Sum](https://leetcode.com/problems/two-sum/)

**双指针解法本身并不强制要求排序，但在这个特定问题中，排序是为了让双指针能够正确工作**。

- 双指针的核心原理
    - 双指针算法的正确性依赖于数据的单调性：
    - 当数组有序时，我们可以根据 sum 与 target 的比较结果，确定性地移动指针：
        - sum < target → 需要更大的数 → left++
        - sum > target → 需要更小的数 → right--
- left/right只是两个数的指针，不代表区间
- 这个题最优解还是哈希表，时间O(n)，空间O(n). 双指针主要开销在排序上，空间和哈希表一致。

```cpp
class Solution {
public:
    struct Node {
        int val = 0;
        int idx = 0;
        Node (int v, int i) : val(v), idx(i) {}

        bool operator<(const auto& rhs) const {
            return val < rhs.val;
        }
    }; 

    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> ret;
        vector<Node> nodes;
        for (int i = 0; i < nums.size(); ++i) { nodes.emplace_back(nums[i], i); }
        std::sort(nodes.begin(), nodes.end());
        
        int left = 0, right = nums.size() - 1;
        while (left < right) {
            int cur = nodes[left].val + nodes[right].val;
            if (cur == target) return {nodes[left].idx, nodes[right].idx};
            if (cur < target) ++left;
            else --right;
        }

        return ret;
    }
};
```

#### [15. 3Sum](https://leetcode.com/problems/3sum/description/)

- 一刷
    - hashtable求解，但去重的情况太多，没做出来。
- 二刷
    - 正解，双指针。在2sum的基础上调整即可。不过这个题最大的问题是要处理去重的情况，我也是反复debug多次才作对。
    - 去重的情形
        - pruning 3: [0,0,0,0,0] 处理这种case
        - pruning 4: [-1, 0, 1] 处理这种case [-1] + [0, 1] 以及 [-1] + [0] + [1] 以及 [-1, 0,] + [1] 下标从当前i向后
        - pruning 5: [0,0,0,0] 也是这种case，但是它和pruing3不同
            - 前者是[0, 1, 2] and [1, 2, 3]这种 base = 0 and base = 1
            - 后者是[0, 1, 4] and [0, 2, 3]这种 base = 0, l = 1, r = 4 and base = 0, l = 2, r = 3

```cpp
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        vector<vector<int>> rets;
        int len = nums.size();
        std::sort(nums.begin(), nums.end());

        // pruning 1 - 无解
        if (0 < nums[0] or nums[len - 1] < 0) return rets;

        for (int i = 0; i < len - 2; ++i) { // pruning 2 - 减少循环次数
            // pruning 3 - 去重
            if (0 < i and nums[i] == nums[i - 1]) continue; 

            // pruning 4 - 去重
            int left = i + 1, right = len - 1;
            while (left < right) {

                int sum = nums[left] + nums[right] + nums[i];

                if (sum  == 0) { 
                    vector<int> ret; ret.push_back(nums[i]); ret.push_back(nums[left]); ret.push_back(nums[right]); rets.push_back(ret);

                    // 这里不能少，否则会漏解
                    ++left; 
                    --right;

                    // pruning 5 - 去重
                    while (left < right and nums[left] == nums[left-1]) ++left;
                    while (left < right and nums[right] == nums[right + 1]) --right;    
                }
                else if (sum  < 0) ++left;
                else --right;
            }
        }
        return rets;
    }
};
```

- 三刷
    - 思路：算法和4sum保持一致，剪枝。
```cpp
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        vector<vector<int>> rets;
        int len = nums.size();

        if (nums.size() < len) return rets;
        std::sort(nums.begin(), nums.end());

        for (int first = 0; first < len - 2; ++first) {
            // 去重
            if (0 < first and nums[first - 1] == nums[first]) continue;

            // 剪枝
            int min = nums[first] + nums[first + 1] + nums[first + 2];
            if (0 < min) break;

            // 剪枝
            int max = nums[first] + nums[len - 2] + nums[len - 1];
            if (max < 0) continue;

            int left = first + 1, right = len - 1;
            while (left < right) {
                int sum = nums[first] + nums[left] + nums[right];
                if (sum == 0) {
                    vector<int> ret;
                    ret.push_back(nums[first]); ret.push_back(nums[left]); ret.push_back(nums[right]);
                    rets.push_back(ret);

                    ++left; --right;
                    while (left < right and nums[left - 1] == nums[left]) ++left;
                    while (left < right and nums[right + 1] == nums[right]) --right;
                }
                else if (sum < 0) ++left;
                else --right;
            }
        }

        return rets;
    }
};
```

#### [18. 4Sum](https://leetcode.com/problems/4sum/description/)

- 一刷
    - 我的思路：基于3sum，再套一层，思路简单，但是最后TLE(261/294)
    - 我优化了剪枝，但是最终还是没有全过

```cpp
class Solution {
public:
    vector<vector<int>> fourSum(vector<int>& nums, int target) {
        vector<vector<int>> rets;
        std::sort(nums.begin(), nums.end());    
        int len = nums.size();

        if (0 < nums[0] and target <= 0 ) return rets;
        if (nums[len - 1] < 0 and target >= 0) return rets;
        if (len >= 4) {
            long long max = nums[len - 1] + nums[len - 2] + nums[len - 3] + nums[len - 4];
            if (max < target) return rets;

            long long min = nums[0] + nums[1] + nums[2] + nums[3];
            if (target < min) return rets;
        }


        for (int first = 0; first < len - 3; ++first) {
            if (0 < first and nums[first] == nums[first - 1]) continue;

            for (int second = first + 1; second < len - 2; ++second) {
                if (first + 1 < second and nums[second] == nums[second - 1]) continue;
                int left = second + 1, right = len - 1;
                while (left < right) {
                    std::cout << first << "," << second << "," << left << "," << right << endl;
                    long long sum = nums[first];
                    sum += nums[second];
                    sum += nums[left];
                    sum += nums[right];

                    if (sum == target) {
                        vector<int> ret;
                        ret.push_back(nums[first]);
                        ret.push_back(nums[second]);
                        ret.push_back(nums[left]);
                        ret.push_back(nums[right]);
                        rets.push_back(ret);

                        ++left;
                        --right;

                        while (left < right and nums[left] == nums[left - 1]) ++left;
                        while (left < right and nums[right] == nums[right + 1]) --right;
                    }
                    else if (sum < target) ++ left;
                    else --right;
                }
            }
        }
        return rets;
    }
};
```

- 二刷
    - 正解：求助了deepseek，给出了非常精彩的分析，一针见血指出问题。
    - 主要问题
        - 缺少对 first 和 second 的提前剪枝
        - 即使数组已排序，当前最外层两重循环没有根据当前最小/最大可能和来判断是否继续。

你的代码逻辑是对的，主要问题在于**剪枝不够充分**，导致在数据量大、target很大的情况下，`first` 和 `second` 循环做了太多不必要的遍历。

优化思路

- 在 `first` 循环中：
- 计算当前 `nums[first]` 能得到的**最小四数和**：  
  `min_sum = nums[first] + nums[first+1] + nums[first+2] + nums[first+3]`  
  如果 `min_sum > target` → 后面更大，直接 `break`
- 计算当前 `nums[first]` 能得到的**最大四数和**：  
  `max_sum = nums[first] + nums[len-3] + nums[len-2] + nums[len-1]`  
  如果 `max_sum < target` → 当前 `first` 太小，直接 `continue` 到下一个 `first`

在 `second` 循环中：
- 类似地，计算当前 `(first, second)` 组合的最小和 & 最大和，决定是否 `break` 或 `continue`

还有一个需要注意的点：**剪枝2和剪枝4使用continue 而不是 break**

```cpp
class Solution {
public:
    vector<vector<int>> fourSum(vector<int>& nums, int target) {
        vector<vector<int>> rets;
        int len = nums.size();
        if (len < 4) return rets;

        std::sort(nums.begin(), nums.end());

        for (int first = 0; first < len - 3; ++first) {
            // 去重
            if (0 < first and nums[first] == nums[first - 1]) continue;

            // 剪枝1：first 当前最小的4sum
            long long min1 = (long long)nums[first] + nums[first + 1] + nums[first + 2] + nums[first + 3];
            if (target < min1) break;

            // 剪枝2：first 当前最大的4sum
            long long max1 = (long long)nums[first] + nums[len - 3] + nums[len - 2] + nums[len - 1];
            if (max1 < target) continue;

            for (int second = first + 1; second < len - 2; ++second) {
                // 去重
                if (first + 1 < second and nums[second] == nums[second - 1]) continue;

                // 剪枝3: second当前最小的4sum
                long long min2 = (long long)nums[first] + nums[second] + nums[second + 1] + nums[second + 2];
                if (target < min2) break;

                // 剪枝4：second当前最大的4sum
                long long max2 = (long long)nums[first] + nums[second] + nums[len - 2] + nums[len - 1];
                if (max2 < target) continue;

                int left = second + 1, right = len - 1;
                while (left < right) {
                    long long sum = (long long)nums[first] + nums[second] + nums[left] + nums[right];
                    if (sum == target) {
                        vector<int> ret;
                        ret.push_back(nums[first]); ret.push_back(nums[second]); ret.push_back(nums[left]); ret.push_back(nums[right]);

                        ++left; --right;
                        while (left < right and nums[left - 1] == nums[left]) ++left;
                        while (left < right and nums[right + 1] == nums[right]) --right;

                        rets.push_back(ret);
                    } else if (sum < target) ++left;
                    else --right;
                }

            }
        }
        return rets;
    }
};
```

### 基础

#### [59. Spiral Matrix II](https://leetcode.com/problems/spiral-matrix-ii/)

- 一刷
    - 我的思路：模拟即可。
    - 每次就四个方向，按照意义模拟即可。循环结束的条件是所有数字填充完。

```cpp
class Solution {
public:
    vector<vector<int>> generateMatrix(int n) {
        vector<vector<int>> res(n, vector<int>(n, 0));
        int num = 0;
        int row = 0, col = 0;
        while (num < n * n) {
            // right
            while (col < n and res[row][col] == 0) {
                //std::cout << row << "," << col << std::endl;
                ++num;
                res[row][col] = num;
                ++col;
                
            }
            --col;
            ++row;
            // down
            while (row < n and res[row][col] == 0) {
                //std::cout << row << "," << col << std::endl;
                ++num;
                res[row][col] = num;
                ++row;
            }
            --row;
            --col;
            // left
            while (col >= 0 and res[row][col] == 0) {
                //std::cout << row << "," << col << std::endl;
                ++num;
                res[row][col] = num;
                --col;
            }
            ++col;
            --row;
            // up
            while (row >= 0 and res[row][col] == 0) {
                //std::cout << row << "," << col << std::endl;
                ++num;
                res[row][col] = num;
                --row;
            }
            ++row;
            ++col;
        }
        return res;
    }
};
```

## 链表

### 基础

#### [203. Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/)

- 一刷
    - 我的思路：dummy节点 + 基本删除操作
    - 迭代pre/cur指针，便于操作

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
        auto* dummy = new ListNode();
        dummy->next = head;

        auto pre = dummy;
        auto cur = head;

        while (cur) {
            if (cur->val == val) {
                pre->next = cur->next;
                delete cur;
                cur = pre->next;
            } else {
                pre = cur;
                cur = cur->next;
            }
        }

        head = dummy->next;
        delete dummy;
        dummy = nullptr;
        return head;
    }
};
```

#### [707. Design Linked List](https://leetcode.com/problems/design-linked-list/)

- 一刷
    - 我的思路：围绕addHead/addTail这两个方法，先进行数据结构设计，然后实现其他方法。
        - 增加head/tail指针
        - 所有方法，都需要针对数据结构设计，进行调整。
    - 心得：整体来说，这个题反而偏工程实践，不难，但想一把写对不容易。
        - 由于增加了头结点，下标可以从-1 开始，也可以从0开始。注意针对不同的方法即可。
        - 所有add/delete方法，需要注意对head/tail的更新。
        - 元素下标从0开始，一开始我没注意到
```cpp
class MyLinkedList {
public:
    MyLinkedList() {
        head = new Node();
        tail = head;    
    }
    
    int get(int index) {
        auto cur = head->next;
        for (int i = 0; i < index and cur; ++i) {
            cur = cur->next;   
        }     
        if(!cur) return -1;
        else return cur->val;
    }
    
    void addAtHead(int val) {
        auto* node = new Node(val);
        node->next = head->next;
        head->next = node;

        if (!node->next) tail = node;
    }
    
    void addAtTail(int val) {
        auto* node = new Node(val);
        tail->next = node;
        tail = node;
    }
    
    void addAtIndex(int index, int val) {
        auto cur = head;
        for (int i = -1; i < index - 1 and cur; ++i) {
            cur = cur->next;
        }
        if (!cur) return;

        auto node = new Node(val);
        node->next = cur->next;
        cur->next = node;

        if (!node->next) tail = node;
    }
    
    void deleteAtIndex(int index) {
        auto cur = head;
        for (int i = -1; i < index - 1 and cur; ++i) {
            cur = cur->next;
        }
        if (!cur) return;
        auto tmp = cur->next;
        if (!tmp) return;

        cur->next = tmp->next;
        delete tmp;
        tmp = nullptr;   

        if (cur->next == nullptr) tail = cur;
    }
private:
    struct Node {
        int val = 0;
        Node* next = nullptr;
        Node() = default;
        Node(int v) : val(v), next(nullptr) {}
    };

    Node* head = nullptr;
    Node* tail = nullptr;
};

/**
 * Your MyLinkedList object will be instantiated and called as such:
 * MyLinkedList* obj = new MyLinkedList();
 * int param_1 = obj->get(index);
 * obj->addAtHead(val);
 * obj->addAtTail(val);
 * obj->addAtIndex(index,val);
 * obj->deleteAtIndex(index);
 */
```

- 二刷
    - 注意点：
        - 数据结构设计 
        - 下标
        - tail处理
    - 主要解决的是下标的事
        - 引入pre/cur
        - 统一下标从0开始

```cpp
class MyLinkedList {
public:
    MyLinkedList() {
        head = new Node();
        tail = head;    
    }
    
    int get(int index) {
        auto cur = head->next;
        for (int i = 0; i < index and cur; ++i) {
            cur = cur->next;   
        }     
        if(!cur) return -1;
        else return cur->val;
    }
    
    void addAtHead(int val) {
        auto* node = new Node(val);
        node->next = head->next;
        head->next = node;

        if (!node->next) tail = node;
    }
    
    void addAtTail(int val) {
        auto* node = new Node(val);
        tail->next = node;
        tail = node;
    }
    
    void addAtIndex(int index, int val) {
        // auto cur = head;
        // for (int i = -1; i < index - 1 and cur; ++i) {
        //     cur = cur->next;
        // }
        // if (!cur) return;

        // auto node = new Node(val);
        // node->next = cur->next;
        // cur->next = node;

        // if (!node->next) tail = node;

        auto pre = head;
        auto cur = head->next;
        int i = 0;
        for (i = 0; i < index and cur; ++i) {
            pre = cur;
            cur = cur->next;
        }

        if(i < index) return;

        auto node = new Node(val);
        pre->next = node;
        node->next = cur;

        if (!node->next) tail = node;
    }
    
    void deleteAtIndex(int index) {
        // auto cur = head;
        // for (int i = -1; i < index - 1 and cur; ++i) {
        //     cur = cur->next;
        // }
        // if (!cur) return;
        // auto tmp = cur->next;
        // if (!tmp) return;

        // cur->next = tmp->next;
        // delete tmp;
        // tmp = nullptr;   

        // if (cur->next == nullptr) tail = cur;
        auto pre = head;
        auto cur = head->next;
        int i = 0;
        for (i < 0; i < index and cur; ++i) {
            pre = cur;
            cur = cur->next;
        }
        if (i < index) return;
        if (!cur) return;

        pre->next = cur->next;
        delete cur;
        cur = nullptr;

        if (!pre->next) tail = pre;
        
    }
private:
    struct Node {
        int val = 0;
        Node* next = nullptr;
        Node() = default;
        Node(int v) : val(v), next(nullptr) {}
    };

    Node* head = nullptr;
    Node* tail = nullptr;
};

/**
 * Your MyLinkedList object will be instantiated and called as such:
 * MyLinkedList* obj = new MyLinkedList();
 * int param_1 = obj->get(index);
 * obj->addAtHead(val);
 * obj->addAtTail(val);
 * obj->addAtIndex(index,val);
 * obj->deleteAtIndex(index);
 */
```

#### [206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/description/)

- 一刷
    - 我的思路
        - 反转的核心是：cur->next = pre
        - 但是这样会丢掉下一个节点，无法迭代，所以先保存即可
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* pre = nullptr;
        auto cur = head;
        while (cur) {
            auto next = cur->next;
            cur->next = pre;

            pre = cur;
            cur = next;
        }

        head = pre;
        return head;
    }
};
```

- 二刷
    - 我的思路：原问题与子问题具有相同的结构
    - 递归边界好写
    - 递归执行，处理当前节点和剩余子链表即可。
    - 这里注意，处理当前节点并不会改动子链表的头指针，因为reverse.

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        if (!head or !head->next) return head;

        auto new_head = reverseList(head->next);

        auto tail = head->next;
        tail->next = head;
        head->next = nullptr;

        return new_head;
    }
};
```

#### [24. Swap Nodes in Pairs](https://leetcode.com/problems/swap-nodes-in-pairs/description/)

- 一刷
    - 我的思路
        - 关注局部，我先不考虑边界的情况，先写出swap函数。再考虑外部
        - 增加dummy节点，但最后一定别忘了释放，以及**更新head**
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* swapPairs(ListNode* head) {
        auto* dummy = new ListNode();
        dummy->next = head;

        auto pre = dummy;
        while (swapNew(pre)) {
            pre = pre->next->next;
        }
        head = dummy->next;
        delete dummy;
        return head;
    }
    bool swapNew(ListNode*& pre) {
        auto cur = pre->next;
        if (!cur) return false;
        auto nex = cur->next;
        if (!nex) return false;

        auto tmp = nex->next;

        pre->next = nex;
        nex->next = cur;
        cur->next = tmp;

        return true;

    }
};
```

### 双指针

#### [19. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/)

- 一刷
    - 我的思路
        - 快慢指针，一个先走N步，一个接着走，这样fast到终点时，slow刚好到倒数N节点
        - 为了方便删除，引入pre/cur写法。
        - 增加dummy node，别忘了最后删除该节点，以及更新head.

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        auto* dummy = new ListNode(); 
        dummy->next = head;

        auto fast = dummy;
        while (n--) {
            fast = fast->next;
        }

        ListNode* pre = nullptr;
        auto slow = dummy;
        while (fast) {
            fast = fast->next;
            pre = slow;
            slow = slow->next;
        }

        pre->next = slow->next;
        delete slow;
        slow = nullptr;

        head = dummy->next;

        delete dummy;
        return head;
    }
};
```

#### [160. Intersection of Two Linked Lists](https://leetcode.com/problems/intersection-of-two-linked-lists/description/)

- 一刷
    - 我的思路：遍历第一个链表，构造set. 遍历第二个链表，查一下。不高效。

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        std::set<ListNode*> pointers;
        for (auto cur = headA; cur; cur = cur->next) {
            pointers.insert(cur);
        }

        for (auto cur = headB; cur; cur = cur->next) {
            if (pointers.count(cur)) return cur;
        }

        return nullptr;
    }
};
```

- 二刷
    - 最优解：算出步长差值diff。然后长链表移动diff。两个链表再同时移动，如果有交汇，就有，否则没有。
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        int lenA = 0;
        for (auto cur = headA; cur; cur = cur->next) {
            lenA++;
        }

        int lenB = 0;
        for (auto cur = headB; cur; cur = cur->next) {
            lenB++;
        }

        if (lenA < lenB) {
            auto diff = lenB - lenA;
            while (diff--) { headB = headB->next; }
        } else {
            auto diff = lenA - lenB;
            while (diff--) { headA = headA->next; }
        }

        return intersection(headA, headB);
    }

    ListNode *intersection(ListNode *headA, ListNode *headB) {
        while (headA and headB) {
            if (headA == headB) return headA;
            else {headA = headA->next; headB = headB->next;}
        }
        return nullptr;
    }
};
```

#### [141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/description/)

- 一刷
    - 我的思路：快慢指针，一个走一步，一个走两步。如果有环，一定可以相遇。
    - 注意：快指针只能走2步，否则会跨过去，虽然有环，但是不能很快发现。

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    bool hasCycle(ListNode *head) {
        auto fast = head;
        auto slow = head;
        while (fast and fast->next) {
            fast = fast->next->next;
            slow = slow->next;
            if (fast==slow) return true;
        }
        return false;
    }
};
```

#### [142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/description/)

- 一刷
    - 我的思路：没思路。看了题解。需要数学论证：结论
        - 首先，寻找相遇点。
        - 然后，一个从相遇点开始，一个从头开始，相交处即为环入口。
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *detectCycle(ListNode *head) {
        auto fast = head;
        auto slow = head;
        while (fast and fast->next) {
            fast = fast->next->next;
            slow = slow->next;
            if (fast == slow) break;
        }
        if (!fast or !fast->next) return nullptr;
        auto index1 = head;
        auto index2 = fast;
        while (index1 != index2) {
            index1 = index1->next;
            index2 = index2->next;
        }
        return index1;
    }
};
```

## 哈希表

### 基础

#### [242. Valid Anagram](https://leetcode.com/problems/valid-anagram/)

- 一刷
    - 我的思路：两次遍历，第一次建hashmap，++。第二次遍历hashmap,--
    - 注意，无序使用```std::map```即可

```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        if (s.size() != t.size()) return false;

        std::map<char, int> counter;
        for (const auto& ch : s) counter[ch]++;

        for (const auto& ch : t) counter[ch]--;

        for (const auto& [k, v] : counter) {
            if(v != 0) return false;
        }    

        return true;
    }
};
```

#### [349. Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/description/)

- 一刷
    - 我的思路：基础题，不赘述，使用```std::set```即可

```cpp
class Solution {
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
        std::set<int> set1(nums1.begin(), nums1.end());

        set<int> ret;
        for (const auto& ele : nums2) {
            if (set1.count(ele)) ret.insert(ele);
        }

        vector<int> inter_set(ret.begin(), ret.end());
        return inter_set;
    }
};
```

#### [350. Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/description/)

- 一刷
    - 我的思路：这里牵扯到技术，所以使用hashmap, hashset无法解决数量的问题。

```cpp
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
        std::unordered_map<int, int> map;
        for (const auto& ele : nums1) map[ele]++;

        std::vector<int> ret;
        for (const auto& ele : nums2) {
            auto it = map.find(ele);
            if (it != map.end() and it->second > 0) {
                ret.push_back(ele);
                it->second--;
            }
        }
        return ret;    
    }
};
```

#### [202. Happy Number](https://leetcode.com/problems/happy-number/description/)

- 一刷
    - 我的思路：这个题我没思路，主要是不知道怎么处理infinite-loop的问题。
    - 正解：infinite-loop会出现循环数字，这是个正常思路，不一定。但是我没有继续尝试，所以没发现这个规律。

```cpp
class Solution {
public:
    bool isHappy(int n) {
        std::unordered_set<int> set;
        while (true) {
            n = replace(n);
            if (n == 1) return true;
            if (set.count(n)) return false;
            else set.insert(n);
        }    
    }
    int replace(int n) {
        int ret = 0;
        while (n) {
            auto digit = n%10;
            ret += (digit * digit);
            n /= 10;
        }
        return ret;
    }
};
```

#### [1. Two Sum](https://leetcode.com/problems/two-sum/description/)

- 一刷
    - 我的思路：hashmap存一个key，判断另一个key是否在即可。看起来简单，操作起来容易出错。
    - 注意点：下标怎么处理？比如[3,3] 这种，key相同，但是下标不同。
        - 我使用了拉链法的思路。
        - 先建表，再查询。(不是最优)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        std::unordered_map<int, std::vector<int>> hashmap;
        for (int i = 0; i < nums.size(); ++i) {
            hashmap[nums[i]].emplace_back(i);
        }

        vector<int> ret;
        for (int i = 0; i < nums.size(); ++i) {
            auto val = target - nums[i];

            auto it = hashmap.find(val);
            if (it == hashmap.end()) continue;

            const auto& indice = it->second;

            if (val == nums[i] and indice.size() == 1) continue;


            ret.push_back(i);

            if (val == nums[i]) ret.push_back(indice[1]);
            else ret.push_back(indice[0]);

            break;
        }
        return ret;
    }
};
```

- 二刷
    - 最优：一遍遍历即可，不用先建表，再查询。一边建表，一边查询。
    - 这个办法最明显的优点是，不用存indice，只是一个index.
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        std::unordered_map<int, int> map;
        for (int i = 0; i < nums.size(); ++i) {
            auto val = target - nums[i];
            auto it = map.find(val);
            if (it == map.end()) {
                map.emplace(nums[i], i);
            } else {
                return {it->second, i};
            }
        }    
        return {};
    }
};
```

#### [454. 4Sum II](https://leetcode.com/problems/4sum-ii/description/)

- 一刷
    - 正解：hashmap
    - 规律：xSUM类型题目，如果涉及元素本身，用双指针。因为此时如果用hashmap，不好去重。其它则考虑用hashmap
    - 比如，本题不涉及元素本身，如果用下标，不会出现重复的问题，所以首先考虑hashmap.

```cpp
class Solution {
public:
    int fourSumCount(vector<int>& nums1, vector<int>& nums2, vector<int>& nums3, vector<int>& nums4) {
        int count = 0;
        std::unordered_map<int, int> umap;
        for (const auto& first : nums1) {
            for (const auto& second : nums2) {
                umap[first + second]++; 
            }
        }

        for (const auto& third : nums3) {
            for (const auto& fourth : nums4) {
                auto it = umap.find(0 - third - fourth);
                if (it != umap.end()) count += it->second;
            }
        }

        return count;
    }
};
```

#### [383. Ransom Note](https://leetcode.com/problems/ransom-note/description/)

- 一刷
    - 我的思路：hashmap计数
    - 最优解：剪枝 + 数组，这个办法更好，空间负责度可控。
```cpp
class Solution {
public:
    bool canConstruct(string ransomNote, string magazine) {
        std::unordered_map<char, int> umap;
        for (const auto& ch : magazine) umap[ch]++;

        for (const auto& ch : ransomNote) {
            auto it = umap.find(ch);
            if (it == umap.end()) return false;
            if (it->second == 0) return false;

            it->second--;
        }
        return true;
    }
};
```

## 字符串

### 基础

#### [344. Reverse String](https://leetcode.com/problems/reverse-string/description/)

- 一刷
    - 我的思路：遍历一半，进行swap即可。注意循环条件
```cpp
class Solution {
public:
    void reverseString(vector<char>& s) {
        for (int i = 0, k = s.size() - 1; i < s.size() / 2; ++i, --k) {
            std::swap(s[i], s[k]);
        }    
    }
};
```

#### [541. Reverse String II](https://leetcode.com/problems/reverse-string-ii/description/)

- 一刷
    - 我的思路：模拟实现逻辑即可。
    - 注意点：注意下标校验。怎么工程代码下标校验的都挺好，一写算法题反而都不校验呢？
```cpp
class Solution {
public:
    string reverseStr(string s, int k) {
        int len = s.size();
        for (int start = 0; start < len ; start += (k * 2)) {
            reverse(s, start, std::min(len, start + k));
        }
        return s;
    }
    void reverse(string& s, int b, int e) {
        for (int i = b, k = e - 1; i < b + (e - b) / 2; ++i, --k) {
            std::swap(s[i], s[k]);
        }
    }
};
```

#### [151. Reverse Words in a String](https://leetcode.com/problems/reverse-words-in-a-string/description/)

- 一刷
    - 我的思路：模式识别
```cpp
class Solution {
public:
    string reverseWords(string s) {
        int b = 0, e = s.size();
        std::string ret;
        while (b < e) {
            int i = b;

            // 识别起点
            while (i < e and s[i] == ' ') ++i;
            if (i == e) break;
            b = i;
            
            // 识别终点
            while (i < e and s[i] != ' ') ++i;

            // 生成子串
            auto token = s.substr(b, i - b);
            if (ret.empty()) ret = token;
            else ret = token + " " + ret;

            b = i;
        }
        return ret;
    }
};
```

- 二刷
    - 最优解：要求不增加额外空间，就地处理。
    - 整体reverse，再reverse各个部分即可。
    - 需要处理多余空格的情形，这个地方使用快慢指针。

```cpp
class Solution {
public:
    string reverseWords(string s) {
        int len = s.size();
        // 整体reverse
        reverse(s.begin(), s.end());
        int fast = 0, slow = 0;
        while (fast < len) {
            if (s[fast] == ' ') ++fast;
            else {
                // 处理不是第一个单词的情形
                if (slow) s[slow++] = ' ';

                // 处理单词
                int i = fast;
                int old_slow = slow;
                while (i < len and s[i] != ' ') s[slow++] = s[i++];

                // 局部reverse
                reverse(s.begin() + old_slow, s.begin() + slow);
                fast = i;
            }
        }
        s.resize(slow);
        return s;
    }
};
```

#### [28. Find the Index of the First Occurrence in a String](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/)

- 一刷
    - 我的思路：遍历
```cpp
class Solution {
public:
    int strStr(string haystack, string needle) {
        if (haystack.size() < needle.size()) return -1;

        for (int i = 0; i <= haystack.size() - needle.size(); ++i) {
            bool match = true;
            for (int k = 0; k < needle.size(); ++k) {
                if (haystack[i + k] != needle[k]) {
                    match = false; break;
                }
            }
            if (match) return i;
        }
        return -1;
    }
};
```

#### [459. Repeated Substring Pattern](https://leetcode.com/problems/repeated-substring-pattern/description/)

- 一刷
    - 我的思路：暴力枚举子串
    - 这里有个技巧是，不要比较，把子串都加起来，代码上好写一点

```cpp
class Solution {
public:
    bool repeatedSubstringPattern(string s) {
        for (int sublen = s.size() / 2; sublen >= 1; --sublen) {
            if (s.size() % sublen != 0) continue;
            int n = s.size() / sublen;

            auto substr = s.substr(0, sublen);
            auto target = substr;
            for (int i = 0; i < n - 1; ++i) target += substr;
            if (target == s) return true;
        }      
        return false;  
    }
};
```

## 栈和队列

### 基础

#### [232. Implement Queue using Stacks](https://leetcode.com/problems/implement-queue-using-stacks/description/)

- 一刷
    - 我的思路：两个栈模拟即可
```cpp
class MyQueue {
public:
    stack<int> stk;
    stack<int> helper;

    void transfer(stack<int>& from, stack<int>& to) {
        while (!from.empty()) {
            to.push(from.top());
            from.pop();
        }
    }

    MyQueue() {
        
    }
    
    void push(int x) {
        stk.push(x);
    }
    
    int pop() {

        transfer(stk, helper);
        int res = helper.top();
        helper.pop();
        transfer(helper, stk);
        return res;
    }
    
    int peek() {
        transfer(stk, helper);
        int res = helper.top();
        transfer(helper, stk);
        return res;
    }
    
    bool empty() {
        return stk.empty();
    }
};

/**
 * Your MyQueue object will be instantiated and called as such:
 * MyQueue* obj = new MyQueue();
 * obj->push(x);
 * int param_2 = obj->pop();
 * int param_3 = obj->peek();
 * bool param_4 = obj->empty();
 */
```

- 二刷
    - 最优解：上面的解法并非最优，数据结构设计是没问题的，肯定需要两个栈。
    - 但对于这两个栈的关系，理解不同。
        - 我的解法是，一个master，一个helper。helper是纯helper
        - 但，最优解的思路是，他们是一个整体，这点挺秒的。
            - 因为，in/out所涉及到的操作不同，并不需要每次都要transfer
            - in是队列头，out是队列尾
            - in/out完成各自的操作即可。
        - 复用存量方法
```cpp
class MyQueue {
public:
    stack<int> in;
    stack<int> out;
    MyQueue() {
        
    }
    
    void push(int x) {
        in.push(x);
    }
    
    int pop() {
        if (out.empty()) {
            while (!in.empty()) {
                out.push(in.top());
                in.pop();
            }
        }

        auto x = out.top();
        out.pop();
        return x;
    }
    
    int peek() {
        auto x = pop();
        out.push(x);
        return x;
    }
    
    bool empty() {
        return in.empty() and out.empty();
    }
};

/**
 * Your MyQueue object will be instantiated and called as such:
 * MyQueue* obj = new MyQueue();
 * obj->push(x);
 * int param_2 = obj->pop();
 * int param_3 = obj->peek();
 * bool param_4 = obj->empty();
 */
```

#### [225. Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/description/)

- 一刷
    - 我的思路：这个题我意识到和上一到题不一样，这个题并不是in/out一体，而就是base and helper的关系
    - 上一题， in其实是队列头，out是队列尾。这题没有这么会事，因为stk都是只能在一端操作。

```cpp
class MyStack {
public:
    queue<int> base;
    MyStack() {
        
    }
    
    void push(int x) {
        base.push(x);   
    }
    
    int pop() {
        queue<int> helper;
        while (base.size() > 1) {
            auto x = base.front();
            helper.push(x);
            base.pop();
        }
        auto x = base.back(); base.pop();
        while (!helper.empty()) { 
            base.push(helper.front());
            helper.pop();
         } 
         return x;
    }
    
    int top() {
        return base.back();
    }
    
    bool empty() {
        return base.empty();
    }
};

/**
 * Your MyStack object will be instantiated and called as such:
 * MyStack* obj = new MyStack();
 * obj->push(x);
 * int param_2 = obj->pop();
 * int param_3 = obj->top();
 * bool param_4 = obj->empty();
 */
```

- 二刷
    - 最优解：其实一个队列就够了
    - pop n-1次，再插入队列，此时队列头就是要出队的元素
```cpp
class MyStack {
public:
    queue<int> base;
    MyStack() {
        
    }
    
    void push(int x) {
        base.push(x);   
    }
    
    int pop() {
        int n = base.size();
        for (int i = 0; i < n - 1; ++i) {
            base.push(base.front()); base.pop();
        }
        auto res = base.front();
        base.pop();
        return res;
    }
    
    int top() {
        return base.back();
    }
    
    bool empty() {
        return base.empty();
    }
};

/**
 * Your MyStack object will be instantiated and called as such:
 * MyStack* obj = new MyStack();
 * obj->push(x);
 * int param_2 = obj->pop();
 * int param_3 = obj->top();
 * bool param_4 = obj->empty();
 */
```

#### [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/)

- 一刷
    - 我的思路：经典题目，栈来做就好。
    - 细节：右括号多，左括号多的两种情况需要考虑

```cpp
class Solution {
public: 
    bool isValid(string s) {
        stack<char> stk;
        for (const auto& ch : s) {
            if (ch == ']' or ch == ')' or ch == '}') {
                if (stk.empty()) return false;
                auto left = stk.top(); stk.pop();
                if (ch == ']' and left != '[') return false;
                if (ch == ')' and left != '(') return false;
                if (ch == '}' and left != '{') return false;
            } else stk.push(ch);
        }
        return stk.empty();
    }
};
```

#### [1047. Remove All Adjacent Duplicates In String](https://leetcode.com/problems/remove-all-adjacent-duplicates-in-string/)

- 一刷
    - 我的思路：相邻匹配的题目，都可以栈来做。因为栈方便拿pre.

```cpp
class Solution {
public:
    string removeDuplicates(string s) {
        stack<char> stk;
        for (const auto& ch : s) {
            if (stk.empty()) { stk.push(ch); continue; }

            auto pre = stk.top();
            if (pre == ch) { stk.pop(); continue; }

            stk.push(ch);
        }

        std::string ret;
        while (!stk.empty()) {
            auto ch = stk.top(); stk.pop();
            ret = ch + ret;
        }
        return ret;
    }
};
```

#### [150. Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/description/)

- 一刷
    - 我的思路：学生时代经典题，不赘述

```cpp
class Solution {
public:
    int evalRPN(vector<string>& tokens) {
        stack<int> opnd;
        for (const auto& token : tokens) {
            if (token == "+" or token == "-" or token == "*" or token == "/") {
                auto right = opnd.top(); opnd.pop();
                auto left = opnd.top(); opnd.pop();

                if (token == "+") opnd.push(left + right);
                else if (token == "-") opnd.push(left - right);
                else if (token == "*") opnd.push(left * right);
                else if (token == "/") opnd.push(left / right);

            } else opnd.push(stoi(token));
        }
        return opnd.top();
    }
};
```

## 二叉树

### 基本

#### [144. Binary Tree Preorder Traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/submissions/1977206534/)

- 一刷
    - 递归，不赘述

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    vector<int> preorderTraversal(TreeNode* root) {
        vector<int> ret;
        preorder(root, ret);
        return ret;
    }
    void preorder(TreeNode* root, vector<int>& res) {
        if (!root) return;
        res.push_back(root->val);
        preorder(root->left, res);
        preorder(root->right, res);
    }
};
```

#### [94. Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/)

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    vector<int> inorderTraversal(TreeNode* root) {
        vector<int> ret;
        inorder(root, ret);
        return ret;        
    }
    void inorder(TreeNode* root, vector<int>& res) {
        if (!root) return;
        inorder(root->left, res);
        res.push_back(root->val);
        inorder(root->right, res);
    }
};
```

#### [145. Binary Tree Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/submissions/1977210284/)

- 一刷
    - 递归，不赘述

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    vector<int> postorderTraversal(TreeNode* root) {
        vector<int> ret;
        postorder(root, ret);
        return ret;
    }
    void postorder(TreeNode* root, vector<int>& res) {
        if (!root) return;
        postorder(root->left, res);
        postorder(root->right, res);
        res.push_back(root->val);
    }
};
```