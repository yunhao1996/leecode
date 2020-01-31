给定一个由整数组成的非空数组所表示的非负整数，在该数的基础上加一。最高位数字存放在数组的首位， 数组中每个元素只存储单个数字。你可以假设除了整数 0 之外，这个整数不会以零开头。

示例：
```python
输入: [1,2,3]
输出: [1,2,4]
解释: 输入数组表示数字 123。
```

思路： 先求出表示的整数，然后加1， 最后转化成字符，输出列表
Code:
```python
class Solution(object):
    def plusOne(self, digits):
        """
        :type digits: List[int]
        :rtype: List[int]
        """
        sum_str = 0
        n = len(digits)

        for i in range(n):
            sum_str += 10 **(n-i-1) * digits[i]
        
        sum_str1 = str(sum_str + 1)
        return [int(j) for j in sum_str1]
```
