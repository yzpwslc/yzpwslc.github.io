---
layout: post
title:  "leet455.assign cookies"
author: "yzpwslc"
date: 2018-03-10 17:36
---

<p>题目：分配饼干</p>
<p>分析：将孩子喂养列表及饼干列表按升序排序，遍历孩子喂养列表，在饼干列表中寻找能满足的饼干，找到后，满足数加1</p>
<p>代码如下：</p>
{% highlight python %}
        g.sort()
        s.sort()
        cNums = 0
        for x in g:
            for i,y in enumerate(s):
                if x <= y:
                    cNums += 1
                    s = s[i+1:]
                    break
        return cNums
{% endhighlight%}

