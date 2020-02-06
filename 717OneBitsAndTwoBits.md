```
class Solution(object):
    def isOneBitCharacter(self, bits):
        """
        :type bits: List[int]
        :rtype: bool
        """
        #线性扫描
        n = len(bits)
        i = 0
        while i <  (n -1):
            i += bits[i] + 1
        
        return i==n-1
```
