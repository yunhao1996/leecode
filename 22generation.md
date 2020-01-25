题目描述：给出 n 代表生成括号的对数，请你写出一个函数，使其能够生成所有可能的并且有效的括号组合。
```python
n = 3,结果如下：
[
  "((()))",
  "(()())",
  "(())()",
  "()(())",
  "()()()"
]

```
思路：生成的括号要合法，前提是每个右括号需要一个与之对应的左括号与之对应。程序运用递归的思想，先生成左括号，再生成右括号，而且要保证递归过程中生成的左括号数量要比右括号的数目要多。
程序：
```python
class Solution(object):
    def generateParenthesis(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        res = []

	def dfs(left,right,tmp):
		if left==n and right==n:
			res.append(tmp)
			return
		if left<n:
			dfs(left+1,right,tmp+"(")
		if left>right and right<n:
			dfs(left,right+1,tmp+")")
	dfs(0,0,"")
	return res
```
