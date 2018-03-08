---
layout: post
title:  "leet283.Move Zeros"
author: "yzpwslc"
date: 2018-03-08 19:09
---

<p>题目：将列表中0移到列表尾部，不改变其他元素顺序。</p>
<p>分析：使用remove方法删除找到的第一个0并删除，并在末尾添加一个0</p>
<p>代码如下：</p>
{% highlight python %}
        for i in range(nums.count(0)):
            nums.remove(0)
            nums.append(0)
{% endhighlight%}
