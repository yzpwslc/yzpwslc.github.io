---
layout: post
title:  "leet682"
author: "yzpwslc"
date: 2018-03-04 23:38
---

<p>题目：棒球运动计分，不同字符代表不同分数操作，经过指令列表计算出分数</p>
<p>分析：没有特别的想法，按常规办法解决</p>
<p>代码如下：</p>
{% highlight python %}
import json
class Solution(object):
    def calPoints(self, ops):
        """
        :type ops: List[str]
        :rtype: int
        """
        validList = []
        for c in ops:
            if c == 'C':
                validList.pop()
            elif c == 'D':
                validList.append(validList[-1] * 2)
            elif c == '+':
                validList.append(validList[-1] + validList[-2])
            else:
                validList.append(int(c))
        return sum(validList)



def stringToStringArray(input):
    return json.loads(input)


def intToString(input):
    if input is None:
        input = 0
    return str(input)


def main():
    import sys
    def readlines():
        for line in sys.stdin:
            yield line.strip('\n')

    lines = readlines()
    while True:
        try:
            line = lines.next()
            ops = stringToStringArray(line)

            ret = Solution().calPoints(ops)

            out = intToString(ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
{% endhighlight%}
<p>思考：leetcode中提交代码从不检查异常处理;
leetcode运行时间统计不准确，同一代码提交两次，时间差别都很大，不能作为分析效率的依据</p>
