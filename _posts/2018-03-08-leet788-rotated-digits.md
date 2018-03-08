---
layout: post
title:  "leet788.Rotated Digits"
author: "yzpwslc"
date: 2018-03-08 22:33
---

<p>题目：寻找N以内每位数字旋转后依然为数字，且与原数不同的数的个数</p>
<p>分析：对于单个数旋转后依然位数字的数字，计算笛卡尔积，获得与N相同位数以内的所有组合，排除完全由旋转后与自身相同的数，排除重复数字，排序后，小于N的数的个数便是结果</p>
<p>代码如下：</p>
{% highlight python %}
        lst = []
        exLst = []
        ret = 0
        for i in range(1,len(str(N)) + 1):
            lst += [int(''.join(x)) for x in itertools.product('0125689',repeat = i)]
            exLst += [int(''.join(x)) for x in itertools.product('018',repeat = i)]
        lst = set(lst) - set(exLst)
        lst = list(lst)
        lst.append(N)
        lst.sort(reverse=True)
        return  (len(lst) - lst.index(N) - 1)
{% endhighlight%}
<p>思考：1.这个题目目前讨论区最近答案没有完全正确的，如果能通过检测纯属侥幸。2.原本以为将自身旋转后不相同数字排列组合就可以，结果发现错了。3.最初使用升序排序，发现如果N自身也是满足要求的数，它就也存在与列表，indexof就会导致少计算一个，因此改为逆序，克服了这个问题。4.洗澡的时候突然发现，由于计算笛卡尔积包含0,因此生成的结果自然包含了位数低于len(N)的所有符合要求的数，无需进行循环，修改后的代码如下</p>
{% highlight python %}
        lst = []
        exLst = []
        ret = 0
        lst += [int(''.join(x)) for x in itertools.product('0125689',repeat = len(str(N)) + 1)]
        exLst += [int(''.join(x)) for x in itertools.product('018',repeat = len(str(N)) + 1)]
        lst = set(lst) - set(exLst)
        lst = list(lst)
        lst.append(N)
        lst.sort(reverse=True)
        return  (len(lst) - lst.index(N) - 1)
{% endhighlight %}
