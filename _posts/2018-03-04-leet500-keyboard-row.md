---
layout: post
title:  "leet500"
author: "yzpwslc"
date: 2018-03-04 16:09
---

<p>题目：筛选出能用键盘一行输入的字符串</p>
<p>分析：要求该字符串的所有字符都处于键盘上的同一行，分别建立键盘三行字母的字符集，判断并过滤列表</p>
<p>代码如下：</p>
{% highlight python %}
import json
import re
class Solution(object):
    def findWords(self, words):
        """
        :type words: List[str]
        :rtype: List[str]
        """
        # fRet = [self.matchStr(x) for x in words]
        ret = filter(self.matchStr,words)
        return ret
    def matchStr(self,str0):
        p1 = re.compile(r'[qwertyuiop]',re.I)
        p2 = re.compile(r'[asdfghjkl]',re.I)
        p3 = re.compile(r'[zxcvbnm]',re.I)
        ret = False
        flags = 0
        if re.search(p1,str0):
            flags += 1
        if re.search(p2,str0):
            flags += 1
        if re.search(p3,str0):
            flags += 1

        if flags < 2:
            ret = True
        return ret



def stringToStringArray(input):
    return json.loads(input)


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
            words = stringToStringArray(line)

            ret = Solution().findWords(words)

            out = stringArrayToString(ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
{% endhighlight%}
<p>思考：可能个人太过于偏爱正则表达式了，虽然集合也在脑中闪过，但最终选择了正则匹配，最终速度不够理想，看讨论里有个计算速度超过95%用户的大神使用二进制掩码的方式计算，个人认为原理和集合差不多，但代码偏底层，效率略高，不过可读性较差。</p>
