---
layout: post
title:  "leet168.excel sheet column title"
author: "yzpwslc"
date: 2018-03-09 20:17
---

<p>题目：将给定数字输出为对应字符串</p>
<p>分析：可认为是26进制转换</p>
<p>代码如下：</p>
{% highlight python %}
        return  self.num2char(n)

    def num2char(self,num,fix = ''):
        if (num - 1) // 26 > 0:
            fix += self.num2char((num - 1) // 26,fix)
            self.ret += self.num2char(num - ((num -1) // 26 * 26),fix)
        else:
            self.ret = chr(ord('A') + (num - 1) % 26)
        return self.ret
{% endhighlight%}
