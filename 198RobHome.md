你是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。

给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额

思路：找出不相邻组合的最大值，动态规划
```python
class Solution(object):
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        preprofit = 0
        curprofit = 0
        n = len(nums)

        for i in range(n):
            temp = curprofit
            curprofit = max(preprofit + nums[i], curprofit)
            preprofit = temp

        return curprofit
```
