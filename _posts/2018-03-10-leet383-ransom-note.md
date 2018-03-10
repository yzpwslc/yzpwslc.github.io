---
layout: post
title:  "leet383.ransom note"
author: "yzpwslc"
date: 2018-03-10 11:38
---

<p>题目：给定的字符串能否由另一个字符串中的字符组成，每个字符只能用一次</p>
<p>分析：遍历给定字符串，在另一个字符串中查找，找到的话，将其替换为‘’，找不到则返回False</p>
<p>代码如下：</p>
{% highlight python %}
        for x in ransomNote:
            if magazine.find(x) > -1:
                magazine = magazine.replace(x,'',1)
            else:
                return False
        return True
{% endhighlight%}
