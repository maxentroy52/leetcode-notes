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
    + [239. Sliding Window Maximum](#239-sliding-window-maximum)
    + [347. Top K Frequent Elements](#347-top-k-frequent-elements)
- [二叉树](#%E4%BA%8C%E5%8F%89%E6%A0%91)
  * [基本](#%E5%9F%BA%E6%9C%AC)
    + [144. Binary Tree Preorder Traversal](#144-binary-tree-preorder-traversal)
    + [94. Binary Tree Inorder Traversal](#94-binary-tree-inorder-traversal)
    + [145. Binary Tree Postorder Traversal](#145-binary-tree-postorder-traversal)
    + [102. Binary Tree Level Order Traversal](#102-binary-tree-level-order-traversal)
    + [107. Binary Tree Level Order Traversal II](#107-binary-tree-level-order-traversal-ii)
    + [199. Binary Tree Right Side View](#199-binary-tree-right-side-view)
    + [637. Average of Levels in Binary Tree](#637-average-of-levels-in-binary-tree)
    + [429. N-ary Tree Level Order Traversal](#429-n-ary-tree-level-order-traversal)
    + [515. Find Largest Value in Each Tree Row](#515-find-largest-value-in-each-tree-row)
    + [116. Populating Next Right Pointers in Each Node](#116-populating-next-right-pointers-in-each-node)
    + [117. Populating Next Right Pointers in Each Node II](#117-populating-next-right-pointers-in-each-node-ii)
    + [104. Maximum Depth of Binary Tree](#104-maximum-depth-of-binary-tree)
    + [111. Minimum Depth of Binary Tree](#111-minimum-depth-of-binary-tree)
    + [226. Invert Binary Tree](#226-invert-binary-tree)
    + [101. Symmetric Tree](#101-symmetric-tree)
    + [222. Count Complete Tree Nodes](#222-count-complete-tree-nodes)
    + [110. Balanced Binary Tree](#110-balanced-binary-tree)
    + [257. Binary Tree Paths](#257-binary-tree-paths)
    + [404. Sum of Left Leaves](#404-sum-of-left-leaves)
    + [513. Find Bottom Left Tree Value](#513-find-bottom-left-tree-value)
    + [112. Path Sum](#112-path-sum)
    + [105. Construct Binary Tree from Preorder and Inorder Traversal](#105-construct-binary-tree-from-preorder-and-inorder-traversal)
    + [654. Maximum Binary Tree](#654-maximum-binary-tree)
    + [617. Merge Two Binary Trees](#617-merge-two-binary-trees)
    + [98. Validate Binary Search Tree](#98-validate-binary-search-tree)
    + [700. Search in a Binary Search Tree](#700-search-in-a-binary-search-tree)
    + [530. Minimum Absolute Difference in BST](#530-minimum-absolute-difference-in-bst)
    + [501. Find Mode in Binary Search Tree](#501-find-mode-in-binary-search-tree)
    + [701. Insert into a Binary Search Tree](#701-insert-into-a-binary-search-tree)
    + [450. Delete Node in a BST](#450-delete-node-in-a-bst)
    + [669. Trim a Binary Search Tree](#669-trim-a-binary-search-tree)
    + [108. Convert Sorted Array to Binary Search Tree](#108-convert-sorted-array-to-binary-search-tree)

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

#### [239. Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/)

- 一刷
    - 我的思路：暴力枚举window. 这题从题面上来说，并不难。
    - 这题其实还挺好的，多种解法，考差了对多种数据结的使用。
    - 这题的难点在于，window的状态，怎么保证。
        - 最大数好球，搞一个堆即可，但是sliding的时候，移除元素，堆无法操作，因为堆只能操作堆顶。
        - 所以，第一个解法，使用了tree-like data structure。即可以排序，又方便删除。
        - ```std::multiset```可以排序，同时又可以删除，满足要求。
```cpp
class Solution {
public:
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        vector<int> ret;
        multiset<int> range;
        for (int i = 0; i < nums.size(); ++i) {
            range.insert(nums[i]);
            
            // 开始移除元素
            if (i >= k) {
                auto left = range.find(nums[i - k]);
                range.erase( left );
            }

            // 增加range结果
            if (i >= k - 1) ret.push_back( *range.rbegin() );
        }
        return ret;
    }
};
```

- 二刷
    - 优化的思路
        - 对比treeset的思路，之前的思路是，保持住range，然后在range里面找最大。
        - 优化的思路不是这样，过程都一样。但是，不用保证window。
        - 之前不用max_heap的原因在于，left找不到，因为max_heap只能操作top，而top不一定是left，所以无法删除left
        - 这里的核心点在于：我这里需要的是window max，只要不影响max，其实left删不删不重要。
        - [3,4,5,1]，这个case，插入1的时候，在max_heap中删不删1不重要。 
```cpp
class Solution {
public:
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        // [num, idx]
        priority_queue<pair<int, int>> max_heap;    
    
        vector<int> ret;

        for (int i = 0; i < nums.size(); ++i) {
            max_heap.emplace(nums[i], i);
            
            // 开始移除元素
            // 不是要真的移除left
            // 只要left不影响max即可
            if (i >= k) {
                while (!max_heap.empty() and max_heap.top().second <= i - k) max_heap.pop();
            }

            // 增加range结果
            if (i >= k - 1) ret.push_back( max_heap.top().first );
        }

        return ret;
    }
};
```

- 三刷
    - 最优解
        - 其实这三种解法，一路做过来，就发现最优解比较好理解了。
        - 在二刷的时候，我已经意识到，没有必要保留整个range，max_heap能保持有效max即可。
        - 最优解这里也是类似的办法

```cpp
class Solution {
public:
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        std::vector<int> ret;
        std::deque<int> desc_queue;
        for (int i = 0; i < nums.size(); ++i) {
            // 移除元素
            if (!desc_queue.empty() and desc_queue.front() == i - k) desc_queue.pop_front();
            
            // 增加元素
            while ( !desc_queue.empty() and nums[desc_queue.back()] <= nums[i] ) desc_queue.pop_back();
            desc_queue.push_back(i);

            // 记录结果
            if (i >= k - 1) ret.push_back(nums[desc_queue.front()]);
        }
        return ret;
    }
};
```

deepseek给了非常清晰的解答，参考。核心就是用一个单调队列，存下标，因为下标需要校验有效性。只存可能是最大值的下标即可。我觉得跟max_heap一个思路，只不过这个数据结构，时间性能更好。

这个题还是不错的，循序渐进，练到了多种数据结构，其实工作中并不常见，起码我一个都没用过。

The key insight: **We only need to keep potential maximum candidates in decreasing order**. If we have indices `i < j` and `nums[i] <= nums[j]`, then `nums[i]` will NEVER be the maximum for any window that includes `j` (because `j` is larger and will stay in the window longer).

1. Maintain a **deque that stores indices** (not values)
2. The deque is always **decreasing** in terms of values (nums[deque[0]] is largest)
3. For each new element at index `i`:
   - **Remove from front**: Remove indices that are out of current window (index <= i-k)
   - **Remove from back**: While the back element's value <= nums[i], pop it (they're useless now)
   - **Add current index** to the back
   - **Record answer**: The front of deque is the maximum for current window

1. Removing from Front (Window Boundary)
```cpp
if (!dq.empty() && dq.front() == i - k)
    dq.pop_front();
```
- Window covers indices `[i-k+1, i]`
- Any index <= `i-k` is out
- Since indices increase, we only need to check the front (oldest index)

2. Removing from Back (Maintaining Decreasing Order)
```cpp
while (!dq.empty() && nums[dq.back()] <= nums[i])
    dq.pop_back();
```
This is the **most important operation**. Why remove smaller elements?

**Example**: Window has `[5, 3]` and new element `4` arrives
- Deque currently: `[5(index0), 3(index1)]`
- New element `4` at index 2
- Compare `3 <= 4`: yes, remove 3
- Now deque: `[5(index0)]`
- Compare `5 <= 4`: no, stop
- Add 4: deque becomes `[5(index0), 4(index2)]`

The deque maintains a **monotonically decreasing** sequence of values. This property ensures:
- Front is always maximum in current window
- All elements in deque are potential maximums for future windows
- No useless elements are stored

```cpp
class Solution {
public:
    vector<int> maxSlidingWindow(vector<int>& nums, int k) {
        vector<int> result;
        deque<int> dq; // stores INDICES, not values
        
        for (int i = 0; i < nums.size(); i++) {
            // Step 1: Remove indices that are out of current window
            // Window covers [i-k+1, i]
            // If front index is exactly i-k, it's the one leaving
            if (!dq.empty() && dq.front() == i - k) {
                dq.pop_front();
            }
            
            // Step 2: Remove from back all indices whose values are <= current
            // They can never be maximum for any window containing i
            while (!dq.empty() && nums[dq.back()] <= nums[i]) {
                dq.pop_back();
            }
            
            // Step 3: Add current index
            dq.push_back(i);
            
            // Step 4: Record result once we have a full window
            if (i >= k - 1) {
                result.push_back(nums[dq.front()]);
            }
        }
        
        return result;
    }
};
```

#### [347. Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/submissions/1978096715/)

- 一刷
    - 我的思路：这题其实在工作中挺常见的，常规处理即可
```cpp
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        std::unordered_map<int, int> umap;
        for (const auto& num : nums) umap[num]++;

        struct Node {
            int val = 0;
            int cnt = 0;
            Node() = default;
            Node(int v, int c) : val(v), cnt(c) {}
            bool operator<(const Node& rhs) const { return cnt > rhs.cnt; }
        };
        std::vector<Node> counter; counter.reserve(umap.size());
        for (const auto& [val, cnt] : umap) counter.emplace_back(val, cnt);

        std::sort(counter.begin(), counter.end());

        vector<int> ret; ret.reserve(k);
        for (int i = 0; i < k; ++i)  {
            ret.push_back(counter[i].val);
        }
        return ret;
    }
};
```

- 二刷
    - max_heap
```cpp
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        std::unordered_map<int, int> umap;
        for (const auto& num : nums) umap[num]++;

        priority_queue<std::pair<int, int>> max_heap;
        for (const auto& [val, cnt] : umap) {
            // 这里cnt在前
            max_heap.emplace(cnt, val);
        }

        vector<int> ret; ret.reserve(k);
        while (k-- and !max_heap.empty()) {
            ret.push_back(max_heap.top().second);
            max_heap.pop();
        }
        return ret;
    }
};
```

- 三刷
    - 桶排序
    - 这个题，我觉得桶排序的思路也挺好的，有一些巧思在里面。
    - 首先，cnt上限不会大于数组的长度，所以buckets的上限确定。
    - 其次，key是cnt, val是放一个代表元素进来。因为不同元素val可能具有相同的频次。
```cpp
class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        std::unordered_map<int, int> umap;
        for (const auto& num : nums) umap[num]++;

        // 建立桶索引 key-cnt value: num1, num2, ...
        // 不同num可能出现频次一样，放一个代表即可
        vector<vector<int>> buckets(nums.size() + 1);
        for (const auto& [val, cnt] : umap) {
            buckets[cnt].push_back(val);
        }

        int res = 0;
        vector<int> ret; ret.reserve(k);
        for (int i = buckets.size() - 1; i >= 0; --i) {
            for (int c = 0; c < buckets[i].size(); ++c) {
                ret.push_back(buckets[i][c]); res++;
                if (res == k) return ret;
            }
        }
        return ret;
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

- 二刷
    - 非递归思路
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
        stack<TreeNode*> stk;

        if (root) stk.push(root);

        while (!stk.empty()) {
            auto cur = stk.top(); stk.pop();
            ret.push_back(cur->val);
            if (cur->right) stk.push(cur->right);
            if (cur->left) stk.push(cur->left);
        }

        return ret;
    }
};
```


#### [94. Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/)

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

- 二刷
    - 非递归思路
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
        stack<TreeNode*> stk;
        vector<int> ret;

        auto cur = root;
        while (cur or !stk.empty()) {
            if (cur) {
                stk.push(cur);
                cur = cur->left;
            } else {
                cur = stk.top(); stk.pop();
                ret.push_back(cur->val);
                cur = cur->right;
            }
        }

        return ret;
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

- 二刷
    - 非递归
    - 插入的顺序别错了。不管哪种遍历，都是left and right
    - 所以，插入时，都是right and left.

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
        stack<pair<TreeNode*, bool>> stk;
        
        if (root) stk.push({root, false});
        while (!stk.empty()) {
            auto [cur, visited] = stk.top(); stk.pop();
            if (visited) {
                ret.push_back(cur->val);
            }
            else {
                stk.push({cur, true});
                if (cur->right) stk.push( {cur->right, false} );
                if (cur->left) stk.push( {cur->left, false} );
            }
        }
        
        return ret;
    }
};
```

#### [102. Binary Tree Level Order Traversal](https://leetcode.com/problems/binary-tree-level-order-traversal/description/)

- 一刷
    - 有一个注意点，level_size一定要先算出来，因为后面还会向que里面加入元素，否则本层节点数错误

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
    vector<vector<int>> levelOrder(TreeNode* root) {
        queue<TreeNode*> que;
        vector<vector<int>> ret;
        if (root) que.push(root);

        while (!que.empty()) {
            int level_size = que.size(); vector<int> level; level.reserve(level_size);
            for (int i = 0; i < level_size; ++i) {
                auto node = que.front(); que.pop();
                level.push_back(node->val);
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
            }
            ret.push_back(level);
        }

        return ret;
    }
};
```

#### [107. Binary Tree Level Order Traversal II](https://leetcode.com/problems/binary-tree-level-order-traversal-ii/description/)

- 一刷
    - 我的思路：level-order，存储的时候，用deque，插在头部即可
    - 其它解：正常遍历，最后reverse.

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
    vector<vector<int>> levelOrderBottom(TreeNode* root) {
        deque<vector<int>> ret;
        queue<TreeNode*> que;
        if (root) que.push(root);

        while (!que.empty()) {
            int level_size = que.size();
            vector<int> level; level.reserve(level_size);
            for (int i = 0; i < level_size; ++i) {
                auto node = que.front(); que.pop();
                level.push_back(node->val);
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
            }
            ret.push_front(level);
        }
        std::vector<std::vector<int>> final(ret.begin(), ret.end());
        return final;
    }
};
```

#### [199. Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view/)

- 一刷
    - 我的思路：层序，访问最后一个节点即可

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
    vector<int> rightSideView(TreeNode* root) {
        queue<TreeNode*> que;
        if (root) que.push(root);
        vector<int> ret;
        while (!que.empty()) {
            int que_size = que.size();
            ret.push_back(que.back()->val); // 访问本层最后一个节点
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
            }
        }
        return ret;
    }
};
```

#### [637. Average of Levels in Binary Tree](https://leetcode.com/problems/average-of-levels-in-binary-tree/submissions/1978508476/)

- 一刷
    - 层序遍历，统计

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
    vector<double> averageOfLevels(TreeNode* root) {
        vector<double> ret;
        queue<TreeNode*> que;
        if (root) que.push(root);
        while (!que.empty()) {
            auto que_size = que.size();
            double sum = 0.0;
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                sum += node->val;
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
            }
            ret.push_back(sum / que_size);
        }
        return ret;   
    }
};
```

#### [429. N-ary Tree Level Order Traversal](https://leetcode.com/problems/n-ary-tree-level-order-traversal/)

- 一刷
    - 思路：层序遍历

```cpp
/*
// Definition for a Node.
class Node {
public:
    int val;
    vector<Node*> children;

    Node() {}

    Node(int _val) {
        val = _val;
    }

    Node(int _val, vector<Node*> _children) {
        val = _val;
        children = _children;
    }
};
*/

class Solution {
public:
    vector<vector<int>> levelOrder(Node* root) {
        vector<vector<int>> ret;
        queue<Node*> que;
        if (root) que.push(root);
        while (!que.empty()) {
            int que_size = que.size();
            vector<int> level;
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                level.push_back(node->val);
                for (auto& child : node->children) {
                    if (child) que.push(child);
                }
            }
            ret.push_back(level);
        }
        return ret;
    }
};
```

#### [515. Find Largest Value in Each Tree Row](https://leetcode.com/problems/find-largest-value-in-each-tree-row/)

- 一刷
    - 思路：层序遍历

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
    vector<int> largestValues(TreeNode* root) {
        vector<int> ret;
        queue<TreeNode*> que;
        if (root) que.push(root);
        while (!que.empty()) {
            int que_size = que.size();
            int max = INT_MIN;
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                max = std::max(max, node->val);
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
            }
            ret.push_back(max);
        }
        return ret;
    }
};
```

#### [116. Populating Next Right Pointers in Each Node](https://leetcode.com/problems/populating-next-right-pointers-in-each-node/description/)

- 一刷
    - 我的思路：层序遍历。不过我这个题我觉得出的挺有意思，需要结合链表的知识。

```cpp
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* left;
    Node* right;
    Node* next;

    Node() : val(0), left(NULL), right(NULL), next(NULL) {}

    Node(int _val) : val(_val), left(NULL), right(NULL), next(NULL) {}

    Node(int _val, Node* _left, Node* _right, Node* _next)
        : val(_val), left(_left), right(_right), next(_next) {}
};
*/

class Solution {
public:
    Node* connect(Node* root) {
        queue<Node*> que;
        if (root) que.push(root);
        while (!que.empty()) {
            int que_size = que.size();
            Node* pre = nullptr;
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                if (pre) pre->next = node;
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);

                pre = node;
            }
            pre->next = nullptr;
        }
        return root;
    }
};
```

#### [117. Populating Next Right Pointers in Each Node II](https://leetcode.com/problems/populating-next-right-pointers-in-each-node-ii/submissions/1978808914/)

- 一刷
    - 我的思路：从层序遍历的角度来说，这个题跟116确实一模一样。

```cpp
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* left;
    Node* right;
    Node* next;

    Node() : val(0), left(NULL), right(NULL), next(NULL) {}

    Node(int _val) : val(_val), left(NULL), right(NULL), next(NULL) {}

    Node(int _val, Node* _left, Node* _right, Node* _next)
        : val(_val), left(_left), right(_right), next(_next) {}
};
*/

class Solution {
public:
    Node* connect(Node* root) {
        queue<Node*> que;
        if (root) que.push(root);
        while (!que.empty()) {
            int que_size = que.size();
            Node* pre = nullptr;
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                if (pre) pre->next = node;
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);

                pre = node;
            }
            pre->next = nullptr;
        }
        return root;        
    }
};
```

#### [104. Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)

- 一刷
    - 我的思路：求深度，dfs

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
    int maxDepth(TreeNode* root) {
        if (!root) return 0;
        return 1 + std::max( maxDepth(root->left), maxDepth(root->right) );
    }
};
```

- 二刷
    - 思路：用层序遍历也行。

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
    int maxDepth(TreeNode* root) {
        queue<TreeNode*> que;
        int ret = 0;
        if (root) que.push(root);
        while (!que.empty()) {
            int que_size = que.size();
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
            }
            ++ret;
        }
        return ret;
    }
};
```

#### [111. Minimum Depth of Binary Tree](https://leetcode.com/problems/minimum-depth-of-binary-tree/)

- 一刷
    - 我的思路：深度都是dfs的范畴
    - 递归的理解还是比较抽象的，从根节点理解解法即可

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
    int minDepth(TreeNode* root) {
        if (!root) return 0;
        if (!root->left) return 1 + minDepth(root->right);
        if (!root->right) return 1 + minDepth(root->left);
        return 1 + min( minDepth(root->left), minDepth(root->right) );
        
    }
};
```

- 二刷
    - 思路：层序，第一个叶子所在层数，就是最小层

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
    int minDepth(TreeNode* root) {
        queue<TreeNode*> que;
        if (root) que.push(root);

        int level = 0;
        while (!que.empty()) {
            int que_size = que.size();
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                if (node->left == nullptr and node->right == nullptr) return level + 1;
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
            }
            ++level;
        }
        return level;
    }
};
```

#### [226. Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/) 

- 一刷
    - 我的思路：递归处理，但这里有技巧。本质是基于遍历算法来做，采用递归遍历即可。
    - 但，唯独中序遍历不行。这里要理解
    - swap/left/right, right
    - left/right/swap, right
    - left/swap/right, wrong。这里，左子树处理完了，换到右边，再处理右边。左边就漏了

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
    TreeNode* invertTree(TreeNode* root) {
        if (!root) return root;
        swap(root->left, root->right);
        invertTree(root->left);
        invertTree(root->right);
        return root;
    }
}; 
```

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
    TreeNode* invertTree(TreeNode* root) {
        if (!root) return root;
        invertTree(root->left);
        invertTree(root->right);
        swap(root->left, root->right);
        return root;
    }
};
```

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
    TreeNode* invertTree(TreeNode* root) {
        if (!root) return root;
        invertTree(root->left);
        swap(root->left, root->right);
        invertTree(root->left); // 这么写是对的，标准的中序是处理右子树
        return root;
    }
};
```

#### [101. Symmetric Tree](https://leetcode.com/problems/symmetric-tree/)

- 一刷
    - 正解：这个题的难点在于，递归的写法跟之前有区别。
        - 不能把左右子树单独当做整体处理，即以往的递归都是单独处理左右子树。所以函数接口就一个tree pointer.
        - 本题是需要把左右子树，放在一起处理，所以，接口是两个指针

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
    bool isSymmetric(TreeNode* root) {
        if (!root) return true;
        return compare(root->left, root->right);
    }
    bool compare(TreeNode* left, TreeNode* right) {
        if (left == nullptr and right == nullptr) return true;
        else if (left != nullptr and right == nullptr) return false;
        else if (left == nullptr and right != nullptr) return false;
        else if (left->val != right->val) return false;

        return compare(left->left, right->right) and compare(left->right, right->left);
    }
};
```

#### [222. Count Complete Tree Nodes](https://leetcode.com/problems/count-complete-tree-nodes/description/)

- 一刷
    - 我的思路：这个题我觉得和完全二叉树没啥关系，preorder遍历即可

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
    int countNodes(TreeNode* root) {
        if (!root) return 0;
        int ret = 1;
        ret += countNodes(root->left);
        ret += countNodes(root->right);
        return ret;
    }
};
```

#### [110. Balanced Binary Tree](https://leetcode.com/problems/balanced-binary-tree/description/)

- 一刷
    - 次优解
        - 一开始没想到递归求解，是因为左右子树的高度差满足是不够的，左右子树内部还需要满足。
        - 思路上，如果没解法，就直接往遍历上靠就好。
        - 是不是可以这么理解，遍历所有的节点，如果左右子树都满足，是不是就没问题了。

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
    bool isBalanced(TreeNode* root) {
        if (!root) return true;

        if ( abs( depth(root->left) - depth(root->right) ) > 1 ) return false; // weired，访问根节点。但此时用的是根节点的左右孩子，本质还是访问根节点
        return isBalanced(root->left) and isBalanced(root->right);  
    }
    int depth(TreeNode* root) {
        if (!root) return 0;
        else return 1 + std::max( depth(root->left), depth(root->right) );
    }
};
```

- 二刷

你的思路本质：自顶向下（Top-down）
- 你的代码逻辑是：
    - 检查当前节点：左右子树高度差 ≤ 1？
    - 如果满足，递归检查左子树是否平衡
    - 递归检查右子树是否平衡

所以，子树的高度会被反复计算。

更优解法的思维：自底向上（Bottom-up）
核心转变：不让每个节点独立计算深度，而是让深度计算和平衡检查同时进行，一次遍历完成。

```cpp
int dfs(TreeNode* root) {
    if (!root) return 0;
    int left = dfs(root->left);
    if (left == -1) return -1;   // 左子树已经不平衡，直接返回
    int right = dfs(root->right);
    if (right == -1) return -1;  // 右子树已经不平衡
    if (abs(left - right) > 1) return -1;
    return 1 + max(left, right);
}
```

这个代码在做什么？
- 后序遍历：先走到最左下的叶子，然后向上返回。
    - 返回值有两个角色：
    - 如果是正常数字 → 表示这棵树的高度
    - 如果是 -1 → 表示这棵树不平衡（“坏消息”向上传递）
- 一旦发现不平衡，立即“短路”：不再继续检查其他分支。

引入-1是个非常秒的解法， 深度和判断一起做。

这个题，两种做法，本质是先序和后序的差异，top-down vs bottom up。所以，本题很有启发性，主要是洞悉了先序和后序的差异

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
    bool isBalanced(TreeNode* root) {
        return dfs(root) != -1;
    }
    int dfs(TreeNode* root) {
        if (!root) return 0;

        int left = dfs(root->left);
        if (left == -1) return -1;

        int right = dfs(root->right);
        if (right == -1) return -1;

        if ( abs(left - right) > 1 ) return -1;
        return 1 + max(left, right);
    }
};
```

#### [257. Binary Tree Paths](https://leetcode.com/problems/binary-tree-paths/)

- 一刷
    - 我的思路：我有搜索的基础，所以做起来简单点。
    - 虽然是二叉树，有点关系，但关系不大。代码的框架是搜索的框架。
    - 有一点注意，边界是判断叶子，不是空指针

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
    vector<string> binaryTreePaths(TreeNode* root) {
        if (!root) return {};

        string path; vector<string> ret;
        preorder(root, path, ret);
        return ret;
    }

    void preorder(TreeNode* root, string& path, vector<string>& ret) {
        string suffix = to_string(root->val); 
        if (!root->left and !root->right) { 
            path += suffix;
            ret.push_back(path); 
            // 返回前需要回溯
            backtracing(suffix, path);
            return; 
        }

        suffix += "->";
        path += suffix; 

        if (root->left) preorder(root->left, path, ret);
        if (root->right) preorder(root->right, path, ret);

        // 返回前需要回溯
        backtracing(suffix, path);
        return;
    }


    void backtracing(const string& suffix, string& path) {
        for (int i = 0 ; i < suffix.size(); ++i) path.pop_back();
    }
};
```

- 二刷
    - 思路：下面的写法，不用显示的回溯。优雅。

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
    vector<string> binaryTreePaths(TreeNode* root) {
        vector<string> ret;
        if (!root) return ret;
        preorder(root, "", ret);
        return ret;
    }

    void preorder(TreeNode* root, string path, vector<string>& ret) {
        if (!root->left and !root->right) {
            ret.push_back(path + to_string(root->val));
            return;
        }

        if (root->left) preorder(root->left, path + to_string(root->val) + "->", ret);
        if (root->right) preorder(root->right, path + to_string(root->val) + "->", ret);
    }
};
```

#### [404. Sum of Left Leaves](https://leetcode.com/problems/sum-of-left-leaves/submissions/1979963156/)

- 一刷
    - 我的思路：这个题不难，灵活点处理。
    - 做的多了，遍历的时候，有两种条件
        - 一是，判断到空
        - 而是，不判断到空，判断到叶子
    - 这两种情况，看题目需要，灵活处理。
    - 这个题不需要回溯
    
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
    int sumOfLeftLeaves(TreeNode* root) {
           vector<int> ret;
           preorder(root, ret, false);
           return accumulate(ret.begin(), ret.end(), 0);
    }
    void preorder(TreeNode* root, vector<int>& ret, bool is_left) {
        if (!root->left and !root->right and is_left) {
            ret.push_back(root->val);
        }

        if (root->left) preorder(root->left, ret, true);
        if (root->right) preorder(root->right, ret, false);
    }
};
```

#### [513. Find Bottom Left Tree Value](https://leetcode.com/problems/find-bottom-left-tree-value/)

- 一刷
    - 我的思路：层序遍历，每层第一个节点更新即可
    - 不过这里有一个优化点，层序的顺序自己定，也可以从右到左。
    - 那么到最后的节点，返回即可

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
    int findBottomLeftValue(TreeNode* root) {
        queue<TreeNode*> que;
        int ret = 0;
        if (root) que.push(root);   
        while (!que.empty()) {
            int que_size = que.size();
            for (int i = 0; i < que_size; ++i) {
                auto node = que.front(); que.pop();
                if (node->left) que.push(node->left);
                if (node->right) que.push(node->right);
                if (i == 0) ret = node->val;
            }
        }
        return ret;
    }
};
```

#### [112. Path Sum](https://leetcode.com/problems/path-sum/description/)

- 一刷
    - 我的思路：不是二叉树的题目，本质是搜索。这个题我借鉴了257的不显示回溯的写法
    - 这个题遍历的技巧是，不要到空指针，到叶子就行。当然，这也是搜索的思路

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
    bool hasPathSum(TreeNode* root, int targetSum) {
        if (!root) return false;
        return preorder(root, 0, targetSum);
    }

    bool preorder(TreeNode* root, int sum, int target) {
        if (!root->left and !root->right) {
            if (sum + root->val == target) return true;
            else return false;
        }

        if (root->left) {
            auto ret = preorder(root->left, sum + root->val, target);
            if (ret) return true;
        }

        if (root->right) return preorder(root->right, sum + root->val, target);
        else return false;
    }
};
```

#### [105. Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)

- 一刷
    - 我的思路：从中序找根，然后递归左右区间，构成左右子树。
    - 注意点：区间容易写错，我左开右闭。
    - 先序区间我一直忘了排除根节点

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
    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder) {
        return build( preorder, 0, preorder.size(), inorder, 0, inorder.size() );
    }
    TreeNode* build(vector<int>& preorder, int x, int y, vector<int>& inorder, int b, int e) {
        if (x >= y or b >= e) return nullptr;

        int mid;
        for (mid = b; mid < e; ++mid) {
            if (inorder[mid] == preorder[x]) break;
        }

        auto root = new TreeNode(inorder[mid]);
        root->left = build(  preorder, x + 1, x + 1 + mid - b , inorder, b, mid );
        root->right = build( preorder, x + 1 + mid - b, y,   inorder, mid + 1, e );
        return root;
    }
};
```

#### [654. Maximum Binary Tree](https://leetcode.com/problems/maximum-binary-tree/submissions/1982519675/)

- 一刷
    - 我的思路：跟上到题目思路完全一样，先找根，然后划分区间。递归构建
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
    TreeNode* constructMaximumBinaryTree(vector<int>& nums) {
        return build(nums, 0, nums.size());
    }

    TreeNode* build(vector<int>& nums, int b, int e) {
        if (b >= e) return nullptr;

        int root_idx = b;
        int max = nums[root_idx];
        for (int i = b + 1; i < e; ++i) {
            if (max < nums[i]) { root_idx = i; max = nums[i]; }
        }

        auto* root = new TreeNode(max);
        root->left = build(nums, b, root_idx);
        root->right = build(nums, root_idx + 1, e);

        return root;
    }
};
```

#### [617. Merge Two Binary Trees](https://leetcode.com/problems/merge-two-binary-trees/)

- 一刷
    - 思路：不要用非递归的思路去考虑这个问题，还是要更抽象一些。
    - 我是参照了grandyang的思路，解法一也是递归，但它其实是一个更偏重非递归思考问题的办法，就不如下面这个简单

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
    TreeNode* mergeTrees(TreeNode* root1, TreeNode* root2) {
        if (!root1) return root2;
        if (!root2) return root1;

        auto* node = new TreeNode( root1->val + root2->val );
        node->left = mergeTrees(root1->left, root2->left);
        node->right = mergeTrees(root1->right, root2->right);
        return node;
    }
};
```

#### [98. Validate Binary Search Tree](https://leetcode.com/problems/validate-binary-search-tree/)

- 一刷
    - 我的思路：非线性的转化成线性

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
    bool isValidBST(TreeNode* root) {  
        vector<int> res;
        inorder(root, res);
        
        for (int i = 1; i < res.size(); ++i) {
            if (res[i - 1] >= res[i]) return false;
        }

        return true;
    }
    void inorder(TreeNode* root, vector<int>& res) {
        if (!root) return;
        inorder(root->left, res);
        res.push_back(root->val);
        inorder(root->right, res);
    }
};
```

#### [700. Search in a Binary Search Tree](https://leetcode.com/problems/search-in-a-binary-search-tree/)

- 一刷
    - 我的思路：按照定义查找即可

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
    TreeNode* searchBST(TreeNode* root, int val) {
        if (!root) return nullptr;

        if (root->val == val) return root;
        else if (val < root->val) return searchBST(root->left, val);
        else return searchBST(root->right, val);
    }
};
```

#### [530. Minimum Absolute Difference in BST](https://leetcode.com/problems/minimum-absolute-difference-in-bst/submissions/1983324106/)

- 一刷
    - 我的思路：inorder遍历即可，但没必要遍历完，再处理。可以遍历中处理。
    - 注意点：prev指针是引用，传值没用。

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
    int getMinimumDifference(TreeNode* root) {
        int min = INT_MAX;
        TreeNode* prev = nullptr;
        inorder(root, prev, min);
        return min;
    }

    void inorder(TreeNode* root, TreeNode*& pre, int& min) {
        if (!root) return;

        inorder(root->left, pre, min);
        if (pre) { min = std::min(min, root->val - pre->val); }

        pre = root;
        inorder(root->right, pre, min);
    }
};
```

#### [501. Find Mode in Binary Search Tree](https://leetcode.com/problems/find-mode-in-binary-search-tree/submissions/1983340236/)

- 一刷
    - 思路：通过这两道题，总结出BST的一些通用解题思路。
    - 如果要避免额外的空间，就要在inorder遍历中，就地处理。
    - 同时，就地处理的，一定是状态，这意味着，一定要用引用保存状态。
    - 我这个题，就是丢失了状态，导致一直没过。

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
    vector<int> findMode(TreeNode* root) {
        vector<int> res;
        TreeNode* pre = nullptr;
        int cnt = 1;
        int max_cnt = 0;
        inorder(root, pre, cnt, max_cnt, res);
        return res;
    }
    void inorder(TreeNode* root, TreeNode*& pre, int& cnt, int& max_cnt, vector<int>& res) {
        if (!root) return;

        inorder(root->left, pre, cnt, max_cnt, res);

        if (pre) {
            cnt = pre->val == root->val ?cnt + 1:1;
        }
        if (cnt == max_cnt) { res.push_back(root->val); }
        if (cnt > max_cnt) { res.clear(); res.push_back(root->val); max_cnt = cnt; }

        pre = root;
        inorder(root->right, pre, cnt, max_cnt, res);
    }
};
```

#### [701. Insert into a Binary Search Tree](https://leetcode.com/problems/insert-into-a-binary-search-tree/)

- 一刷
    - 思路：这题其实反而要用整体的抽象思路来解决，还是递归。但是grandyang的思路好于随想录
    - 核心都是，都叶子再插入。然后就是二分的思路。插入左右子树，同时更新左右子树跟节点

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
    TreeNode* insertIntoBST(TreeNode* root, int val) {
        if (!root) return new TreeNode(val);
        if (val < root->val) root->left = insertIntoBST(root->left, val);
        else root->right = insertIntoBST(root->right, val);
        return root;
    }
};
```

#### [450. Delete Node in a BST](https://leetcode.com/problems/delete-node-in-a-bst/)

- 一刷
    - 思路：这题我觉得随想录的思路比价好，拆的比较细。
    - BST可以利用二分的思路去递归。写法上跟上一道题类似，最后一定是要更新左右子树的指针。


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
    TreeNode* deleteNode(TreeNode* root, int key) {
        if (!root) return nullptr;

        if (root->val == key ) {
            // case1
            if (!root->left and !root->right) { delete root; return nullptr; }

            // case2
            if (root->left and !root->right) { auto tmp = root; root = root->left; delete tmp; return root; }

            // case3
            if (root->right and !root->left) { auto tmp = root; root = root->right; delete tmp; return root; }

            // case4
            auto cur = root->right;
            while (cur->left) cur = cur->left;

            cur->left = root->left;
            auto tmp = root;
            root = root->right;
            delete tmp;

            return root;
        }

        if (key < root->val) root->left = deleteNode(root->left, key);
        else root->right = deleteNode(root->right, key);

        return root;
    }
};
```

- 二刷
    - 思路：这个是一般写法，不针对BST
    - 后续遍历，同时把左子树挂到右子树左下

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
    TreeNode* deleteNode(TreeNode* root, int key) {
        if (!root) return nullptr;

        root->left = deleteNode(root->left, key);
        root->right = deleteNode(root->right, key);

        if (root->val == key) {
            if (!root->left) {
                auto tmp = root;
                root = root->right;
                delete tmp;
                return root;
            }

            if (!root->right) {
                auto tmp = root;
                root = root->left;
                delete tmp;
                return root;
            }

            auto cur = root->right;
            while (cur->left) cur = cur->left;
            cur->left = root->left;

            auto tmp = root;
            root = root->right;
            delete tmp;
            return root;
        }

        return root;
    }
};
```

- 三刷
    - 精简一刷代码
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
    TreeNode* deleteNode(TreeNode* root, int key) {
        if (!root) return nullptr;

        if (root->val == key ) {
            if (!root->left) { auto tmp = root; root = root->right; delete tmp; return root; }
            if (!root->right) { auto tmp = root; root = root->left; delete tmp; return root; }

            auto cur = root->right;
            while (cur->left) cur = cur->left;

            cur->left = root->left;
            auto tmp = root;
            root = root->right;
            delete tmp;

            return root;
        }

        if (key < root->val) root->left = deleteNode(root->left, key);
        else root->right = deleteNode(root->right, key);

        return root;
    }
};
```

#### [669. Trim a Binary Search Tree](https://leetcode.com/problems/trim-a-binary-search-tree/submissions/1984320002/)

- 一刷
    - 思路：这个题我觉得随想录的思路是没问题的，这个题看起来简单，但如果有BST的惯性，只能按照随想录的办法来做。
    - 不过，这个题我最终按照grandyang的思路来做，因为简单
        - 核心做法还是先根遍历，递归。非常抽象。
        - 但，能这么做的核心是利用了BST的特性
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
    TreeNode* trimBST(TreeNode* root, int low, int high) {
        if (!root) return nullptr;

        if (root->val < low) return trimBST(root->right, low, high);
        if (high < root->val) return trimBST(root->left, low, high);
        root->left = trimBST(root->left, low, high);
        root->right = trimBST(root->right, low, high);

        return root;
    }
};
```

#### [108. Convert Sorted Array to Binary Search Tree](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/)

- 一刷
    - 思路：线性需求转化为非线性序列，有了之前前序 + 中序的那道题目，积累经验。
    - 递归划分区间即可。BST二分划分即可

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
    TreeNode* sortedArrayToBST(vector<int>& nums) {
        return helper(nums, 0, nums.size() - 1);
    }

    TreeNode* helper(vector<int>& nums, int low, int high) {
        // 闭区间 [low, high]
        if (low > high) return nullptr;

        int mid = low + (high - low) / 2;
        TreeNode* root = new TreeNode(nums[mid]);
        root->left = helper(nums, low, mid - 1);
        root->right = helper(nums, mid + 1, high);
        return root;
    }
};
```