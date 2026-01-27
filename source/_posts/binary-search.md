---
title: binary-search
date: 2026-01-24 15:52:34
tags: 
- 算法 
- 二分
---

# 二分查找算法

> 常见的二分查找一般用于有序队列中快速查找一个元素的位置，时间复杂度为 * O(log n)*。

--------------------------------

但我们也可以将二分查找的思想应用到其他问题中，比如：
一个问题的**解空间是单调**的，我们可以通过二分查找来快速定位解。

## 🌰举一个例子：

当题目当题目要求我们在一个数组中找到一个满足某种条件的最大值或最小值时，我们可以考虑使用二分查找来优化搜索过程。

我经常使用的模板是开区间：

```python
# 求最小
class Solution:
    # 计算满足 check(x) == True 的最小整数 x
    def binarySearchMin(self, nums: List[int]) -> int:
        # 二分猜答案：判断 mid 是否满足题目要求
        def check(mid: int) -> bool:
            # TODO

        left =   # 循环不变量：check(left) 恒为 False
        right =   # 循环不变量：check(right) 恒为 True
        while left + 1 < right:  # 开区间不为空
            mid = (left + right) // 2
            if check(mid):  # 说明 check(>= mid 的数) 均为 True
                right = mid  # 接下来在 (left, mid) 中二分答案
            else:  # 说明 check(<= mid 的数) 均为 False
                left = mid  # 接下来在 (mid, right) 中二分答案
        # 循环结束后 left+1 = right
        # 此时 check(left) == False 而 check(left+1) == check(right) == True
        # 所以 right 就是最小的满足 check 的值
        return right
-------------------------------------------
#求最大
class Solution:
    # 计算满足 check(x) == True 的最大整数 x
    def binarySearchMax(self, nums: List[int]) -> int:
        # 二分猜答案：判断 mid 是否满足题目要求
        def check(mid: int) -> bool:
            # TODO
        left =   # 循环不变量：check(left) 恒为 True
        right =   # 循环不变量：check(right) 恒为 False
        while left + 1 < right:
            mid = (left + right) // 2
            if check(mid):
                left = mid  # 注意这里更新的是 left，和上面的模板反过来
            else:
                right = mid
        # 循环结束后 left+1 = right
        # 此时 check(left) == True 而 check(left+1) == check(right) == False
        # 所以 left 就是最大的满足 check 的值
        return left  # check 更新的是谁，最终就返回谁
#来自灵茶山
```
> 部分题目可以优化二分边界，减少二分次数，从而减少代码运行时间。对于初次接触二分答案的同学，无需强求自己写出最优的代码，设定一个比较大的二分上界也是可以的。


