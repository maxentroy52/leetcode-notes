[TOC]

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

### 无分类

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

### 无分类

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