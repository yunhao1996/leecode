给定一个数组，它的第 i 个元素是一支给定股票第 i 天的价格。

如果你最多只允许完成一笔交易（即买入和卖出一支股票），设计一个算法来计算你所能获取的最大利润。

注意你不能在买入股票前卖出股票。

思路：更新最小价格和最大利润

```python
class Solution(object):
    def maxProfit(self, prices):
        """
        :type prices: List[int]
        :rtype: int
        """
        n = len(prices)
        if n == 0 or n == 1:
            return 0
        
        min_price = prices[0]
        profit = 0
        
        for i in range(1,  n):
            if prices[i] < min_price:
                min_price = prices[i]
           
            if prices[i] - min_price > profit:
                profit = prices[i] - min_price
        
        return profit
```
