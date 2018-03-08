---
layout: post
title:  "leet696"
author: "yzpwslc"
date: 2018-03-08 21:12
---

<p>题目：在只包含0、1的字符串中查找连续出现1和0数量相同的字符串，统计个数。</p>
<p>分析：每个符合要求的子字符串都以01或10为中心，查找01或10,在其附近寻找最长符合条件字符串，以该字符串中间位置为起点，截取子字符串递归操作</p>
<p>代码如下：</p>
{% highlight python %}
        pattern = re.compile(r'(01)|(10)')
        strNum = [0]
        def findStr(s):
            if re.search(pattern,s):
                start = re.search(pattern,s).start()
                lLeft = start + 1
                subStr = s[lLeft:]
                lRight = subStr.find(s[0])
                if lRight < 0:
                    lRight = len(subStr)
                strNum[0] += min(lRight,lLeft)
                findStr(subStr)
        findStr(s)
        return strNum[0]
{% endhighlight%}
<p>思考：1.这个方案可以得到正确结果，然而最后提交时提示超时，在讨论区找到了和我思路类似，但显然更好的实现方法，代码如下：</p>
{% highlight python %}
        s = map(len, s.replace('01', '0 1').replace('10', '1 0').split())
        return sum(min(a, b) for a, b in zip(s, s[1:]))
{% endhighlight %}
