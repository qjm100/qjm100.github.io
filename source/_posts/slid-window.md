---
title: 滑动窗口
date: 2026-01-29 12:30:47
tags:
  - 算法
  - 滑动窗口
---
> 算法基础之一，用于解决数组和字符串相关的问题。

### 使用python做题的一些奇淫技巧 

1. defaultdict(Type) 可以自动初始化字典中的键，避免了在访问不存在的键时引发 KeyError 异常，简单来说是一个**hash表**，删除键值对使用del。
2. enumerate(iterable) 函数用于在遍历可迭代对象时，同时获取元素的索引和值，返回一个包含索引和值的元组。

# 定长滑动窗口
给定一个数组 `nums` 和一个整数 `k`，请你找出所有长度为 `k` 的子数组的最大值。

```python
#e.g.
nums = [1,3,-1,-3,5,3,6,7]
k = 3
ma = 0
cou = 0
for right, x in enumerate(nums):
  cou += x
  if right - k + 1 < 0:
    continue
  ma = max(ma, cou)
  cou -= nums[right - k + 1]

print(ma)  # Output: 16
  
```

# 不定长滑动窗口

不定长滑动窗口分为三类：求最长子串、求最短子串、求符合条件的子串个数。
## 求最短/最长子串

1. 越短越合法：求最长子串

  e.g. ![leetcode 1004](https://leetcode.cn/problems/max-consecutive-ones-iii/description/)
```python
class Solution:
    def longestOnes(self, nums: List[int], k: int) -> int:
        ma = left = 0
        same = defaultdict(int)
        for right, x in enumerate(nums):
            same[x] += 1
            while same[0] > k:
                same[nums[left]] -= 1
                left += 1
            ma = max(ma, right-left+1)
        return ma
```
2. 越长越合法：求最短子串

## 符合条件的子串个数

1. 越短越好

2. 越长越好

3. 恰好型滑动窗口
