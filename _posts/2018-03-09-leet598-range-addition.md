---
layout: post
title:  "leet598.Range Addition II"
author: "yzpwslc"
date: 2018-03-09 21:21
---

<p>题目：计算m*n零矩阵经过一系列操作后，最大值的个数</p>
<p>分析：如果没有操作，最大值为0,数量为m*n，否则，寻找操作区域的交集，交集中元素的个数即为要求值</p>
<p>代码如下：</p>
{% highlight python %}
        if ops:
            lst = map(min,zip(*ops))
            return min(lst[0],m) * min(lst[1],n)
        else:
            return m * n
{% endhighlight %}
