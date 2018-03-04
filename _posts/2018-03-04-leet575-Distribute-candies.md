---
layout: post
title:  "leet575"
author: "yzpwslc"
date: 2018-03-04 22:47
---

<p>题目：用一个数组每个元素代表一根蜡烛，每种数字代表一类蜡烛，将蜡烛平均分给兄妹，一个人最多的种类数</p>
<p>分析：列表转为集合，统计种类数，种类数大于蜡烛一半，则最多获得总数一半，否则为种类数</p>
<p>代码如下：</p>
{% highlight python %}
import json
class Solution(object):
    def distributeCandies(self, candies):
        """
        :type candies: List[int]
        :rtype: int
        """
        return len(set(candies)) if len(set(candies)) <= len(candies) >> 1 else len(candies) >> 1



def stringToIntegerList(input):
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
            candies = stringToIntegerList(line)

            ret = Solution().distributeCandies(candies)

            out = intToString(ret)
            print out
        except StopIteration:
            break


if __name__ == '__main__':
    main()
{% endhighlight%}

