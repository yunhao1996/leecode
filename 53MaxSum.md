给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。
```python
输入: [-2,1,-3,4,-1,2,1,-5,4],
输出: 6
解释: 连续子数组 [4,-1,2,1] 的和最大，为 6。
```
思路：贪心算法。从前向后，遍历最大的序列和。需要一个当前的最大值和最终的最大值。遍历更新。
````python
class Solution(object):
    def maxSubArray(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        n = len(nums)
        current_max = all_max = nums[0]

        for i in range(1, n):
            current_max = max(nums[i], current_max + nums[i])
            all_max = max(all_max, current_max)

        return all_max
```
