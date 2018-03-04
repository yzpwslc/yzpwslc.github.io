---
layout: post
title:  "leet766"
author: "yzpwslc"
date: 2018-03-04 22:13
---

<p>题目：判断一个矩阵是否为托普利茨矩阵</p>
<p>分析：遍历二维数组，相应数据比对，不一致立刻返回</p>
<p>代码如下：</p>
{% highlight python %}
import json
class Solution(object):
    def isToeplitzMatrix(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: bool
        """
        m = len(matrix)
        n = len(matrix[0])
        for i in range(m - 1):
            for j in range(n - 1):
                if matrix[i][j] != matrix[i + 1][j + 1]:
                    return  False
        return True



def stringToInt2dArray(input):
    return json.loads(input)


def main():
    import sys
    def readlines():
        for line in sys.stdin:
            yield line.strip('\n')

    lines = readlines()
    while True:
        try:
            line = lines.next()
            matrix = stringToInt2dArray(line)

            ret = Solution().isToeplitzMatrix(matrix)

            out = (ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
{% endhighlight%}
<p>思考：python代码确实可以简短，自由，但不明白leetcode上的用户为何一味追求简短，看到一个方案，使用了all()方法，虽然代码看起来上减少一重循环，但感觉使用该方法必定遍历所有元素，实际并不节省资源，有时间要找个巨大的矩阵比对一下</p>
