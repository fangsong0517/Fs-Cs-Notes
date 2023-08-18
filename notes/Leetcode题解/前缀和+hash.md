[TOC]

# 前缀和+hash

523，560，974，525，1124，528，497，1248，930

#### [523. 连续的子数组和](https://leetcode-cn.com/problems/continuous-subarray-sum/)(是否和为K倍数)

给你一个整数数组 `nums` 和一个整数 `k` ，编写一个函数来判断该数组是否含有同时满足下述条件的连续子数组：

- 子数组大小 **至少为 2** ，且
- 子数组元素总和为 `k` 的倍数。

如果存在，返回 `true` ；否则，返回 `false` 。

如果存在一个整数 `n` ，令整数 `x` 符合 `x = n * k` ，则称 `x` 是 `k` 的一个倍数。`0` 始终视为 `k` 的一个倍数。

 

**示例 1：**

```
输入：nums = [23,2,4,6,7], k = 6
输出：true
解释：[2,4] 是一个大小为 2 的子数组，并且和为 6 。
```

**示例 2：**

```
输入：nums = [23,2,6,4,7], k = 6
输出：true
解释：[23, 2, 6, 4, 7] 是大小为 5 的子数组，并且和为 42 。 
42 是 6 的倍数，因为 42 = 7 * 6 且 7 是一个整数。
```

**示例 3：**

```
输入：nums = [23,2,6,4,7], k = 13
输出：false
```

 

```cpp
class Solution {
public:
    bool checkSubarraySum(vector<int>& nums, int k) {
        unordered_map<int, int>m;
        int sum = 0, n = nums.size();
        m[0] = -1;//如果整个数组和刚好为k，也满足
        for(int i = 0; i < n; i++) {
            sum += nums[i];
            if(k != 0) {
                sum = sum % k;
            }
            if(m.find(sum) != m.end()) {
                if(i - m[sum] > 1) {
                    return true;
                }
            } else {
                m[sum] = i;
            }
        }
        return false;
    }
};
```

#### [560. 和为K的子数组](https://leetcode-cn.com/problems/subarray-sum-equals-k/)（和为K的个数）

给定一个整数数组和一个整数 **k，**你需要找到该数组中和为 **k** 的连续的子数组的个数。

**示例 1 :**

```
输入:nums = [1,1,1], k = 2
输出: 2 , [1,1] 与 [1,1] 为两种不同的情况。
```

```cpp
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        unordered_map<int, int>m;
        m[0] = 1;
        int temp = 0, ret;
        for(int i = 0; i < nums.size(); i++) {
            temp += nums[i];
            ret += m[temp - k];
            m[temp]++;
        }
        return ret;
    }
};
```

#### [974. 和可被 K 整除的子数组](https://leetcode-cn.com/problems/subarray-sums-divisible-by-k/)（和为K的倍数的个数）

给定一个整数数组 `A`，返回其中元素之和可被 `K` 整除的（连续、非空）子数组的数目。

**示例：**

```
输入：A = [4,5,0,-2,-3,1], K = 5
输出：7
解释：
有 7 个子数组满足其元素之和可被 K = 5 整除：
[4, 5, 0, -2, -3, 1], [5], [5, 0], [5, 0, -2, -3], [0], [0, -2, -3], [-2, -3]
```

```cpp
class Solution {
public:
    int subarraysDivByK(vector<int>& nums, int k) {
        unordered_map<int, int>m;
        int n = nums.size(), sum = 0, ret = 0;
        m[0] = 1;
        for(int i = 0; i < nums.size(); i++) {
            sum += nums[i];
            sum = (sum % k + k) % k;
            ret += m[sum];
            m[sum]++;
        }
        return ret;
    }
};
```

#### [525. 连续数组](https://leetcode-cn.com/problems/contiguous-array/)

给定一个二进制数组 `nums` , 找到含有相同数量的 `0` 和 `1` 的最长连续子数组，并返回该子数组的长度。

**示例 1:**

```
输入: nums = [0,1]
输出: 2
说明: [0, 1] 是具有相同数量 0 和 1 的最长连续子数组。
```

```cpp
class Solution {
public:
    int findMaxLength(vector<int>& nums) {
        unordered_map<int, int>m;
        m[0] = 0;
        int sum = 0, mmax = 0, n = nums.size();
        for(int i = 0; i < n; i++) {
            sum += nums[i] * 2 - 1;
            if(m.count(sum)) {
                mmax = max(mmax, i + 1 - m[sum]);
            } else {
                m[sum] = i + 1;
            }
        }
        return mmax;;
    }
};
```

#### [1124. 表现良好的最长时间段](https://leetcode-cn.com/problems/longest-well-performing-interval/)

给你一份工作时间表 `hours`，上面记录着某一位员工每天的工作小时数。

我们认为当员工一天中的工作小时数大于 `8` 小时的时候，那么这一天就是「**劳累的一天**」。

所谓「表现良好的时间段」，意味在这段时间内，「劳累的天数」是严格 **大于**「不劳累的天数」。

请你返回「表现良好时间段」的最大长度。

**示例 1：**

```
输入：hours = [9,9,6,0,6,6,9]
输出：3
解释：最长的表现良好时间段是 [9,9,6]。
```

```cpp
class Solution {
public:
    int longestWPI(vector<int>& hours) {
        int n = hours.size(), maxlen = 0, sum = 0;
        unordered_map<int, int> m;
        for(int i = 0; i < n; i++) {
            sum += hours[i] > 8 ? 1 : -1;
            if(sum > 0) maxlen = i + 1;//和大于0，全部满足条件
            else {
                if(m.count(sum - 1))//第一次出现的前一种状态（sum-1）存在吗
                    maxlen = max(maxlen, i - m[sum - 1]);
                if(!m.count(sum)) //存下第一次出现的当前状态
                    m[sum] = i;
            }
        }
        return maxlen;
    }
};
```

#### [930. 和相同的二元子数组](https://leetcode-cn.com/problems/binary-subarrays-with-sum/)（和为K的子数组个数）

给你一个二元数组 `nums` ，和一个整数 `goal` ，请你统计并返回有多少个和为 `goal` 的 **非空** 子数组。

**子数组** 是数组的一段连续部分。

**示例 1：**

```
输入：nums = [1,0,1,0,1], goal = 2
输出：4
解释：
如下面黑体所示，有 4 个满足题目要求的子数组：
[1,0,1,0,1]
[1,0,1,0,1]
[1,0,1,0,1]
[1,0,1,0,1]
```

```cpp
class Solution {
public:
    int numSubarraysWithSum(vector<int>& nums, int goal) {
        unordered_map<int, int>m;
        m[0] = 1;
        int temp = 0, ret = 0;
        for(int i = 0; i < nums.size(); i++) {
            temp += nums[i];
            ret += m[temp - goal];
            m[temp]++;
        }
        return ret;
    }
};
```

















