---
layout: post
title:  "leet492.construct the rectange"
author: "yzpwslc"
date: 2018-03-09 21:57
---

<p>题目：给定矩形面积，计算长宽，要求长大于宽，长-宽最小</p>
<p>分析：实质为计算一整数最接近的一对因子，从面积平方根向1搜索</p>
<p>代码如下：</p>
{% highlight python %}
        sArea = math.sqrt(area)
        if sArea * int(sArea) != area:
            for x in range(int(sArea),0,-1):
                if area % x == 0:
                    return [area//x,x]
        else:
            return [int(sArea)] * 2
{% endhighlight%}
