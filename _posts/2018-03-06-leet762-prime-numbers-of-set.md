---
layout: post
title:  "leet673"
author: "yzpwslc"
date: 2018-03-06 23:48
---

<p>题目：统计给定区间内数值二进制形式1的个数为质数的元素数量</p>
<p>分析：将元素转换为二进制字符串，统计1的数量，判断是否为质数，为减少重复查询，建立一个已查询素数集合</p>
<p>代码如下：</p>
{% highlight python %}
class Solution(object):
    def countPrimeSetBits(self, L, R):
        """
        :type L: int
        :type R: int
        :rtype: int
        """
        nums = 0
        primeList = set()
        for x in range(L,R + 1):
            counts = bin(x).count('1')
            if set([counts]).issubset(primeList) | isPrime(counts):
                primeList.add(counts)
                nums += 1
        return nums

def isPrime(num):
    res = 1
    if num > 1:
        if num > 2:
            for i in range(2,int(math.sqrt(num) + 1)):
                if num % i == 0:
                    res = 0
                    break
    else:
        res = 0
    return res
{% endhighlight%}
