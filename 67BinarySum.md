给定两个二进制字符串，返回他们的和（用二进制表示）。

输入为非空字符串且只包含数字 1 和 0。

```python
示例：  
输入: a = "11", b = "1"  
输出: "100"
```
思路：转化成十进制，求和，再把结果转化成二进制。
```python
class Solution(object):
    def addBinary(self, a, b):
        """
        :type a: str
        :type b: str
        :rtype: str
        """
        return "{0:b}".format(int(a, 2) + int(b, 2))
```
