---
layout: post
title:  "leet561"
author: "yzpwslc"
---

<p>题目：计算整数的补数</p>
<p>分析：要获得补数，需要对该整数按位取反；因此，需要寻找与该数值二进制位数相同的最大数,进行异或运算</p>
<p>代码如下：</p>
{% highlight python %}
class Solution(object):
    def findComplement(self, num):
        """
        :type num: int
        :rtype: int
        """
        binNum = bin(num)
        mask = 2 ** (len(binNum) - 2) - 1
        ret = num ^ mask
        return ret


def stringToInt(input):
    return int(input)


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
            num = stringToInt(line)

            ret = Solution().findComplement(num)

            out = intToString(ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
{% endhighlight%}
<p>思考：计算掩码时，使用幂运算，影响运算速度，可见思维过于死板，浏览该问题讨论时，看到使用移位运算才恍然大悟，还需多多训练。</p>

