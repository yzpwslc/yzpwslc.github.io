---
layout: post
title:  "leet13.roman tointeger"
author: "yzpwslc"
date: 2018-03-10 10:50
---

<p>题目：将罗马数字转换为阿拉伯数字</p>
<p>分析：建立罗马数字字符与阿拉伯数字对应表，遍历给定的罗马数字，遇到(i,x,c)判断右侧是否有更大的数，有则返回对应值的负值，没有则返回正值，其余情况返回正值</p>
<p>代码如下：</p>
{% highlight python %}
        romanDict = {'I':1,'V':5,'X':10,'L':50,'C':100,'D':500,'M':1000}
        leftNums = ['I','X','C']
        ret = 0
        def charConvert(c,left = True):
            retNum = 0
            if left and c in leftNums:
                retNum = romanDict[c] * -1
            else:
                retNum = romanDict[c]
            return retNum
        for i,x in enumerate(s):
            if (i < len(s) - 1) and (x in leftNums) and (romanDict[x] < romanDict[s[i + 1]]):
                ret += charConvert(x)
            else:
                ret += charConvert(x,False)
        return ret
{% endhighlight%}
<p>思考：1.总是和其他语言混淆，把&当作and用，总是和其他语言混淆，把&当作and用，总是和其他语言混淆，把&当作and用。重要的事情说三遍！2.没有判断输入罗马数字的合法性</p>
