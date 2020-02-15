思路：左右同时向里找到和的1/3处。没有就是False
```python
class Solution(object):
    def canThreePartsEqualSum(self, A):
        N = len(A)
        s=sum(A)

        if s%3!=0:
            return False

        left = right = 0
        i, j = 0, N-1
        avg = s/3

        while left != avg and i < N:
            left+=A[i]
            i+=1

        while right!=avg and j > -1:
            right+=A[j]
            j-=1

        if i<=j and left==right==avg:
            return True

        return False
```
