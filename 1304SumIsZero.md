给你一个整数 n，请你返回 任意 一个由 n 个 各不相同 的整数组成的数组，并且这 n 个数相加和为 0 。

思路：　先添加ｎ-1个数，最后一个添加的数是前n-1个数和的负数。
```python
class Solution(object):
    def sumZero(self, n):
        """
        :type n: int
        :rtype: List[int]
        """
        ans = [x for x in range(n-1)]
        ans.append(-sum(ans))

        return ans
```
