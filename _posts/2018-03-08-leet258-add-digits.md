---
layout: post
title:  "leet258"
author: "yzpwslc"
date: 2018-03-08 00:36
---

<p>题目：将一个数每位相加直到变成个位数。</p>
<p>分析：通过将整数变为字符串再转换为数字列表的方式分离每一位，使用归并方式计算和，然后进行递归，直到达到目标</p>
<p>代码如下：</p>
{% highlight python %}
        res = [0]
        def sumBit(num):
            if num > 9:
                temp = list(str(num))
                res.append(reduce(lambda x,y:int(x) + int(y),temp))
                sumBit(res[-1])
            else:
                res.append(num)
        sumBit(num)
        return res[-1]
{% endhighlight%}
<p>思考：我实在想不到可以有办法不用循环，时间复杂度为O(1)解出这个问题，看别人解法，才知道这个东东叫Digital Root,有一个类似(1+2+3+4+6)%9=12346%9的数学公式，代码如下</p>
{% highlight python %}
return num % 9 or 9 if num else 0
{% endhighlight %}
