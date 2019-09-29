@[TOC](LeetCode 1.Two Sum)
第一次写，不是很懂。
# 题目

给定一个整数数组 `nums` 和一个目标值 `target`，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。


# 示例
> 给定 nums = [2, 7, 11, 15], target = 9
因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]

# 解法
一次循环，先将目标值减去第一个数，然后将这个数加入到字典中，如果字典中能找到另外一个数与当前的数加和满足目标，就输出。
```python3
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        dic = {}
        for index, num in enumerate(nums):
            another_num = target - num
            if another_num in dic:
                return [dic[another_num], index]
            dic[num] = index
        return None
```
