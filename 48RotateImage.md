题目：给定一个 n × n 的二维矩阵表示一个图像。
将图像顺时针旋转 90 度。
思路： 转置矩阵，每一行反向排序
```python
class Solution(object):
    def rotate(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: None Do not return anything, modify matrix in-place instead.
        """
        n = len(matrix[0])
        for i in range(n):
            for j in range(i, n):
                matrix[j][i], matrix[i][j] = matrix[i][j], matrix[j][i]
        
        for i in range(n):
            matrix[i].reverse()
```
