---
layout: post
title:  "leet242.valid anagram"
author: "yzpwslc"
date: 2018-03-09 01:08
---

<p>题目：两个字符串是否互为变位词</p>
<p>分析：变位词特点，长度相同，每个字符数量相同，找到字符串的字符集，依次在两个字符串中删除字符集中的字符，判断删除后的长度，长度不同，则返回False</p>
<p>代码如下：</p>
{% highlight python %}
        if s == t:
            return True
        if len(s) != len(t):
            return False
        if set(s) != set(t):
            return False
        for x in set(s):
            t = t.replace(x,'')
            s = s.replace(x,'')
            if len(t) != len(s):
                return False
        return True
{% endhighlight%}
<p>思考：1.如果字符串中字符扩展到整个unicode范围，该方法依然适用。2.如果采用将两字符串相加，对字符归并求异或无法排除两个字符串每个字符串中每个字符数量均为偶数的情况</p>
