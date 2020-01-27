一个机器人位于一个 m x n 网格的左上角 （起始点在下图中标记为“Start” ）。
机器人每次只能向下或者向右移动一步。机器人试图达到网格的右下角（在下图中标记为“Finish”）。
问总共有多少条不同的路径？
思路：因为起点和终点已经固定死了，并且机器人只能采用向下和向右两种方式，所以可以采用递归或者，直接用数学推理，这里采用的是把向右的步骤排到整个步骤中，有多少种排法，就有多少条路经。
```python
class Solution(object):
    def uniquePaths(self, m, n):
        """
        :type m: int
        :type n: int
        :rtype: int
        """
        return int(math.factorial(m+n-2)/math.factorial(m-1)/math.factorial(n-1))
```
