---
layout: post
title:  "leet412"
author: "yzpwslc"
date: 2018-03-04 18:24
---

<p>题目：用指定字符串代替1到n的整数</p>
<p>分析：按顺序判断被3和被5整除</p>
<p>代码如下：</p>
{% highlight python %}
import json
class Solution(object):
    def fizzBuzz(self, n):
        """
        :type n: int
        :rtype: List[str]
        """
        ret = [self.int2str(x) for x in range(1,n + 1)]
        return ret

    def int2str(self,num):
        ret = ""
        if num % 3 == 0:
            ret += "Fizz"
        if num % 5 == 0:
            ret += "Buzz"
        if ret == "":
            ret = str(num)
        return ret



def stringToInt(input):
    return int(input)


def stringArrayToString(input):
    return json.dumps(input)


def main():
    import sys
    def readlines():
        for line in sys.stdin:
            yield line.strip('\n')

    lines = readlines()
    while True:
        try:
            line = lines.next()
            n = stringToInt(line)

            ret = Solution().fizzBuzz(n)

            out = stringArrayToString(ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
{% endhighlight%}
<p>思考：看了讨论区的方案，python果然很freedom</p>
