---
layout: post
title:  "leet485"
author: "yzpwslc"
date: 2018-03-07 20:20
---

<p>题目：计算一个整数列表中1连续最长出现次数。</p>
<p>分析：遍历列表遇到0重新计算连续出现次数，记录大于之前最大次数的数值</p>
<p>代码如下：</p>
{% highlight python %}
        maxLen = 0
        length = 0
        for x in nums:
            if x < 1:
                if maxLen < length:
                    maxLen = length
                length = 0
            else:
                length += 1
        return max(maxLen,length)
{% endhighlight%}
<p>思考：还有一种思路，将列表转换为字符串，以0为分隔符截取，计算每部分的长度，求出最大值，效率明显会低于前者，代码没写</p>
