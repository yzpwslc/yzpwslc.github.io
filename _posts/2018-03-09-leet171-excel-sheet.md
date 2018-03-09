---
layout: post
title:  "leet171.excel sheet column"
author: "yzpwslc"
date: 2018-03-09 20:45
---

<p>题目：将输入字符串转换为指定数字</p>
<p>分析：可视为26进制转10进制</p>
<p>代码如下：</p>
{% highlight python %}
        return int(reduce(lambda an1,an:an1 + an,[m * math.pow(26,i) for i,m in enumerate([ord(x) - ord('A') + 1 for x in list(s)[::-1]])]))

{% endhighlight%}
<p>看到一个思路和我一致，但代码简单很多的家伙。1.看到他的代码我意思到map函数s、可直接用于字符串，而我多此一举进行了字符串到列表的转换.2.我完全没有意识到reduce归并函数的强大之处，使用不够重复</p>
